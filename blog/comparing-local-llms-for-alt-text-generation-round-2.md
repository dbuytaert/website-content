---
url: 'https://dri.es/comparing-local-llms-for-alt-text-generation-round-2'
title: 'Comparing local LLMs for alt-text generation, round 2'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-05-27T14:04:35-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Can local large language models (LLMs) generate accurate alt-text, or do cloud-based services still offer better results?'
tags:
  - 'Artificial Intelligence'
  - Alt-text
  - Accessibility
  - Python
image: japan-2024/shibuya-crossing
published: true
featured: false
id: 5816
---

# Comparing local LLMs for alt-text generation, round 2

Four months ago, I [tested 10 local vision LLMs](https://dri.es/comparing-local-llms-for-alt-text-generation) and compared them against the top cloud models. *Vision models* can analyze images and describe their content, making them useful for `alt`-text generation.

The result? The local models missed important details or introduced hallucinations. So [I switched to using cloud models](https://dri.es/automating-alt-text-generation-ai), which produced better results but meant sacrificing privacy and offline capability.

Two weeks ago, [Ollama](https://ollama.com/) released [version 0.7.0](https://github.com/ollama/ollama/releases/tag/v0.7.0) with improved support for vision models. They added support for three vision models I hadn't tested yet: [Mistral 3.1](https://huggingface.co/mistralai/Mistral-Small-3.1-24B-Instruct-2503), [Qwen 2.5 VL](https://huggingface.co/Qwen/Qwen2.5-VL-32B-Instruct) and [Gemma 3](https://huggingface.co/google/gemma-3-27b-it).

I decided to evaluate these models to see whether they've caught up to GPT-4 and Claude 3.5 in quality. Can local models now generate accurate and reliable `alt`-text?

<table>
  <thead>
  <tr>
  <th>Model</th>
  <th>Provider</th>
  <th>Release date</th>
  <th>Model size</th>
</tr>
</thead>
  <tbody>
  <tr>
  <td>
  <a href="https://huggingface.co/google/gemma-3-27b-it">Gemma 3 (27B)</a>
</td>
  <td>Google DeepMind</td>
  <td>March 2025</td>
  <td>27B</td>
</tr>
  <tr>
  <td>
  <a href="https://huggingface.co/Qwen/Qwen2.5-VL-32B-Instruct">Qwen 2.5 VL (32B)</a>
</td>
  <td>Alibaba</td>
  <td>March 2025</td>
  <td>32B</td>
</tr>
  <tr>
  <td>
  <a href="https://huggingface.co/mistralai/Mistral-Small-3.1-24B-Instruct-2503">Mistral 3.1 (24B)</a>
</td>
  <td>Mistral AI</td>
  <td>March 2025</td>
  <td>24B</td>
</tr>
</tbody>
</table>

### Updating my `alt`-text script

For my earlier experiments, I created [an open-source script](https://github.com/dbuytaert/image-caption) that generates `alt`-text descriptions. The script is a Python wrapper around [Simon Willison's `llm` tool](https://github.com/simonw/llm), which provides a unified interface to LLMs. It supports models from Ollama, Hugging Face and various cloud providers.

To test the new models, I added 3 new entries to my script's [`models.yaml`](https://github.com/dbuytaert/image-caption/blob/v2/models.yaml), which defines each model's prompt, temperature, and token settings. Once configured, generating `alt`-text is simple. Here is an example using the three new vision models:

```shell
$ ./caption.py test-images/image-1.jpg –model mistral-3.1-24b gemma3-27b qwen2.5vl-32b
```

Which outputs something like:

```shell
{
  "image": "test-images/image-1.jpg",
  "captions": {
    "mistral-3.1-24b": "A bustling intersection at night filled with pedestrians crossing in all directions."
    "gemma3-27b": "A high-angle view shows a crowded Tokyo street filled with pedestrians and brightly lit advertising billboards at night.",
    "qwen2.5vl-32b": "A bustling city intersection at night, crowded with people crossing the street, surrounded by tall buildings with bright, colorful billboards and advertisements.",
  }
}
```

### Evaluating the models

To keep the results consistent, I used the same test images and the same evaluation method as in [my earlier blog post](https://dri.es/comparing-local-llms-for-alt-text-generation#model-evaluation). The details results are in this [Google spreadsheet](https://docs.google.com/spreadsheets/d/1LttMys6cEkse6LrRZoznvDdvBiz_WkVyauNBFV2jIXg/edit).

Each `alt`-text was scored from 0 to 5 based on three criteria: how well it identified the most important elements in the image, how effectively it captured the mood or atmosphere, and whether it avoided repetition, grammar issues or hallucinated details. I then converted each score into a letter grade from A to F.

For comparison, the cloud models received the following scores: GPT-4o earned an average of 4.8 out of 5 (grade A), and Claude 3.5 Sonnet received a perfect 5 out of 5 (grade A).

#### Test image 1: Shibuya Crossing, Tokyo

<div class="large">
  [image japan-2024/shibuya-crossing caption=false]
</div>

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
  <td>Mistral 3.1 (24B)</td>
  <td>A bustling intersection at night filled with pedestrians crossing in all directions.</td>
  <td>C</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td>A high-angle view shows a crowded Tokyo <mark>street</mark> filled with pedestrians and brightly lit advertising billboards.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td>A bustling city intersection at night, crowded with people crossing the street, surrounded by brightly lit billboards and tall buildings.</td>
  <td>B</td>
</tr>
</tbody>
</table>

None earned an A because they failed to identify this as Shibuya Crossing in Tokyo, while cloud models do. Mistral also missed the billboards.

#### Test image 2: Isabella Stewart Gardner Museum, Boston

<div class="large">
  [image miscellaneous-2023/isabella-stewart-gardner-museum caption=false]
</div>

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
  <td>Mistral 3.1 (24B)</td>
  <td>An ornate wall features a large empty picture frame.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td>An empty, ornate gold frame hangs on a patterned green wall between two framed portraits and a candle sconce.</td>
  <td>A</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td>A vintage-style room features ornate wallpaper, a framed empty canvas, a lit candelabra, and a decorative vase on a table, with portraits on either side.</td>
  <td>A</td>
</tr>
</tbody>
</table>

The vision models in my previous post often mistook the empty frame for a framed painting. All three models in this test correctly identified it as empty. Gemma and Qwen captured valuable details about the scene, while Mistral's description felt sparse.

#### Test image 3: wakeboarding in Vermont, USA

<div class="large">
  [image vermont-2024/wakeboarding caption=false]
</div>

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
  <td>Mistral 3.1 (24B)</td>
  <td>Two shirtless men on a boat watch another person <mark>water skiing</mark> on a lake.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td>Two people on a boat watch a <mark>waterskier</mark> speeding across the lake on a sunny day.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td>Two shirtless men on a boat watch a person <mark>water skiing</mark> in the distance on a calm lake.</td>
  <td>B</td>
</tr>
</tbody>
</table>

All three described a wakeboarding scene as "water skiing", while the cloud models correctly identified it as wakeboarding.

#### Test image 4: hiking in the Dolomites, Italy

<div class="large">
  [image italy-2022/santa-maddalena-church-in-funes-2 caption=false]
</div>

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
  <td>Mistral 3.1 (24B)</td>
  <td>A wooden statue of a <mark>saint</mark> is mounted on a post with directional signs pointing to various locations.</td>
  <td>C</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td>A small wooden shrine with a statue of Mary stands beside a signpost indicating hiking trails in a grassy field.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td>A wooden shrine with a statue of <mark>a figure</mark> stands on a tree stump, surrounded by a scenic mountain landscape with directional signs in the foreground.</td>
  <td>B</td>
</tr>
</tbody>
</table>

Only Gemma recognized the statue as Mary. Both Mistral and Gemma missed the mountains in the background, which seems important.

#### Test image 5: backgammon by candlelight

<div class="large">
  [image vermont-2023/backgammon-by-candlelight caption=false]
</div>

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
  <td>Mistral 3.1 (24B)</td>
  <td>A lit candle and a glass of liquid are on a wooden table next to a wooden board game.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td>A lit candle and glass votive sit on a wooden table, creating a warm, inviting glow in a dimly lit space.</td>
  <td>B</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td>A cozy scene with a lit candle on a wooden table, next to a backgammon board and a glass of liquid, creating a warm and inviting atmosphere.</td>
  <td>A</td>
</tr>
</tbody>
</table>

Neither Mistral nor Gemma recognized the backgammon board. Only Qwen identified it correctly. Mistral also failed to capture the photo's mood.

<h3 id="model-accuracy">Model accuracy</h3>

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
  <td>Mistral 3.1 (24B)</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ffeb99">Fair</td>
  <td>3.4/5</td>
  <td>C</td>
</tr>
  <tr>
  <td>Gemma 3 (27B)</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ccffcc">Good</td>
  <td>4.2/5</td>
  <td>B</td>
</tr>
  <tr>
  <td>Qwen 2.5 VL (32B)</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ccffcc">Never</td>
  <td style="background-color: #ccffcc">Good</td>
  <td>4.4/5</td>
  <td>B</td>
</tr>
</table>
</div>

Qwen 2.5 VL performed best overall, with Gemma 3 not far behind.

Needless to say, these results are based on a small set of test images. And while I used a structured scoring system, the evaluation still involves subjective judgment. This is not a definitive ranking, but it's enough to draw some conclusions.

It was nice to say that all three LLMs avoided repetition and hallucinations, and generally captured the mood of the images.

Local models still make mistakes. All three described wakeboarding as "water skiing", most failed to recognize the statue as Mary or place the intersection in Japan. Cloud models get these details right, as I showed in [my previous blog post](https://dri.es/comparing-local-llms-for-alt-text-generation).

### Conclusion

I ran my original experiment four months ago, and at the time, none of the models I tested felt accurate enough for large-scale `alt`-text generation. Some, like Llama 3, showed promise but still fell short in overall quality.

Newer models like Qwen 2.5 VL and Gemma 3 have matched the performance I saw earlier with Llama 3. Both performed well in my latest test. They produced relevant, grounded descriptions without hallucinations or repetition, which earlier local models often struggled with.

Still, the quality is not yet at the level where I would trust these models to generate thousands of `alt`-texts without human review. They make more mistakes than GPT-4 or Claude 3.5.

My main question was: are local models now good enough for practical use? While Qwen 2.5 VL performed best overall, it still needs human review. I've started using it for small batches where manual checking is manageable. For large-scale, fully automated use, I continue using cloud models as they remain the most reliable option.

That said, local vision-language models continue to improve. My long-term goal is to return to a 100% local-first workflow that gives me more control and keeps my data private. While we're not there yet, these results show real progress.

My plan is to wait for the next generation of local vision models (or upgrade my hardware to run larger models). When those become available, I'll test them and report back.
