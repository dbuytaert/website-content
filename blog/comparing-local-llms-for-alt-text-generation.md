---
title: 'Comparing local large language models for alt-text generation'
date: '2025-02-03T11:45:10-05:00'
author: Dries
summary: 'I tested 12 LLMs – 10 running locally and 2 cloud-based – to assess their accuracy in generating alt-text for images.'
image: italy-2022/santa-maddalena-church-in-funes-2
tags:
  - Accessibility
  - 'Artificial Intelligence'
  - 'My site'
  - Alt-text
featured: true
published: true
type: blog
url: /comparing-local-llms-for-alt-text-generation
id: 5751
---

I have [10,000 photos](https://dri.es/photos) on my website. About 9,000 have no `alt`-text. I'm not proud of that, and it has bothered me for a long time.

When I started my blog nearly 20 years ago, I didn't think much about `alt`-texts. Over time, I realized its importance for visually impaired users who rely on screen readers.

The past 5+ years, I diligently added `alt`-text to every new image I uploaded. But that only covers about 1,000 images, leaving most older photos without descriptions.

Writing 9,000 `alt`-texts manually would take ages. Of course, AI could do this much faster, but is it good enough?

To see what AI can do, I tested 12 *Large Language Models* (LLMs): 10 running locally and 2 in the cloud. My goal was to test their accuracy and determine whether they can generate accurate `alt`-text.

The TL;DR is that, not surprisingly, cloud models (GPT-4, Claude Sonnet 3.5) set the benchmark with A-grade performance, though not 100% perfect. I prefer local models for privacy, cost, and offline use. Among local options, the Llama variants and MiniCPM-V perform best. Both earned a B grade: they work reliably but sometimes miss important details.

I know I'm not the only one. Plenty of people – entire organizations even – have massive backlogs of images without `alt`-text. I'm determined to fix that for my blog and share what I learn along the way. This blog post is just step one – [subscribe by email](https://buttondown.com/dries-buytaert-blog) or [RSS](https://dri.es/rss.xml) to get future posts.

### Models evaluated

I tested `alt`-text generation using 12 AI models: 9 on my MacBook Pro with 32GB RAM, 1 on a higher-RAM machine (thanks to Jeremy Andrews, a friend and long-time Drupal contributor), and 2 cloud-based services.

The table below lists the models I tested, with details like links to research papers, release dates, parameter sizes (in billions), memory requirements, some architectural details and more:

<div class="large">
  <table>
  <thead>
   <tr>
    <th></th>
    <th>Model</th>
    <th>Launch date</th>
    <th>Type</th>
    <th>Vision encoder</th>
    <th>Language encoder</th>
    <th>Model size (billions of parameters)</th>
    <th>RAM</th>
    <th>Deployment</th>
 </tr>
 </thead>
  <tbody>
   <tr>
    <td>1</td>
    <td>
     <a href="https://huggingface.co/nlpconnect/vit-gpt2-image-captioning">VIT-GPT2</a>
   </td>
    <td>2021</td>
    <td>Image-to-text</td>
    <td>ViT (Vision Transformer)</td>
    <td>GPT-2</td>
    <td>0.4B</td>
    <td>~8GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>2</td>
    <td>
     <a href="https://huggingface.co/microsoft/git-base">Microsoft GIT</a>
   </td>
    <td>2022</td>
    <td>Image-to-text</td>
    <td>Swin Transformer</td>
    <td>Transformer Decoder</td>
    <td>1.2B</td>
    <td>~8GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>3</td>
    <td>
     <a href="https://huggingface.co/Salesforce/blip-image-captioning-large">BLIP Large</a>
   </td>
    <td>2022</td>
    <td>Image-to-text</td>
    <td>ViT</td>
    <td>BERT</td>
    <td>0.5B</td>
    <td>~8GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>4</td>
    <td>
     <a href="https://huggingface.co/Salesforce/blip2-opt-2.7b">BLIP-2 OPT</a>
   </td>
    <td>2023</td>
    <td>Image-to-text</td>
    <td>CLIP ViT</td>
    <td>OPT</td>
    <td>2.7B</td>
    <td>~8GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>5</td>
    <td>
     <a href="https://huggingface.co/Salesforce/blip2-flan-t5-xl">BLIP-2 FLAN-T5</a>
   </td>
    <td>2023</td>
    <td>Image-to-text</td>
    <td>CLIP ViT</td>
    <td>FLAN-T5 XL</td>
    <td>3B</td>
    <td>~8GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>6</td>
    <td>
     <a href="https://ollama.com/library/minicpm-v">MiniCPM-V</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>SigLip-400M</td>
    <td>Qwen2-7B</td>
    <td>8B</td>
    <td>~16GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>7</td>
    <td>
     <a href="https://ollama.com/library/llava">LLaVA 13B</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>CLIP ViT</td>
    <td>Vicuna 13B</td>
    <td>13B</td>
    <td>~16GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>8</td>
    <td>
     <a href="https://ollama.com/library/llava">LLaVA 34B</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>CLIP ViT</td>
    <td>Vicuna 34B</td>
    <td>34B</td>
    <td>~32GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>9</td>
    <td>
     <a href="https://ollama.com/library/llama3.2-vision">Llama 3.2 Vision 11B</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>Custom Vision Encoder</td>
    <td>Llama 3.2</td>
    <td>11B</td>
    <td>~20GB</td>
    <td>Local, Dries</td>
 </tr>
   <tr>
    <td>10</td>
    <td>
     <a href="https://ollama.com/library/llama3.2-vision">Llama 3.2 Vision 90B</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>Custom Vision Encoder</td>
    <td>Llama 3.2</td>
    <td>90B</td>
    <td>~128GB</td>
    <td>Local, Jeremy</td>
 </tr>
   <tr>
    <td>11</td>
    <td>
     <a href="https://chat.openai.com">OpenAI GPT-4o</a>
   </td>
    <td>2023</td>
    <td>Multi-modal</td>
    <td>Custom Vision Encoder</td>
    <td>GPT-4</td>
    <td>&gt;150B</td>
    <td>
   </td>
    <td>Cloud</td>
 </tr>
   <tr>
    <td>12</td>
    <td>
     <a href="https://claude.ai">Anthropic Claude 3.5 Sonnet</a>
   </td>
    <td>2024</td>
    <td>Multi-modal</td>
    <td>Custom Vision Encoder</td>
    <td>Claude 3.5</td>
    <td>&gt;150B</td>
    <td>
   </td>
    <td>Cloud</td>
 </tr>
 </tbody>
</table>
</div>

### How image-to-text models work (in less than 30 seconds)

LLMs come in many forms, but for this project, I focused on *image-to-text* and *multi-modal* models. Both types of models can analyze images and generate text, either by describing images or answering questions about them.

Image-to-text models follow a two-step process: **vision encoding** and **language decoding**:

1. **Vision encoding**: First, the model breaks an image down into *patches*. You can think of these as "puzzle pieces". The patches are converted into mathematical representations called *embeddings*, which summarize their visual details. Next, an [attention mechanism](https://en.wikipedia.org/wiki/Attention_(machine_learning)) filters out the most important patches (e.g. the puzzle pieces with the cat's outline or fur texture) and eliminates less relevant details (e.g. puzzle pieces with plain blue skies).
2. **Language encoding**: Once the model has summarized the most important visual features, it uses a *language model* to translate those features into words. This step is where the actual text (image captions or Q&amp;A answers) is generated.

In short, the vision encoder *sees* the image, while the language encoder *describes* it.

If you look at the table above, you'll see that each row pairs a *vision encoder* (e.g., ViT, CLIP, Swin) with a *language encoder* (e.g., GPT-2, BERT, T5, Llama).

For a more in-depth explanation, I recommend [Sebastian Raschka](https://sebastianraschka.com/)'s article [Understanding Multi-modal LLMs](https://sebastianraschka.com/blog/2024/understanding-multimodal-llms.html), which also covers how image encoders work. It's fantastic!

### Comparing different AI models

I wrote a Python script that generates `alt`-texts for images using nine different local models. You can find it in my [GitHub repository](https://github.com/dbuytaert/image-caption). It takes care of installing models, running them, and generating `alt`-texts. It supports both [Hugging Face](https://huggingface.co/) and [Ollama](https://ollama.ai/) and is built to be easily extended as new models come out.

You can run the script as follows:

```shell
$ ./caption.py ./test-images/image-1.jpg
```

The first time you run the script, it will download all models, which requires significant disk space and bandwidth – expect to download over 50GB of model data.

The script outputs a JSON response, making it easy to integrate or analyze programmatically. Here is an example output:

<pre>
  <code class="language-json">{
  "image": "test-images/image-1.jpg",
  "<code>alt</code>-texts": {
  "vit-gpt2": "A city at night with skyscrapers and a traffic light on the side of the street in front of a tall building.",
  "git": "A busy city street is lit up at night, with the word qroi on the right side of the sign.",
  "blip": "This is an aerial view of a busy city street at night with lots of people walking and cars on the side of the road.",
  "blip2-opt": "An aerial view of a busy city street at night.",
  "blip2-flan": "An aerial view of a busy street in tokyo, japanese city at night with large billboards.",
  "minicpm-v": "A bustling cityscape at night with illuminated billboards and advertisements, including one for Michael Kors.",
  "llava-13b": "A bustling nighttime scene from Tokyo's famous Shibuya Crossing, characterized by its bright lights and dense crowds of people moving through the intersection.",
  "llava-34b": "A bustling city street at night, filled with illuminated buildings and numerous pedestrians.",
  "llama32-vision-11b": "A bustling city street at night, with towering skyscrapers and neon lights illuminating the scene."
  }
  }
</code>
</pre>

### Test images

With the script ready, I decided to test it on some of [my 10,000 photos](https://dri.es/photos). Not all of them at once. I picked five that I consider non-standard. Instead of simple portraits or landscapes, I picked photos with elements that might confuse or challenge the models.

One photo is from the [Isabella Stewart Gardner Museum](https://en.wikipedia.org/wiki/Isabella_Stewart_Gardner_Museum_theft) in Boston and features an empty gold frame. The frame once held a masterpiece stolen in the infamous 1990 heist, one of the biggest art thefts in history. I wanted to see if the models would recognize it as empty or mistake it for a framed painting.

Another photo, taken last summer in Vermont, shows a wakeboarder. Though he is the main subject, he is relatively small in the frame. I was curious to see if the models could still recognize him as the focal point.

In another photo, a backgammon game is set in a dark but cozy atmosphere. I was curious to see if the models could recognize partially visible objects and capture the mood of the scene.

To ensure a fair test, I stripped all [EXIF metadata](https://en.wikipedia.org/wiki/Exif) from the images. This includes any embedded captions, GPS coordinates, or other details that could inadvertently help the models.

Yes, I *know* that a test set of five images is small, but it's sufficient to identify the top models for further evaluation. With 12 models generating `alt`-texts for each photo, I had to [manually evaluate 60 `alt`-texts](https://docs.google.com/spreadsheets/d/1LttMys6cEkse6LrRZoznvDdvBiz_WkVyauNBFV2jIXg/edit), which was tedious to do fairly and accurately. For now, these five images are enough to filter out weaker models and pinpoint the best 2-3 LLMs for more detailed testing.

Next, I'll share the detailed results for each of the five photos. It's a lot to go through, so feel free to skip ahead to the [summary](#model-accuracy).

#### Test image 1: Shibuya Crossing, Tokyo

<div class="large">
  [image japan-2024/shibuya-crossing caption=false]
</div>

Benchmark LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>GPT-4o</td>
   <td>A vibrant city intersection with crowds crossing, surrounded by illuminated billboards and towering buildings, likely Shibuya, Tokyo.</td>
   <td>A</td>
 </tr>
  <tr>
   <td>Claude</td>
   <td>Hundreds of people cross Tokyo's famous Shibuya intersection as neon signs light up the surrounding skyscrapers.</td>
   <td>A</td>
 </tr>
</tbody>
</table>

Local LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>VIT-GPT2</td>
   <td>A city at night with skyscrapers and a <mark>traffic light</mark> on the side of the street in front of a tall <mark>building</mark>.</td>
   <td>F</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td>A busy city street is lit up at night, with the word <mark>qroi</mark> on the right side of the sign.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>BLIP</td>
   <td>This is an aerial view of a busy city street at night with lots of people walking and cars on the side of the road.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP-2 with OPT</td>
   <td>An aerial view of a busy city street at night.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>BLIP-2 with FLAN</td>
   <td>An aerial view of a busy street in <mark>Tokyo, Japanese city</mark> at night with large billboards.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>LLaVA (13B)</td>
   <td>A bustling nighttime scene of Tokyo's Shibuya Crossing, with neon lights and people walking across the intersection.</td>
   <td>A</td>
 </tr>
  <tr>
   <td>LLaVA (34B)</td>
   <td>A bustling city street at night, with illuminated buildings and numerous pedestrians.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>MiniCPM-V</td>
   <td>A bustling cityscape at night with various advertisements, including one for Michael Kors and another for Yakult.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>Llama 3.2 Vision (11B)</td>
   <td>A bustling city street at night, with numerous billboards and advertisements lining the buildings.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>Llama 3.2 Vision (90B)</td>
   <td>A bustling city street with many people and buildings.</td>
   <td>D</td>
 </tr>
</tbody>
</table>

#### Test image 2: Isabella Stewart Gardner Museum, Boston

<div class="large">
  [image miscellaneous-2023/isabella-stewart-gardner-museum caption=false]
</div>

Benchmark LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>GPT-4o</td>
   <td>
    <mark>Elegant</mark> wallpaper, an empty gold frame, candelabra, and framed painting in a classic room.</td>
    <td>B</td>
 </tr>
   <tr>
    <td>Claude</td>
    <td>Ornate Victorian room with damask wallpaper, candelabra, and gold frames on wall.</td>
    <td>B</td>
 </tr>
 </tbody>
</table>

Local LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>VIT-GPT2</td>
   <td>A living room with a <mark>mirror</mark>, candles, and a vase of <mark>flowers</mark> on a table in front of a <mark>mirror</mark>.</td>
   <td>F</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td>A picture frame is hanging on a wall next to a vase <mark>and a vase</mark> with <mark>the word tulips on it</mark>.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>BLIP</td>
   <td>A room with a painting on the wall and <mark>two vases</mark> on the table in front of it.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>BLIP-2 with OPT</td>
   <td>A room with a painting on the wall, a picture frame, and a chandelier.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>BLIP-2 with FLAN</td>
   <td>A room with a <mark>painting</mark> on the wall and a couple of framed pictures hanging on the wall next to it.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>LLaVA (13B)</td>
   <td>An <mark>empty</mark> wall with ornate decorations, including candlesticks and framed artwork, suggesting a formal or historical setting.
 </td>
  <td>D</td>
</tr>
  <tr>
  <td>LLaVA (34B)</td>
  <td>An ornate room with framed pictures on the wall, a chandelier <mark>hanging from the ceiling</mark>, and a <mark>fireplace mantel</mark> adorned with decorative items.</td>
  <td>E</td>
</tr>
  <tr>
  <td>MiniCPM-V</td>
  <td>A room with ornate wallpaper, candlesticks and framed portraits of historical figures is displayed.</td>
  <td>
 </td>
</tr>
  <tr>
  <td>Llama 3.2 Vision (11B)</td>
  <td>An empty gold frame on a wall with ornate wallpaper, surrounded by other decorative items.</td>
  <td>A</td>
</tr>
  <tr>
  <td>Llama 3.2 Vision (90B)</td>
  <td>An ornate room with a gold frame, a painting of a man, and a vase on a <mark>table</mark>.</td>
  <td>B</td>
</tr>
</tbody>
</table>

#### Test image 3: wakeboarding in Vermont, USA

<div class="large">
  [image vermont-2024/wakeboarding caption=false]
</div>

Benchmark LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>GPT-4o</td>
   <td>Two shirtless boys on a boat watch a person wakeboarding in the distance on a cloudy day.</td>
   <td>A</td>
 </tr>
  <tr>
   <td>Claude</td>
   <td>People watching from a boat as a person is wakeboarding on a lake with a wooded shoreline.</td>
   <td>B</td>
 </tr>
</tbody>
</table>

Local LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>VIT-GPT2</td>
   <td>A man standing on top of a boat next to another man <mark>holding a surfboard in one hand</mark> and <mark>a surfboard in the other</mark>.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td>Two men are in a boat, one of them is wearing an orange hat <mark>and the other is wearing an orange hat</mark>.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP</td>
   <td>There are two men riding on the back of a boat in the water, <mark>one of them is on a surfboard and the other is on a board</mark>.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP-2 with OPT</td>
   <td>
    <mark>Three young men</mark> sitting on the back of a boat.</td>
    <td>D</td>
 </tr>
   <tr>
    <td>BLIP-2 with FLAN</td>
    <td>
     <mark>A group of people</mark> sitting on a boat watching a man ride a <mark>surfboard</mark> in the middle of the water.</td>
     <td>C</td>
   </tr>
    <tr>
     <td>LLaVA (13B)</td>
     <td>Two shirtless men on a boat, watching another man <mark>surfing</mark> in the water.</td>
     <td>B</td>
   </tr>
    <tr>
     <td>LLaVA (34B)</td>
     <td>Two shirtless men on a boat, watching another person <mark>water skiing</mark>.</td>
     <td>B</td>
   </tr>
    <tr>
     <td>MiniCPM-V</td>
     <td>Two shirtless men on a boat watch as another person <mark>water skis away from them</mark>, with trees and sky visible across the lake behind him.</td>
     <td>B</td>
   </tr>
    <tr>
     <td>Llama 3.2 Vision (11B)</td>
     <td>Two shirtless men on a boat watching <mark>people</mark> wakeboarding or <mark>surfing</mark> behind it.</td>
     <td>B</td>
   </tr>
    <tr>
     <td>Llama 3.2 Vision (90B)</td>
     <td>Two men on a boat watching another man wakeboarding.</td>
     <td>A</td>
   </tr>
 </tbody>
 </table>

#### Test image 4: hiking in the Dolomites, Italy

<div class="large">
  [image italy-2022/santa-maddalena-church-in-funes-2 caption=false]
</div>

Benchmark LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>GPT-4o</td>
   <td>A wooden shrine with a statue of Mary and directional signs, set against mountains and green hills.</td>
   <td>A</td>
 </tr>
  <tr>
   <td>Claude</td>
   <td>Wooden shrine of St. Magdalena with trail signs in the Dolomites mountains of Italy.</td>
   <td>A</td>
 </tr>
</tbody>
</table>

Local LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>VIT-GPT2</td>
   <td>A <mark>bird</mark> perched on top of a wooden post in front of a mountain range with a view of <mark>a mountain range and mountains</mark>.</td>
   <td>F</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td>A <mark>wooden sign</mark> in front of a mountain with a statue on it that says <mark>"Meise museum"</mark> on the top.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP</td>
   <td>There is <mark>a birdhouse with a statue</mark> on top of it in the middle of a field with trees and mountains in the background.</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP-2 with OPT</td>
   <td>A statue of Mary on a wooden post in the middle of a field with mountains in the background.</td>
   <td>B</td>
 </tr>
  <tr>
   <td>BLIP-2 with FLAN</td>
   <td>A statue of the Virgin Mary sits on top of a wooden post <mark>in the middle of a mountain</mark>.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>LLaVA (13B)</td>
   <td>A picturesque scene of a small wooden chapel with a statue of <mark>Jesus</mark>, set against a backdrop of majestic mountains and lush greenery.</td>
   <td>C</td>
 </tr>
  <tr>
   <td>LLaVA (34B)</td>
   <td>A wooden shrine with religious iconography, surrounded by alpine scenery and signposts.</td>
   <td>B</td>
 </tr>
  <tr>
   <td>MiniCPM-V</td>
   <td>A wooden shrine with a statue of Mary and several directional signs pointing to various locations such as Kirchsteig, Magdalena, St.</td>
   <td>B</td>
 </tr>
  <tr>
   <td>Llama 3.2 Vision (11B)</td>
   <td>A wooden shrine with a statue of Mary and a signpost in front of mountains.</td>
   <td>A</td>
 </tr>
  <tr>
   <td>Llama 3.2 Vision (90B)</td>
   <td>A statue of Mary in a wooden shrine with a signpost pointing to various locations, including Rundweg St.</td>
   <td>B</td>
 </tr>
</tbody>
</table>

#### Test image 5: backgammon by candlelight

<div class="large">
  [image vermont-2023/backgammon-by-candlelight caption=false]
</div>

Benchmark LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>GPT-4o</td>
   <td>A cozy, dimly lit room with <mark>a candle</mark> on a wooden table, next to a backgammon board, creating a warm, rustic ambiance.
 </td>
  <td>B</td>
</tr>
  <tr>
  <td>Claude</td>
  <td>Two candles light up a game board for backgammon on a wooden table at night.</td>
  <td>A</td>
</tr>
</tbody>
</table>

Local LLMs:

<table>
  <thead>
  <tr>
   <th>Model</th>
   <th>Description</th>
   <th>Grade</th>
 </tr>
</thead>
  <tbody>
  <tr>
   <td>VIT-GPT2</td>
   <td>A candle is lit on a wooden table in front of a <mark>fire place</mark> with candles and other items on top of it.</td>
   <td>E</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td>Two candles are lit next to each other on a table, <mark>one of them is lit up and the other is lit up</mark>.
 </td>
  <td>D</td>
</tr>
  <tr>
  <td>BLIP</td>
  <td>There is a lit <mark>candle</mark> sitting on top of a wooden table next to a game board and <mark>a glass of wine</mark> on the table.
</td>
  <td>D</td>
</tr>
<tr>
  <td>BLIP-2 with OPT</td>
  <td>A candle sits on top of a wooden table.</td>
  <td>C</td>
</tr>
<tr>
  <td>BLIP-2 with FLAN</td>
  <td>A candle sits on a wooden table next to a backgammon board and a <mark>glass of wine</mark>.</td>
  <td>D</td>
</tr>
<tr>
  <td>LLaVA (13B)</td>
  <td>A cozy indoor setting with candles, <mark>a guitar</mark>, and a warm ambiance.</td>
  <td>D</td>
</tr>
<tr>
  <td>LLaVA (34B)</td>
  <td>A candlelit wooden table with <mark>musical instruments</mark> and a cozy ambiance.</td>
  <td>C</td>
</tr>
<tr>
  <td>MiniCPM-V</td>
  <td>A dimly lit room with candles and backgammon pieces on a wooden table, creating an atmosphere of relaxation or leisure activity.</td>
  <td>A</td>
</tr>
<tr>
  <td>Llama 3.2 Vision (11B)</td>
  <td>A dimly lit room with a wooden table, featuring a backgammon board and two candles.
</td>
<td>A</td>
</tr>
<tr>
  <td>Llama 3.2 Vision (90B)</td>
  <td>A candle and backgammon board on a wooden table.
</td>
<td>B</td>
</tr>
</tbody>
</table>

<h3 id="model-accuracy">Model accuracy</h3>

I evaluated each description using [a structured but subjective scoring system](https://docs.google.com/spreadsheets/d/1LttMys6cEkse6LrRZoznvDdvBiz_WkVyauNBFV2jIXg/edit). For each image, I identified the two or three most important objects the AI should recognize and include in its description. I also assessed whether the model captured the photo's mood, which can be important for visually impaired users. Finally, I deducted points for repetition, grammar errors, or hallucinations (invented details). Each `alt`-text received a score from 0 to 5, which I then converted to a letter grade from A to F.

<div class="large">
  <table>
  <tr>
   <th>Model</th>
   <th>Repetitions</th>
   <th>Hallucinations</th>
   <th>Moods</th>
   <th>Average score</th>
   <th>Grade</th>
 </tr>
  <tr>
   <td>VIT-GPT2</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Poor</td>
   <td>0.4/5</td>
   <td>F</td>
 </tr>
  <tr>
   <td>GIT</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Poor</td>
   <td>1.6/5</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Often</td>
   <td style="background-color: #ffcccc">Poor</td>
   <td>1.8/5</td>
   <td>D</td>
 </tr>
  <tr>
   <td>BLIP2 w/OPT</td>
   <td style="background-color: #ccffcc">Rarely</td>
   <td style="background-color: #ffeb99">Sometimes</td>
   <td style="background-color: #ffeb99">Fair</td>
   <td>2.6/5</td>
   <td>C</td>
 </tr>
  <tr>
   <td>BLIP2 w/FLAN</td>
   <td style="background-color: #ccffcc">Rarely</td>
   <td style="background-color: #ffeb99">Sometimes</td>
   <td style="background-color: #ffeb99">Fair</td>
   <td>2.2/5</td>
   <td>D</td>
 </tr>
  <tr>
   <td>LLaVA 13B</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ffeb99">Sometimes</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>3.2/5</td>
   <td>C</td>
 </tr>
  <tr>
   <td>LLaVA 34B</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ffeb99">Sometimes</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>3.2/5</td>
   <td>C</td>
 </tr>
  <tr>
   <td>MiniCPM-V</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>3.8/5</td>
   <td>B</td>
 </tr>
  <tr>
   <td>Llama 11B</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Rarely</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>4.4/5</td>
   <td>B</td>
 </tr>
  <tr>
   <td>Llama 90B</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Rarely</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>3.8/5</td>
   <td>B</td>
 </tr>
  <tr>
   <td>GPT-4o</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>4.8/5</td>
   <td>A</td>
 </tr>
  <tr>
   <td>Claude 3.5 Sonnet</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Never</td>
   <td style="background-color: #ccffcc">Good</td>
   <td>5/5</td>
   <td>A</td>
 </tr>
</table>
</div>

The cloud-based models, GPT-4o and Claude 3.5 Sonnet, performed nearly perfectly on my small test of five images, with no major errors, hallucinations, repetitions and excellent mood detection.

Among local models, both Llama variants and MiniCPM-V show the strongest performance.

Repetition in descriptions frustrates users of screen readers. Early models like VIT-GPT2, GIT, BLIP, and BLIP2 frequently repeat content, making them unsuitable.

Hallucinations can be a serious issue in my opinion. Describing nonexistent objects or actions misleads visually impaired users and erodes trust. Among the best-performing local models, MiniCPM-V did not hallucinate, while Llama 11B and Llama 90B each made one mistake. Llama 90B misidentified a cabinet at the museum as a table, and Llama 11B described multiple people wakeboarding instead of just one. While these errors aren't dramatic, they are still frustrating.

Capturing mood is essential for giving visually impaired users a richer understanding of images. While early models struggled in this area, all recent models all performed well. This includes both LLaVA variants and MiniCPM-V.

From a practical standpoint, Llama 11B and MiniCPM-V ran smoothly on my 32GB RAM laptop, but Llama 90B needed more memory. Long story short, this means that Llama 11B and MiniCPM-V are my best candidates for additional testing.

### Possible next steps

The results raise a tough question: is a "B"-level `alt`-text better than none at all? Many human-written `alt`-texts probably aren't perfect either. Should I wait for local models to hit an "A"-grade, or is an imperfect description still better than no `alt`-text at all?

Here are four possible next steps:

1. **Combine AI outputs** – Run the same image through different models and merge their results to try and create more accurate descriptions.
2. **Wait and upgrade** – Use the best local model for now, tag AI-generated `alt`-texts in the database, and refresh them in 6–12 months when new and better local models are available.
3. **Go cloud-based** – Get the best quality with a cloud model, even if it means uploading 65GB of photos. I can't explain why, or if the feeling is even justified, but it feels like giving in.
4. **Hybrid approach** – Use AI to generate `alt`-texts but review them manually. With 9,000 images, that is not practical. I'd need a way to flag `alt`-texts most likely to be wrong. Can LLMs give me a reliably confidence score?

Each option comes with trade-offs. Some options are quick but imperfect, others take work but might be worth it. Going cloud-based is the easiest but it feels like giving in. Waiting for better models is effortless but means delaying progress. Merging AI outputs or assigning a confidence score takes more effort but might be the best balance of speed and accuracy.

Maybe the solution is a combination of these options? I could go cloud-based now, tag the AI-generated `alt`-texts in my database, and regenerate them in 6–12 months when LLMs got even better.

It also comes down to pragmatism versus principle. Should I stick to local models because I believe in data privacy and Open Source, or should I prioritize accessibility by providing the best possible `alt`-text for users? The local-first approach better aligns with my values, but it might come at the cost of a worse experience for visually impaired users.

I'll be weighing these options over the next few weeks. What would you do? I'd love to hear your thoughts!

**Update:** My thoughts on using AI for `alt`-text has evolved across several blog posts. First, I [chose a cloud-based LLM](https://dri.es/i-want-to-run-ai-locally-here-is-why-i-am-not-yet) after all. Then, I [built an automated system](https://dri.es/automating-alt-text-generation-ai) to generate and update descriptions for just one image. Finally, I [scaled it to 9,000 images](https://dri.es/trusting-ai-with-my-images-was-not-easy) and learned to trust AI in the process.
