---
layout: post
title:  "Urban Mining and the CDW Circular Economy"
date:   2023-05-09
categories: jekyll update
toc: true
img-url: 2023-05-09-Urban-Mining-and-the-CDW-Circular-Economy\
---

## Background

Urban mining is the process of recovering valuable resources from electronic waste, construction and demolition waste, and other types of urban waste. It is an important concept in the circular economy, which aims to reduce waste, conserve resources, and promote sustainable development. The circular economy seeks to move away from the traditional "take-make-dispose" linear model of production and consumption, and towards a more sustainable model that prioritizes the reuse, recycling, and repurposing of materials.

Construction and demolition waste (CDW) is a significant source of urban waste, accounting for about one-third of all waste generated in the European Union, for example. CDW includes materials such as concrete, bricks, wood, metals, glass, and plastics, which are often disposed of in landfills or incinerated, leading to environmental problems such as pollution, greenhouse gas emissions, and resource depletion.

The CDW circular economy seeks to address these issues by promoting the recovery, reuse, and recycling of CDW materials. This involves designing buildings and infrastructure for disassembly and recovery, creating markets for recycled materials, promoting deconstruction rather than demolition, and improving the efficiency of waste management systems. By adopting a circular economy approach to CDW, we can reduce waste, conserve resources, and create new economic opportunities, while also reducing environmental impacts and improving sustainability.

<div class="blog-only-image">
    <img src="{{ site.blog-img-url }}{{ page.img-url }}Constructions.png">
</div>




## Introduction

In this paper, the author manage to Destory the data by diffusion, and then learn a reverse diffusion process that restores structure in data,
yielding a highly flexible and tractable generative model of the data.


<!-- <label for="input-box">Total Distance (Mile):</label>
<input type="text" id="input-box" name="name">

<label for="input-box">Amount of Material (Ton):</label>
<input type="text" id="input-box" name="name"> -->

<label for="input-box">Total Distance (Mile):</label>
<input type="text" id="input-box-distance" name="number">
<button onclick="calculate_transp_cost()">Calculate Transp Cost</button>
<p id="result"></p>

<label for="input-box">Amount of Material (Ton):</label>
<input type="text" id="input-box-amt" name="number">
<button onclick="calculate_transp_cost()">Calculate Transp Cost</button>
<p id="result"></p>

<script>
  function calculate_transp_cost() {
    // Get a reference to the input box
    const inputBox1 = document.getElementById("input-box-distance");
    const inputBox2 = document.getElementById("input-box-distance");

    // Retrieve the value of the input box
    const dis = inputBox1.value;
    const amt = inputBox2.value;

    // Process the input using a formula
    const total_transp_cost_standard = dis/4*3.4*Math.ceil(amt/22,0)+amt*12+amt*44+Math.ceil(amt/22,0)*(dis/30)*100;
    // const avg_transp_cost_standard = total_transp_cost_standard/amt;
    // const total_transp_cost_recycled = dis/3.5*3.4*Math.ceil(amt/40,0)+amt*10+Math.ceil(amt/40,0)*dis/25*100;
    // const avg_total_transp_cost_recycled = total_transp_cost_recycled/amt

    // Output the result to the user
    const result_total_cost_standard = document.getElementById("total_transp_cost_standard");
    resultBox.textContent = `The total transportation cost in standard process is ${result_total_cost_standard}.`;
  }
</script>



### 2.3 Hierarchical Text-Conditional Image Generation with CLIP Latents (2022)
This is a paper for the well-known OpenAI project "DALL-E2". Even though the we don't know what model "Midjourney" is using, we can fairly predict that they are
using the similar model like "DALL-E2" because the input and output of them are similar.

The following is the architacture of the "DALL-E2" model.

<div class="blog-only-image">
    <img src="{{ site.blog-img-url }}{{ page.img-url }}2-3-1.png">
</div>

<div class="blog-quote">
    “A high-level overview of unCLIP. Above the dotted line, we depict the CLIP training process,
through which we learn a joint representation space for text and images. Below the dotted line, we depict our
text-to-image generation process: a CLIP text embedding is first fed to an autoregressive or diffusion prior
to produce an image embedding, and then this embedding is used to condition a diffusion decoder which
produces a final image. Note that the CLIP model is frozen during training of the prior and decoder”
</div>

My study will only focus on the diffusion model part base on the DDPM paper.

<br/>
## 3.Derivation of Diffusion Model

In this section, I will follow the idea of the DDPM paper and do the derivation of the diffusion model untill we get the final loss function.

