---
layout: r-tutorials
title: Data Walk
language: en
slug: data-walk
chapter: model
chapter-title: 3D Modeling
section: 3
section-title: "Text & graphics "
previous: model2
next: fabricate
next-text: "Fabrication"  
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/data-walk/tree/master/3d_model"
video: "yes"
video-link: "https://player.vimeo.com/video/305381291"
output-image: "/cookbook/data-walk/img/3-output.png"
---

<div>
<p style="font-size: 12px;">
<b>1</b>. Hide the two <code>Array</code> elements so that again only the base is showing. Move to the <code>Drawing Workbench</code> and click through the menu <code>Drawing > Insert new drawing > A0 Landscape</code>. A <code>Page</code> element will appear on the left sidebar and the window where you designed object was will radically change. It will now show a blank page (don’t panic).
</p>
<img src="/cookbook/data-walk/img/3-1.png" />
<img src="/cookbook/data-walk/img/3-2.png" />
<img src="/cookbook/data-walk/img/3-3.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Select the last <code>Cut</code> element from the left sidebar. Click through the menu <code>Drawing > Insert Orthographic Views</code>. A new interface with some options and checkboxes will appear on the left sidebar. Change the defaults so that the options and values match those in the image below. Then click <code>OK</code>.
</p>
<img src="/cookbook/data-walk/img/3-4.png" />
<img src="/cookbook/data-walk/img/3-5.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Now it’s time to export the project. Click the <code>Page</code> element on the left sidebar, then go through the menu <code>Drawing > Export page</code>. Name the file and select a destination path. This will save the page as an .SVG graphic file.
</p>
<img src="/cookbook/data-walk/img/3-6.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Open the file with Inkscape. Click on one of the four edges of the base and move it aside, so that you can then easily select everything except the base and delete it. See the second image below for the results of this operation.
</p>
<img src="/cookbook/data-walk/img/3-7.png" />
<img src="/cookbook/data-walk/img/3-8.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. At this point, you can open the .SVG file with a vector graphics software and add all the graphical elements you desire. Because this part is not strictly about 3D digital fabrication, but rather about 2D vector graphics, and it can be done with any vector graphics software you might already be familiar with, we will skip the step-by-step text tutorial. If you want to receive guidance, you can watch the video uploaded at the top of the page, which includes how we created the graphics using Inkscape. Or you can also download the resulting .SVG graphics file from Github and edit/reuse it directly, without starting from scratch, and then proceed with the following steps.  If you are making your own .SVG graphics, make sure you convert all objects and texts to paths before proceeding to the export.  <br><em><b>Note</b> that if you or your lab has a laser cutting machine, you can already use this .SVG file to engrave the base of the installation with these graphics, without following through with the rest of this section. This will definitely save you time. Otherwise, if you only have access to a CNC milling machine, you need to follow through with the next steps of tutorial.</em><br>
</p>
<img src="/cookbook/data-walk/img/3-9.png" />
<img src="/cookbook/data-walk/img/3-10.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Switch back to the FreeCAD window, navigate to <code>File > Import</code> and select the exported .svg file. In the pop-up that appears next, make sure you select the option <code>SVG as geometry (importSVG)</code>.
</p>
<img src="/cookbook/data-walk/img/3-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Switch to the <code>Draft Workbench</code>.  Select the last two <code>Array</code> elements from the left sidebar and hide their visibility, so that you can clearly see the whole base component and the imported text/graphics. Go through <code>View > Standard Views > Top</code> to have a clear view of all the elements. Select the rectangle containing the text/graphics via <code>Edit > Box Selection</code>. On the menu, go to <code>Draft > Move</code> and click on one of the corners of the rectangle with the imported text/graphics. Then, click on the corresponding corner of the object’s base, as shown in the last of the images below. This will perfectly align your graphics to the base.
</p>
<img src="/cookbook/data-walk/img/3-12.png" />
<img src="/cookbook/data-walk/img/3-13.png" />
<img src="/cookbook/data-walk/img/3-14.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. You can now hide the base (the last <code>Cut</code> component on the left sidebar) and delete the 4 segments forming the rectangle that contains the text/graphics, so that your results look like the following image. </p>
<img src="/cookbook/data-walk/img/3-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Switch to the <code>Part Workbench</code>. Select all the text/graphics element with a box selection and extrude them via the <code>Part > Extrude</code> command. On the left pop-up panel that now appears, assign a length of <code>-10mm</code>.<br><br> <em><b>Note</b>: if your computer freezes or crashes at this point, it might be that it is not powerful enough to handle the calculation. If you suspect this is the case, work in sections and select + extrude only a part of the text/graphics element each time.</em>
</p>
<img src="/cookbook/data-walk/img/3-16.png" />
<img src="/cookbook/data-walk/img/3-17.png" />
<img src="/cookbook/data-walk/img/3-18.png" />
<img src="/cookbook/data-walk/img/3-19.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. As you can see, because of how extrusion works, it didn’t handle all the letters and numbers as desired. This is due to the fact that the command has no way of detecting the difference between a line and what we perceive as a “hole” (technically: counter). To remedy this, we need to make a Boolean cut operation on all the letters. For each of the letters/numbers that present this problem, select the outer shape and then the inner shape (in this order) and then click through <code>Part > Boolean > Cut</code>.
</p>
<img src="/cookbook/data-walk/img/3-20.png" />
<img src="/cookbook/data-walk/img/3-21.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Select all of these text/graphics elements and perform a Boolean union, by clicking through <code>Part > Boolean > Union</code>. All of these components are now grouped in a single Fusion element in the left sidebar, so that you can now select all of them at once.
</p>
<img src="/cookbook/data-walk/img/3-22.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. From the left sidebar, select both the last <code>Cut</code> element (the one with the base) and the last <code>Fusion</code> element (with the text and graphics). <b>Make sure you select them in this order</b>. Then perform a cut by clicking through <code>Part > Boolean > Cut</code>. Depending on how powerful your processor is, it might take a few minutes for the calculation to be completed. Your file is now ready to go into fabrication, so make sure you save it.
</p>
<img src="/cookbook/data-walk/img/3-23.png" />
<img src="/cookbook/data-walk/img/3-24.png" />
<img src="/cookbook/data-walk/img/3-25.png" />
<img src="/cookbook/data-walk/img/3-26.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<h4>A few words on the graphics and text</h4>
<p style="font-size: 12px;">
To keep things simple, this tutorial has kept the graphics and text elements to the minimum. It is pretty easy, however, to add more elements, like titles, annotations, legends and so on. The level of complexity you can achieve will depend greatly on your previous knowledge of graphics notions and of the software. Additionally, it will depend on the kind of machines you have access to. If you only have a CNC milling machine to engrave, then this means that you will manually have to fix the holes in every single letter of your text. Something that can quickly escalate to be a tedious and long task, prone to errors (it’s easy to forget about a few letters). In this case, it is probably wise to stick to the basics and use other things (posters, stickers…) to provide more context. On the other hand, if you have a laser cutter/engraver, then the graphics can be quite complex, like in the suggested example below, as the .SVG file produced with Inkscape (or your software of choice) can be directly used to engrave, without the need to pass through FreeCAD. 
</p>
<img src="/cookbook/data-walk/img/graphics-best.png" style="border: 0.5px solid black"/>
