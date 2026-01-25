---
url: 'https://dri.es/infinite-scroll-with-htmx'
title: 'Infinite scroll with htmx'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-11-26T17:55:48-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'My site'
  - Drupal
  - 'Photo stream'
  - Photography
  - JavaScript
image: 'image miscellaneous-2022/train-2'
published: true
featured: false
id: 5951
---

# Infinite scroll with htmx

[image miscellaneous-2022/train-2 caption=false]

Several years ago, [I built a photo stream](https://dri.es/a-photo-stream-for-my-site) on my Drupal-powered website. You can see it at https://dri.es/photos. This week, I gave it a small upgrade: infinite scroll.

My first implementation used vanilla JavaScript using the [Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API), and it worked fine. It took about 30 lines of custom JavaScript and 20 lines of PHP code.

But Drupal now ships with [htmx](https://htmx.org/) support, and that had been on my mind. So a couple of hours later, I rewrote the feature with htmx to see if it could do the same job more simply.

It's something I love about [Drupal](https://www.drupal.org/): how we keep adding small, well-chosen features like htmx support. Not flashy, but they quietly make everyday work nicer. Years ago, Drupal was one of the first CMSes to adopt jQuery, and our early adoption helped contribute to its widespread use. Today, we're replacing parts of jQuery with htmx, and Drupal may well be among the first CMSes to ship htmx in core.

If, like me, you haven't used htmx before, it lets you add dynamic behavior to pages using HTML attributes instead of writing JavaScript. Want to load content when something is clicked or scrolled into view? You add an attribute like `hx-get="/load-more"` and htmx handles the request, then swaps the response into your page. It gives you [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming))-style interactions without having to write JavaScript.

To make the photo stream load more images as you scroll, I added an "htmx trigger". When it scrolls into view, htmx fetches more photos and appends them to the right container.  The resulting HTML looks like this:

```html
<div hx-get="/photos/load-more?offset=25"
         hx-trigger="revealed"
         hx-target="#album"
         hx-swap="beforeend">
  <figure>
   ...
  </figure>
</div>
```

The `hx-get` points to a controller that returns the next batch of photos. The `hx-trigger="revealed"` attribute means "fire when scrolled into view". The `hx-target="#album"` tells htmx where to put the new content, and `hx-swap="beforeend"` appends it at the end of that `#album` container.

I didn't want users to hit the last photo and have to wait for more to load. To keep the scrolling smooth, I added the trigger a few photos _before_ the end. This pre-fetches the next batch before the user even realizes they are running out of photos. This is what the code in Drupal looks likes:

```php
// Trigger 3 images before the end to prefetch the next batch.
$trigger = array_keys($images)[max(0, count($images) - 4)];

foreach ($images as $key => $image) {
  …

  if ($key === $trigger) {
    // Add htmx attributes to the <div> surrounding the image.
    $build['#attributes']['hx-get'] = '/photos/load-more?offset=' . ($offset + $limit);
    $build['#attributes']['hx-trigger'] = 'revealed';
    $build['#attributes']['hx-target'] = '#album';
    $build['#attributes']['hx-swap'] = 'beforeend';
  }
}
```

And the controller that returns the HTML:

```php
public function loadMorePhotos(Request $request) {
  $offset = $request->query->getInt('offset', 0);
  $limit = 25;
  $photos = PhotoCollection::loadRecent($offset, $limit);
  if (!$photos) {
    return new Response('');
  }

  $build = $this->buildImages($photos, $offset, $limit);
  $html = \Drupal::service('renderer')->renderRoot($build);
  return new Response($html);
}
```

Each response includes 25 photos. It continues fetching new photos as you scroll down until there are no more photos, at which point the controller returns an empty response and the scrolling stops.

As you can tell, there is _no_ custom JavaScript in my code. It's all abstracted away by htmx. The htmx version took less than 10 lines of PHP code (shown above) instead of 30+ lines of custom JavaScript. The `loadMorePhotos` controller I needed either way.

The savings are negligible. Replacing a couple dozen lines of JavaScript won't change the world.  And at 16KB gzipped, htmx is much larger than the custom JavaScript I wrote by hand. But it still feels reasonable. My photo stream is image-heavy, and htmx adds less than 0.5% to the initial page weight.

Overall, I'd say that htmx grew on me. There is something satisfying about declarative code. You describe what should happen, and the implementation disappears. I may try it in a few more places to improve the user experience of my site.
