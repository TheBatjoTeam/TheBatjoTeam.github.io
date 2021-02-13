---
layout: default
title: Data Driven News Installations
language: en
handle: /cookbook
nav-order: 2
slug: cookbook
---
## A Digital Fabrication Cookbook for Journalists

*If this is your first visit, you can read our [manifesto](/manifesto) and a [quick guide on digital fabrication](/digital-fabrication)*.

**The cookbook is a tool to promote the knowledge of digital fabrication skills among newsroom professionals.**
While it is targeted at tech-savvy users, it doesn’t require any prior knowledge of digital fabrication. Its main goal is both to **educate** about basic open source tools and techniques, and to promote a **creative** approach to crafting physical data driven installations. For this latter reason, we chose the format of a cookbook: just like cooking recipes, also the digital fabrication recipes published are open to customizations and variations. In fact, each recipe is presented alongside with suggestions on different outputs that can be obtained by modifying the provided recipe. Follow one recipe from start-to-finish and you will have produced a physical data-driven installation.

Each recipe contains videos, text explanations, images, screenshots, diagrams, and renders to help visualize suggestions. All our designs and tutorial are made using exclusively on open source software: FreeCAD, Blender, Slic3r, ArduinoIDE, Inkscape.

Each of the proposed data installations has been designed so that it responds to three main criteria:

1. **Journalistic relevance**: we opted for designs that are suited to portray the data and types of patterns journalists work with most, [after having categorized and studied the data journalism projects awarded at the DJA and Malofiej awards](https://medium.com/batjo/journalism-dataviz-the-whos-whats-whys-and-hows-439a2f3e1d7a). All the designs also include space for text, legends and annotations, as, unlike artistic data sculptures, this is a must for journalistic data viz. 
2. **Learning opportunity**: each of the three designs illustrates specific building blocks of digital fabrication, be it a technology or technique. This way, following through each recipe is also a way to gradually master the basics and move onto designing your own journalistic data installations. 
3. **Advantages of physicality**:  the news installations are designed so that they are not merely a 3D reproduction of a 2D chart. We strove for each design to take full advantage of its being a physical object. For example, by being experienced through multiple sense, or by  fostering real-world interaction or collaboration between participants, etc.

To make it easier to understand the general workflow involved in designing and fabricating objects with digital fabrication techniques, all the recipes are organized in the same sections, each section referring to specific step of the workflow.

![scheme](/img/cookbook/scheme.png){: style="padding-bottom:5px ; max-width:100%; padding-top:5px"}

---- 
## CONTENT OF SECTIONS

![overview](/img/cookbook/overview.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 1. Overview 
{: style="text-align: center;"}
In depth overview of the project so that you can assess whether it is right for your case. Details on what type of data patterns and stories the installation is useful for. Design strengths of the project, including things like whether the installation is reusable, modular, scalable, etc. Fruition strengths of the project, for example whether it engages multiple sense, fosters collaboration and participatory interaction, etc. Suggestions for possible customization options in terms of size, appearance and materials. Indication of the level of effort required to reproduce it, in terms of time, costs and technical difficulty. Ideas on what types of customization options you could implement.   
![overview](/img/cookbook/overview-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"}  

![overview](/img/cookbook/ingredients.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 2. What you need
{: style="text-align: center;"}
Section includes information on the material, hardware and software needed, as well as an estimate of time and costs you should expect to allot. The chapter also explains precisely what is the expected format/structure of the dataset(s) you should use to follow through the steps seamlessly if you are replicating the project your own data.   
![overview](/img/cookbook/ingredients-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 

![overview](/img/cookbook/model.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 3. 3D Modeling and Programming
{: style="text-align: center;"}
Tutorial on how to produce the digital 3D model of the installation components and on how to setup microcontrollers. The tutorial is structured with different levels of accessibility, so that you can both watch the video of the process and/or follow-up by reading the detailed explanation about what is going on in each step. You can also directly download the files with the final results if you get stuck or wish to apply quick customizations without repeating the whole workflow. Depending on the project, some things you will do in this phase are:

- Binding the datapoints and spreadsheet to visual elements such lines, curves, lengths and width
- Building the physical components of the installation that you will use to host sensors and motors to record and animate the data
- Building physical boards with engraved information about the data, axis ticks, labels and annotations, titles, and so on.
- Create circuits connecting electronics components
- Program (Arduino) microcontrollers to read data from sensors and control interactions and appearance   
![overview](/img/cookbook/model-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 


![overview](/img/cookbook/fabricate.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 4. Fabrication
{: style="text-align: center;"}
Step-by-step guide with video, text and photos on how to transform your digital 3D model file into a physical object through digital fabrication machines. This section covers the transformation of your 3d digital model into a physical object. Generally speaking, this process consists of two main steps:

- First, you generate a G-Code file. Such file is essentially a conversion of the digital model into a series of instructions that the machine can understand and follow to convert the digital model into its physical counterpart. The G-Code commands included in the file instruct the machine on things like how to move, which coordinates to follow in tracing paths, how deep to cut (if using a CNC milling machine), what measurement unit to follow, and so on. If you are using a 3D printer, you will also need to figure out whether the project needs supports (for example when printing bridges, overhangs and suspended structures).
- Secondly, you set up the basic parameters on the machine and upload the G-Code file, so that the printing or milling can begin. In this phase, you won't have to actively do anything, although it is recommended that someone stays close to the machines so that, if something goes wrong, you can stop the process in time before wasting material or causing damage.   
![overview](/img/cookbook/fabricate-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 

![overview](/img/cookbook/assemble.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 5. Assembly
{: style="text-align: center;"}
In most cases, once your digital designed has materialized as a physical object, you will still need to apply the final touches manually. What you do in this phase will greatly depend on your project. For example, you might need to:     

- Screw, glue, and/or join different pieces together
- Fit sensors and/or electronics components in their casing
- Color, paint and/or gloss arts of the object
- Sand and smoothen wooden parts and edges
- Connect wires
This section contains infographic instructions on how to assemble your physical data installation in a few steps.
![overview](/img/cookbook/assembly-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 

![overview](/img/cookbook/present.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"}
### 6. Presentation
{: style="text-align: center;"}
Suggestions on how to present the physical news installation.   
![overview](/img/cookbook/present-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 

![overview](/img/cookbook/present.png){: style="max-width:50%; padding-top:2em; padding-bottom:0px; margin: 0 auto; display: block;"} 
### 7. Resources
{: style="text-align: center;"}
Links to useful resources to help you in your project.   

![overview](/img/cookbook/resources-preview.png){: style="padding-bottom:2em ; max-width:100%; padding-top:5px"} 