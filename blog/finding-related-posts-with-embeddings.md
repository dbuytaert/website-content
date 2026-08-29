---
url: 'https://dri.es/finding-related-posts-with-embeddings'
title: 'Finding related posts with embeddings'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-08-26T04:40:02-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How I built related posts for my blog using embeddings, and why the obvious way of comparing them made almost every post look related.'
tags:
  - 'My site'
  - Drupal
  - 'Artificial Intelligence'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7498328825290768384/' }
published: true
featured: false
id: 6306
---

# Finding related posts with embeddings

I added a new feature to my blog: a list of related posts at the bottom of each post. I implemented it using embeddings, and this note documents how.

I looked at how other content management systems identify related posts: most use shared tags, backlinks, manual curation, or embeddings. I chose embeddings, which compare the meaning of each post, because they can uncover connections without shared tags, existing links, or manual curation.

## Embeddings turn meaning into numbers

An embedding model reads text and returns a vector: a long list of numbers. The model I use, [`bge-base-en-v1.5`](https://huggingface.co/BAAI/bge-base-en-v1.5) from the Beijing Academy of Artificial Intelligence (BAAI), returns 768 numbers for each post.

For one of my posts, the first handful of those coordinates looks something like this:

```text
[ 0.021, -0.045, 0.038, -0.012, 0.007, ..., 0.019 ]
```

You can think of those 768 numbers as coordinates in a high-dimensional meaning space, where each dimension captures some pattern the model learned from text. 

Conceptually, it is a bit like tagging each blog post with hundreds of auto-generated tags, except that these tags are unnamed (they are just numbers) and distributed (meaning is spread across all of them). Together, the 768 numbers place the post near other posts with similar meaning.

This is what lets two posts match even when they use different words. During training, the model learns that certain words and phrases appear in similar contexts or play similar roles, so it places them near each other in the space. It does not need "car" and "automobile" to share any letters to learn that they are used in related ways.

## Raw cosine similarity makes everything look related

Once every post has an embedding vector, the next question is how to compare them. This is where I had to dust off a little math. Fortunately, it turned out to be mostly high-school math: averages, angles, and multiplication.

The standard way to compare two vectors is [cosine similarity](https://en.wikipedia.org/wiki/Cosine_similarity). Imagine each vector as an arrow pointing away from the origin. Cosine similarity measures the angle between two of these arrows and then takes the cosine of that angle, which is where the name comes from. 

Two arrows pointing in nearly the same direction form a small angle, and the cosine of a small angle is close to 1, meaning the posts are related. As the arrows spread apart, the cosine falls: at a right angle it is 0, and for arrows pointing in opposite directions it drops to -1, so unrelated posts score closer to 0 or even negative.

In practice, these raw cosine values can be misleading, because embedding models rarely spread their vectors evenly in every direction. They tend to pack most vectors into a narrow cone, a property called [anisotropy](https://arxiv.org/abs/1907.12009). It means that the cosine similarities tend to cluster in a narrow band. 

On my blog, the raw cosine similarity between two randomly chosen posts is almost always between 0.5 and 0.75, with a median of 0.64. The practical effect is that almost any two posts look somewhat similar even if they are not. 

## Mean-centering reveals what makes each post distinct

Anisotropy has several known fixes. The easiest is *mean-centering*, which is what I use and what the rest of this section explains. 

Other solutions include [All-but-the-top](https://arxiv.org/abs/1702.01417), which removes the average and the next few strongest directions. [Whitening](https://arxiv.org/abs/2103.15316) stretches the space so every direction carries equal weight (the name comes from white noise). 

With mean-centering you simply compute the average vector across all posts and subtract it from every post's vector. Subtracting the average vector from each post removes what all posts have in common; what remains is what makes each post distinct. 

A modern model like `bge-base-en-v1.5` already suffers less from anisotropy than older or simpler encoders: it is trained with [contrastive learning](https://en.wikipedia.org/wiki/Self-supervised_learning#Contrastive_self-supervised_learning), which pushes unrelated texts apart, and version 1.5 was tuned specifically to spread out its similarity scores. That said, centering still made the scores much more useful on my corpus.

An example might help. Imagine three posts with only two numbers each instead of 768:

```text
A = (0.90, 0.10)
B = (0.85, 0.80)
C = (0.80, 0.75)
```

At first glance, all three posts might look somewhat similar. In every post the first number is high and close to the others (0.90, 0.85 and 0.80). A number that barely changes from post to post tells you little about how they differ, so that first number is not very useful.

The average (mean) of the three vectors is:

```text
mean = (0.85, 0.55)
```

Now subtract that average from each post:

```text
A = ( 0.05, -0.45)
B = ( 0.00,  0.25)
C = (-0.05,  0.20)
```

Now the picture is already clearer. B and C both have a positive second number, so they point in roughly the same direction; A's second number is negative, so it points somewhere else.

Before centering, everything looked similar. After centering, the comparison focuses on what is different from the average.

## Normalization reduces comparison to a dot product

After centering, each vector has a length as well as a direction. Length says how far a post sits from the average, and direction says in what way it differs. 

I want to rank posts by what they are about, not by how unusual they are, so only the direction matters. Hence, we normalize each vector by dividing it by its own length, which scales it to length 1 and moves it onto the unit circle (or, in 768 dimensions, the unit sphere), leaving only its direction. 

It also makes the comparison cheaper. Cosine similarity is normally the dot product divided by the product of the two vectors' lengths. If both vectors have length 1, that denominator is 1 × 1 = 1, so the expression reduces to the dot product alone: multiply the two lists number by number, then add the results.

Using the same example, the centered vectors for B and C are:

```text
B = ( 0.00, 0.25)
C = (-0.05, 0.20)
```

First, normalize each vector to length 1. A vector's length is the square root of the sum of its squared numbers (good old Pythagoras, only with more numbers). B has length √(0.00² + 0.25²) = 0.25, while C has length √((-0.05)² + 0.20²) ≈ 0.206, so dividing each vector by its own length gives:

```text
B ≈ ( 0.00, 1.00)
C ≈ (-0.24, 0.97)
```

Then take the dot product:

```text
(0.00 × -0.24) + (1.00 × 0.97) = 0.97
```

That is a strong match: the closer the score is to 1, the more the two posts point in the same direction. B and C are nearly aligned.

A, after normalization, points mostly downward. Next to B:

```text
A ≈ ( 0.11, -0.99)
B ≈ ( 0.00,  1.00)
```

Multiplying them the same way:

```text
(0.11 × 0.00) + (-0.99 × 1.00) = -0.99
```

That is not a match at all.

## The PHP code is shorter than the explanation

The production code does the same arithmetic, just with 768 numbers per post instead of two:

```php
public static function center(array $raw): array {
  if ($raw === []) {
    return [];
  }
  $mean = array_fill(0, count(reset($raw)), 0.0);
  foreach ($raw as $vector) {
    foreach ($vector as $i => $value) {
      $mean[$i] += $value;
    }
  }
  $count = count($raw);
  foreach ($mean as $i => $sum) {
    $mean[$i] = $sum / $count;
  }
  $centered = [];
  foreach ($raw as $nid => $vector) {
    $norm = 0.0;
    foreach ($vector as $i => $value) {
      $vector[$i] = $value - $mean[$i];
      $norm += $vector[$i] * $vector[$i];
    }
    // A vector sitting exactly on the mean centers to zero; fall back to 1.0
    // so the division below never hits a zero norm.
    $norm = sqrt($norm) ?: 1.0;
    foreach ($vector as $i => $value) {
      $vector[$i] = $value / $norm;
    }
    $centered[$nid] = $vector;
  }
  return $centered;
}

public static function topMatches(array $source, array $pool, int $self): array {
  $scores = [];
  foreach ($pool as $nid => $vector) {
    if ($nid === $self) {
      continue;
    }
    $similarity = 0.0;
    foreach ($source as $i => $value) {
      $similarity += $value * $vector[$i];
    }
    $scores[$nid] = $similarity;
  }
  arsort($scores);
  return array_keys(array_slice($scores, 0, 3, TRUE));
}
```

While my explanation was long, both PHP methods are relatively short. In `center()`, each vector has the corpus mean subtracted, then is divided by its own length. In `topMatches()`, I calculate the cosine similarity between one post and every other post, then keep the three highest.

You might expect a vector database to replace all of this. It would replace some of it: storing a vector and asking for the closest three would remove `topMatches()`, but it would not remove `center()`. Centering is optional, but it meaningfully improved my results.

A vector database likely makes centering harder. Today I store raw vectors and subtract the average when I compare them, so a new post does not change anything I have stored. A vector database would search what I stored, so the subtraction would have to happen before storing. I'd have to update all stored vectors for every new post or every edit, which feels more complex. Maybe vector databases have a good answer for that; I have not looked.

## One-time embeddings, occasional ranking

You might wonder how expensive it is to generate these embeddings and compare all these vectors. It turns out to be fast and cheap.

There are two kinds of work, and they happen at different times. Generating an embedding calls an AI model, but happens only once after a post is created or edited. Ranking uses ordinary PHP arithmetic and happens occasionally, when Drupal rebuilds a page's cached related-post list.

I run the model on Cloudflare Workers AI. To generate an embedding, my server makes an HTTPS call that passes the post's text to Cloudflare, which runs the model and returns the 768-number vector. That round trip takes about 250ms. It happens on the first view after a post is created or edited, and the vector is then cached. The model is deterministic, so the same text always produces the same 768 numbers. 

Cloudflare bills Workers AI usage in units it calls Neurons and includes 10,000 free each day. Embedding my full archive of roughly 1,500 posts used roughly 4,000 Neurons, and a new post costs about three. Embedding my blog is basically free.

Calculating the related posts never calls the AI model. It all happens in [Drupal](https://www.drupal.org/), my website's content management system. When Drupal needs to build one of the related posts lists, it loads all the stored vectors, centers them, and scores the current post against all the others: roughly 1,500 dot products, each over 768 numbers. This takes around 250ms on my site. After a list has been built, it is cached.

In other words, my website never loads model weights; it just stores the 768 numbers that come back. The machine-learning compute lives at Cloudflare's edge, and my server stays a plain PHP application. None of this needs a vector database or a machine-learning framework: one HTTP call generates the embedding, a key-value store caches it, and a few dozen lines of arithmetic choose the related posts.

Tags are too blunt, backlinks only capture the links I remembered to make, and manual curation does not scale. All three need me to notice the connection first. Using embeddings might sound a bit scary, but they turned out to be easy to implement, fully automated, and able to surface posts I would never have thought to link.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7498328825290768384/).
