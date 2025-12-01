---
title: 'Analyzing my photography history'
date: '2022-06-13T04:49:51-04:00'
author: Dries
summary: 'How I programmatically parse EXIF data to analyze my photography behavior and history.'
image: blog/camera-history-2000-to-2022
tags:
  - Photography
  - 'My site'
published: true
type: blog
url: /analyzing-my-photography-history
id: 5341
---

[image miscellaneous-2022/hello]

I have over 10,000 photos on my website. All these photos are managed by a custom [Drupal](https://www.drupal.org/) module. I wrote the first version of that module over 15 years ago, and continue to work on it from time to time. Like this weekend, when I added a new feature.

Digital photos have [EXIF data](https://en.wikipedia.org/wiki/Exif) embedded in them. EXIF data includes information such as camera model, lens, aperture, shutter speed, focal length, ISO, and much more.

My module now extracts the [EXIF data](https://en.wikipedia.org/wiki/Exif) from my photos and stores it in a database. Having all my EXIF metadata in a database allows me to analyze my photography history.

For example, over the years, I've owned 11 different cameras and 10 different lenses:

```sql
SELECT COUNT(DISTINCT(camera)) AS count FROM images; 
+-------+
| count |
+-------+
|    11 |
+-------+

SELECT COUNT(DISTINCT(lens)) AS count FROM images;  
+-------+
| count |
+-------+
|    10 |
+-------+
```

Here is a SQL query that shows all cameras I have owned in the last 22 years, and the timeframe I used them for.

```sql
SELECT camera, MIN(DATE(date)) AS first, MAX(DATE(date)) AS last, TIMESTAMPDIFF(YEAR, MIN(date), MAX(date)) AS years FROM images GROUP BY camera ORDER BY first; 
+---------------------+------------+------------+-------+
| camera              | first      | last       | years |
+---------------------+------------+------------+-------+
| Sony Cybershot      | 2000-01-01 | 2003-08-01 |     3 |
| Nikon Coolpix 885   | 2001-11-13 | 2004-04-11 |     2 |
| Nikon D70           | 2004-04-03 | 2006-11-19 |     2 |
| Nikon D200          | 2006-12-31 | 2012-06-17 |     5 |
| Panasonic Lumix GF1 | 2011-10-11 | 2014-10-26 |     3 |
| Nikon D4            | 2012-07-01 | 2018-08-26 |     6 |
| Sony Alpha 7 II     | 2015-02-25 | 2019-01-09 |     3 |
| DJI Mavic Pro       | 2017-07-23 | 2019-01-18 |     1 |
| Nikon D850          | 2019-03-16 | 2021-04-24 |     2 |
| Nikon Z 7           | 2019-04-07 | 2021-08-31 |     2 |
| Leica M10-R         | 2021-11-18 | 2022-06-09 |     0 |
+---------------------+------------+------------+-------+
```

Finally, here is a chart that visualizes my camera history:

<div class="large">
  [image blog/camera-history-2000-to-2022 resize=false]
</div>

A few takeaways:

- I used my Nikon D4 for 6 years and my Nikon D200 for 5 years. On average, I use a camera for 3.3 years.
- I should dust of my drone (DJI Mavic Pro) as I haven't used it since early 2019.
- In 2019, I bought a Nikon D850 and a Nikon Z 7. I liked the Nikon Z 7 better, and didn't use my Nikon D850 much.
- Since the end of 2021, I've been exclusively using [my Leica](https://dri.es/photography-as-meditation).

I shared this with my family but they weren't impressed. Blank stares ensued, and the conversation took a quick turn. While I could go on and share more statistics, I'll take a hint from my family, and stop here.
