---
layout: post
title:  "Urban Mining and the CDW Circular Economy"
date:   2023-05-09
categories: jekyll update
toc: true
img-url: 2023-05-09-Urban-Mining-and-the-CDW-Circular-Economy\
---

## Background

Urban mining is the process of recovering valuable resources from what is considered waste, such as construction and demolition waste (CDW). It is an important concept that supports creation of a circular economy, which aims to reduce waste, conserve resources, and promote sustainable development. The circular economy seeks to move away from the traditional “take-make-dispose” linear model of production and consumption, and towards a more sustainable model that prioritizes the reuse, recycling, and repurposing of materials.

CDW is a significant source of urban waste, estimated in New York State to account for 46% of the State’s total waste stream (Draft New York State Solid Waste Management Plan, pp. 9, 20, at <a href="https://www.dec.ny.gov/docs/materials_minerals_pdf/draftsswmp.pdf">https://www.dec.ny.gov/docs/materials_minerals_pdf/draftsswmp.pdf)</a>) CDW includes materials such as excavated soil, concrete, bricks, wood, metals and
glass, much of which are often disposed of in landfills.

New York State’s Part 360 beneficial use designation (BUD) regulations aim to divert these materials from landfills toward direct re-use or toward processing for re-use in new construction materials. The State’s BUDs support the creation of a CDW circular economy using the urban mining concept to support the recovery, reuse, and recycling of CDW materials. Other mechanisms to support a circular CDW economy would involve designing buildings and infrastructure for disassembly and recovery, creating markets for recycled materials, promoting deconstruction rather than demolition, and improving the efficiency of waste management systems. By adopting a circular economy approach to CDW, we can reduce waste, conserve resources, and create new economic opportunities, while also reducing environmental impacts and improving sustainability.

<div class="blog-only-image" style="margin-bottom: 20px;">
    <img src="{{ site.blog-img-url }}{{ page.img-url }}Constructions.png">
</div>


## Introduction


Our objective is to develop a model that permits comparison of direct cost (primarily transportation related) and GHG emissions savings from local processing and local reuse of CDW materials (the recycled process) to the direct costs and GHG emissions of sending these materials to landfills (the standard process). We based the model on a hypothetical excavation in Jamaica Queens, with the excavated soil transported to a Long Island rock wash plant that produced clean sand for use in new concrete at a nearby batch concrete plant. The model we developed permits a comparison between the hypothetical local recovery and reuse of excavated soil and the standard process of sending the excavated soil to Pennsylvania, where many landfills take CDW from New
York..

The model for the hypothetical case study (<a href="https://docs.google.com/spreadsheets/d/1439GZQQ7Zko0tlztk9GlA12wQrmT_APnIGqUQmlOEc4/edit#gid=416468233">Rock Tech</a>) uses data for various expenses such as fuel cost, tipping/disposal fee and disposal costs, and trucking costs and truck weight limits, along with milage, to determine the transportation costs of the two options. The model also calculates GHC emissions associated with the two options, which to determine GHG emissions savings of the local CDW re-use option. The GHG emissions calculation was based on the estimate by the U.S. Environmental Protection Agency (EPA) that diesel fuel produces approximately 0.43 kg of CO2 emissions per liter and permitted us to calculate the average GHG emissions per ton of material.

<div class="blog-only-image" style="margin-bottom: 20px;">
    <img src="{{ site.blog-img-url }}{{ page.img-url }}Truck.png">
</div>


## Calculator

This case study model provides the basis for comparing different options for CDW
materials that can be re-used in locally produced concrete and cement, which is a
component of concrete. We have created a prototype cost and GHG savings
“calculator” below to demonstrate the potential to expand the model and methodology for local recovery and reuse of other CDW materials.

# Transportation Cost

<label for="input-box-dis">Total Distance (Mile):</label>
<input type="text" id="input-box-dis" name="number">
<button onclick="calculate_transp_cost()">Transp Cost-Standard Process</button> 
<p id="result_total_cost_standard"></p>

<label for="input-box-amt">Amount of Material (Ton):</label>
<input type="text" id="input-box-amt" name="number">
<button onclick="calculate_transp_cost()">Transp Cost-Recyled Process</button>
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

# Greenhouse Gas (GHG) emission

<button onclick="calculate_emission()">GHG Emission-Standard Process</button> 
<p id="result_emission_standard"></p>

<button onclick="calculate_emission()">GHG Emission-Recyled Process</button>
<p id="result_emission_recycled"></p>

<script>
  function calculate_emission() {
    // Get a reference to the input box
    const inputBox1 = document.getElementById("input-box-dis");
    const inputBox2 = document.getElementById("input-box-amt");

    // Retrieve the value of the input box
    const dis = inputBox1.value;
    const amt = inputBox2.value;

    // Process the input using a formula
    const total_emission_standard = Math.ceil(amt/22,0)*dis/4*1.62772;
    // const avg_transp_cost_standard = total_transp_cost_standard/amt;
    const total_emission_recycled = Math.ceil(amt/40,0)*dis/3.5*1.62772;
    // const avg_total_transp_cost_recycled = total_transp_cost_recycled/amt

    // Output the result to the user

    const result_emission_standard = document.getElementById("result_emission_standard");
    result_emission_standard.textContent = `The total GHG emission in standard process is ${total_emission_standard} Kg.`;
    
    const result_emission_recycled = document.getElementById("result_emission_recycled");
    result_emission_recycled.textContent = `The total GHG emission in recycled process is ${total_emission_recycled} Kg.`;
  }

</script>

## Sensitivity Analysis (Jamaica Hospital Case)
