---
url: 'https://dri.es/optimizing-site-performance-by-lazy-loading-images'
title: 'Optimizing site performance by "lazy loading" images'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2019-02-21T03:48:30-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Learn how to implement lazy loading images to improve the performance of your website.'
tags:
  - 'Web performance'
  - Drupal
  - 'My site'
  - POSSE
image: blog/webpagetest-images-february-2019-after
published: true
id: 4771
---

# Optimizing site performance by "lazy loading" images

Recently, I've been spending some time making performance improvements to my site. In my previous blog post on this topic, I described my progress [optimizing the JavaScript and CSS usage on my site](https://dri.es/optimizing-site-performance-by-reducing-javascript-and-css), and concluded that image optimization was the next step.

Last summer I published [a blog post about my vacation in Acadia National Park](https://dri.es/our-vacation-at-acadia-national-park). Included in that post are 13 photos with a combined size of about 4 MB.

When I benchmarked that post with [WebPageTest](https://webpagetest.org), it showed that it took 7.275 seconds (blue vertical line) to render the page.

The graph shows that the browser downloaded all 13 images to render the page. Why would a browser download all images if most of them are below the fold and not shown until a user starts scrolling? It makes very little sense.

As you can see from the graph, downloading all 13 images take a very long time (purple horizontal bars). No matter how much you [optimize your CSS and JavaScript](https://dri.es/optimizing-site-performance-by-reducing-javascript-and-css), this particular blog post would have remained slow until you optimize how images are loaded.

<div class="large">
  [image blog/webpagetest-images-february-2019-before]
</div>

"Lazy loading" images is one solution to this problem. Lazy loading means that the images aren't loaded until the user scrolls and the images come into the browser's viewport.

You might have seen lazy loading in action on websites like Facebook, Pinterest or Medium. It usually goes like this:

- You visit a page as you normally would, scrolling through the content.
- Instead of the actual image, you see a blurry placeholder image.
- Then, the placeholder image gets swapped out with the final image as quickly as possible.

[image blog/lazy-loading-images-animation resize=false]

To support lazy loading images on my blog I do three things:

1. Automatically generate lightweight yet useful placeholder images.
2. Embed the placeholder images directly in the HTML to speed up performance.
3. Replace the placeholder images with the real images when they become visible.

### Generating lightweight placeholder images

To generate lightweight placeholder images, I implemented [a technique used by Facebook](https://code.fb.com/android/the-technology-behind-preview-photos/): create a tiny image that is a downscaled version of the original image, strip out the image's metadata to optimize its size, and let the browser scale the image back up.

To create lightweight placeholder images, I resized the original images to be 5 pixels wide. Because I have [about 10,000 images on my blog](https://dri.es/responsive-images-for-dri-es), my [Drupal](https://www.drupal.org)-based site automates this for me, but here is how you create one from the command line using [ImageMagick](https://www.imagemagick.org/)'s `convert` tool:

```shell
$ convert -resize 5x -strip original.jpg placeholder.jpg
```

- `-resize 5x` resizes the image to be 5 pixels wide while maintaining its aspect ratio.
- `-strip` removes all comments and redundant headers in the image. This helps make the image's file size as small as possible.

The resulting placeholder images are tiny – often shy of 400 bytes.

[image blog/lazy-loading-images-original-1]
[image blog/lazy-loading-images-placeholder-1]

Here is another example to illustrate how the colors in the placeholders nicely match the original image:

[image blog/lazy-loading-images-original-2]
[image blog/lazy-loading-images-placeholder-2]

Even though the placeholder image should only be shown for a fraction of a second, making them relevant is a nice touch as they suggest what is coming. It's also an *important* touch, as [users are very impatient with load times on the web](https://dri.es/faster-is-better).

### Embedding placeholder images directly in HTML

One not-so-well-known feature of the `<img>` element is that you can embed an image directly into the HTML document using [the data URL scheme](https://tools.ietf.org/html/rfc2397):

```html
<img src="data:image/jpg;base64,/9j/4AAQSkZJRgABAQEA8ADwAAD/2wB
  DAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQICAQECAQEB
  AgICAgICAgICAQICAgICAgICAgL/2wBDAQEBAQEBAQEBAQECAQEBAgICAgICA
  gICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgL/wA
  ARCAADAAUDAREAAhEBAxEB/8QAFAABAAAAAAAAAAAAAAAAAAAACf/EAB8QAAM
  AAQMFAAAAAAAAAAAAAAECAwcEBQYACAkTMf/EABUBAQEAAAAAAAAAAAAAAAAA
  AAIG/8QAJBEAAQIFAgcAAAAAAAAAAAAAAQURAAIDBDEGFBIVQUVRcYH/2gAMA
  wEAAhEDEQA/AAeyb5HO8o8lSLZd01Jz2nbKoK4yxDVvZqYl7uaV4CWdmZQSSS
  ST86FJBsafEJK15KD05ioNk4G6Yeg0V9bVCmZpXt08sB2hJ8DJ2Tn7H/2Q==" />
```

Data URLs are composed of four parts: the `data:` prefix, a [media type](https://en.wikipedia.org/wiki/Media_type) indicating the type of data (`image/jpg`), an optional `base64` token to indicate that the data is base64 encoded, and the base64 encoded image data itself.

```shell
data:[<media type>][;base64],<data>
```

To base64 encode an image from the command line, use:

```shell
$ base64 placeholder.jpg
```

To base64 encode an image in PHP, use:

```php
$data =  base64_encode(file_get_contents('placeholder.jpg'));
```

What is the advantage of embedding a base64 encoded image using a data URL? It eliminates HTTP requests as the browser doesn't have to set up new HTTP connections to download the images. Fewer HTTP requests usually means faster page load times.

### Replacing placeholder images with real images

Next, I used JavaScript's `IntersectionObserver` to replace the placeholder image with the actual image when it comes into the browser's viewport. I followed [Jeremy Wagner](https://jeremy.codes/)'s approach shared on [Google Web Fundamentals Guide on lazy loading images](https://developers.google.com/web/fundamentals/performance/lazy-loading-guidance/images-and-video/) – with some adjustments.

It starts with the following HTML markup:

```html
<img class="lazy" src="placeholder.jpg" data-src="original.jpg" />
```

The three relevant pieces are:

1. The `class="lazy"` attribute, which is what you'll select the element with in JavaScript.
2. The `src` attribute, which references the placeholder image that will appear when the page first loads. Instead of linking to `placeholder.jpg` I embed the image data using the data URL technique explained above.
3. The `data-src` attribute, which contains the URL to the original image that will replace the placeholder when it comes in focus.

Next, we use JavaScript's `IntersectionObserver` to replace the placeholder images with the actual images:

```js
document.addEventListener('DOMContentLoaded', function() {
  var lazyImages = [].slice.call(document.querySelectorAll('img.lazy'));

  if ('IntersectionObserver' in window) {
    let lazyImageObserver = new IntersectionObserver(
      function(entries, observer) {
        entries.forEach(function(entry) {
          if (entry.isIntersecting) {
            let lazyImage = entry.target;
            lazyImage.src = lazyImage.dataset.src;
            lazyImageObserver.unobserve(lazyImage);
          }
        });
    });

    lazyImages.forEach(function(lazyImage) {
      lazyImageObserver.observe(lazyImage);
    });
  }
  else {
    // For browsers that don't support IntersectionObserver yet,
    // load all the images now:
    lazyImages.forEach(function(lazyImage) {
      lazyImage.src = lazyImage.dataset.src;
    });
  }
});
```

This JavaScript code queries the DOM for all `<img>` elements with the `lazy` class. The `IntersectionObserver` is used to replace the placeholder image with the original image when the `img.lazy` elements enter the viewport. When `IntersectionObserver` is not supported, the images are replaced on the `DOMContentLoaded` event.

By default, the `IntersectionObserver`'s callback is triggered the moment a single pixel of the image enters the browser's viewport. However, using the `rootMargin` property, you can trigger the image swap before the image enters the viewport. This reduces or eliminates the *visual* or *perceived lag time* when swapping a placeholder image for the actual image.

I implemented that on my site as follows:

```js
const config = {
    // If the image gets within 250px of the browser's viewport, 
    // start the download:
    rootMargin: '250px 0px',
  };

let lazyImageObserver = new IntersectionObserver(..., config);
```

### Lazy loading images drastically improves performance

After making these changes to my site, I did a new <https://webpagetest.org> benchmark run:

<div class="large">
  [image blog/webpagetest-images-february-2019-after]
</div>

You can clearly see that the page became a lot faster to render:

- The document is complete after 0.35 seconds (blue vertical line) instead of the original 7.275 seconds.
- No images are loaded before the document is complete, compared to 13 images being loaded before.
- After the document is complete, one image (purple horizontal bar) is downloaded. This is triggered by the JavaScript code as the result of one image being above the fold.

<p class="pullquote">Lazy loading images improves web page performance by reducing the number of HTTP requests, and consequently reduces the amount of data that needs to be downloaded to render the initial page.</p>

### Is base64 encoding images bad for SEO?

Faster sites have a SEO advantage as [page speed is a ranking factor for search engines](https://webmasters.googleblog.com/2018/01/using-page-speed-in-mobile-search.html). But, lazy loading might also be bad for SEO, as search engines have to be able to discover the original images.

To find out, I headed to [Google Search Console](https://search.google.com/search-console). Google Search Console has a "URL inspection" feature that allows you to look at a webpage through the eyes of Googlebot.

I tested it out [with my Acadia National Park](https://dri.es/our-vacation-at-acadia-national-park) blog post. As you can see in the screenshot, the first photo in the blog post was not loaded. Googlebot doesn't seem to support data URLs for images.

<div class="large">
  [image blog/google-search-console-live-preview]
</div>

### Is `IntersectionObserver` bad for SEO?

The fact that Googlebot doesn't appear to support data URLs does not have to be a problem. The real question is whether Googlebot will scroll the page, execute the JavaScript, replace the placeholders with the actual images, and index those. If it does, it doesn't matter that Googlebot doesn't understand data URLs.

To find out, I decided to conduct an experiment. For the experiment, I published a blog post about [Matt Mullenweg and me visiting a museum together](https://dri.es/two-internet-entrepreneurs-walk-into-an-old-publishing-house). The images in that blog post are lazy loaded and can only be discovered by Google if its crawler executes the JavaScript and scrolls the page. If those images show up in Google's index, we know there is no SEO impact.

I only posted that blog post yesterday. I'm not sure how long it takes for Google to make new posts and images available in its index, but [I'll keep an eye out for it](https://www.google.com/search?q=matt+mullenweg+dries+buytaert+plantin+moretus).

If the images don't show up in Google's index, lazy loading might impact your SEO. My solution would be to selectively disable lazy loading for the most important images only. (Note: even if Google finds the images, there is no guarantee that it will decide to index them – short blog posts and images are often excluded from Google's index.)

### Conclusions

Lazy loading images improves web page performance by reducing the number of HTTP requests and data needed to render the initial page.

Ideally, over time, browsers will support lazy loading images natively, and some of the SEO challenges will no longer be an issue. Until then, consider adding support for lazy loading yourself. For my own site, it took about 40 lines of JavaScript code and 20 lines of additional PHP/Drupal code.

I hope that by sharing my experience, more people are [encouraged to run their own sites](https://dri.es/taking-control-of-my-data-and-social-media) and to optimize their sites' performance.
