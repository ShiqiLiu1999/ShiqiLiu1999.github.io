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


Our objective is to support urban mining companies in estimating the transportation costs and greenhouse gas (GHG) emissions for both their standard and recycled processes, based on the total distance covered in miles and the amount of materials transported in tons.

To determine the transportation cost, we factor in various expenses such as fuel fee, tipping fee, landfilling and disposal costs, and truck rental charges. By adding these costs together, we can determine the transportation cost per ton of material.

In addition to transportation costs, we also calculate GHG emissions. To calculate GHG emissions, we multiply the amount of fuel used by 0.43, based on the estimate by the U.S. Environmental Protection Agency (EPA) that diesel fuel produces approximately 0.43 kg of CO2 emissions per liter. This calculation provides us with the average GHG emissions per ton of material.


## Calculator
<!-- <label for="input-box">Total Distance (Mile):</label>
<input type="text" id="input-box" name="name">

<label for="input-box">Amount of Material (Ton):</label>
<input type="text" id="input-box" name="name"> -->

<label for="input-box-dis">Total Distance (Mile):</label>
<input type="text" id="input-box-dis" name="number">
<button onclick="calculate_transp_cost()">Calculate Transp Cost</button> 
<p id="result_total_cost_standard"></p>

<label for="input-box-amt">Amount of Material (Ton):</label>
<input type="text" id="input-box-amt" name="number">
<button onclick="calculate_transp_cost()">Calculate Transp Cost</button>
<p id="result_total_cost_recycled"></p>

<script>
  function calculate_transp_cost() {
    // Get a reference to the input box
    const inputBox1 = document.getElementById("input-box-dis");
    const inputBox2 = document.getElementById("input-box-amt");

    // Retrieve the value of the input box
    const dis = inputBox1.value;
    const amt = inputBox2.value;

    // Process the input using a formula
    const total_transp_cost_standard = dis/4*3.4*Math.ceil(amt/22,0)+amt*12+amt*44+Math.ceil(amt/22,0)*(dis/30)*100;
    // const avg_transp_cost_standard = total_transp_cost_standard/amt;
    const total_transp_cost_recycled = dis/3.5*3.4*Math.ceil(amt/40,0)+amt*10+Math.ceil(amt/40,0)*dis/25*100;
    // const avg_total_transp_cost_recycled = total_transp_cost_recycled/amt

    // Output the result to the user

    const result_total_cost_standard = document.getElementById("result_total_cost_standard");
    result_total_cost_standard.textContent = `The total transportation cost in standard process is $${total_transp_cost_standard}.`;
    
    const result_total_cost_recycled = document.getElementById("result_total_cost_recycled");
    result_total_cost_recycled.textContent = `The total transportation cost in recycled process is $${total_transp_cost_recycled}.`;
  }

</script>


## Sensitivity Analysis (Jamaica Hospital Case)
