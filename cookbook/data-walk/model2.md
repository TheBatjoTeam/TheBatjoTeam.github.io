---
layout: r-tutorials
title: Data Walk
language: en
slug: data-walk
chapter: model
chapter-title: 3D Modeling
section: 2
section-title: "The base support"
previous: model1
next: model3
next-text: "3D Modeling · Part 3"  
video: "yes"
video-link: "https://player.vimeo.com/video/305384670"
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/data-walk/tree/master/3d_model"
output-image: "/cookbook/data-walk/img/2-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. Switch to the <code>Part Design Workbench</code>. Select the Fusion element and click on the <code>Create Body</code> icon (or go through the menu <code>Part Design > Create New Body</code>). A pop-up warning sign will appear, and you can click <code>OK</code>. Again, the left sidebar will inform you of this change by adding a new <code>Body</code> element, this time below the previous <code>Fusion</code> element, without replacing it. Additionally, the curves will no longer be of the colors you had assigned them, but will be gray again.
</p>
<img src="/cookbook/data-walk/img/2-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Rotate the object so that its base is facing you. Select any one of the faces of the base, as long as it is not one of the protruding ridges. Click on <code>Create a New Sketch</code>. This way, the sketch you are going to create now will already be laying on the base of the curves. You will now use a new command,  <code>External Geometry</code> (<code>Sketch > Sketcher geometries > External geometries</code>), which will allow you to see in your current sketch the projection of a geometrical element that is not part of your current sketch. Once you have selected the command, use the cursor to select the segments on the outer edges of the base of the curves. Look at the image below: the segments you need to click on are the ones that have turned purple in the image. When all four segments have turned purple, click <code>ESC</code> to exit the command.
Now click on the <code>Create Rectangle</code> icon (or go through the menu <code>Sketch > Sketcher geometries > Create Rectangle</code>). Draw a rectangle around the base of the curves, making sure it is bigger than them. This is the green rectangle of the image below. At this point, you need to define exactly the size of the base and position the curves in the center of it.  Select the top left corner of the rectangle and the leftmost point of the top left pink projection segment. Then apply a <code>Horizontal Distance Constraint</code> with length of <code>200mm</code> (or the number that best fits your design).  Select the same two points and now apply a <code>Vertical Distance Constraint</code> with length of <code>400mm</code> (or the number that best fits your design).
Now move on to select the bottom right corner of the rectangle and the rightmost point of the bottom right pink projection segment. On these two points apply the same constraints as before, a <code>Horizontal Distance Constraint</code> of 200mm and a <code>Vertical Distance Constraint</code> of 400mm. Now close the sketch.
</p>
<img src="/cookbook/data-walk/img/2-2.png" />
<img src="/cookbook/data-walk/img/2-3.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Move to the  <code>Part Workbench</code>.  Select this last <code>Sketch </code> and then  <code>Part > Extrude</code>. On the panel that appears on the left, under  <code>Length</code>, type in  <code>20mm</code> and then click  <code>OK</code>. This because the base will be cut out of a 20mm-thick wood sheet. If you are using another material or sheets of another thickness, type in that amount.
</p>
<img src="/cookbook/data-walk/img/2-4.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. You now want to cut out, from the base, the slits where the ridges of the curves will fit into. From the left sidebar, select, <b>in this order</b>, the last <code>Extrude</code> element (the base) and the <code>Fusion element</code> (the curves). You use <code>CMD+click</code> (on a Mac) or <code>CTRL+click</code> (on Windows and Linux) to select multiple elements. Now click through <code>Part > Boolean > Cut</code>.
</p>
<img src="/cookbook/data-walk/img/2-5.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. As a last step, you need to clean up the shape to remove unneeded subdivisions from the surface of the base. To do this, first select the last <code>Body</code> element in your left sidebar and hide it (hit the spacebar or right-click and select <code>Hide Selection</code>).  Select the <code>Cut</code> element from the left sidebar. This element is essentially the base of the object with the slits cut out. Go through <code>Part > Refine Shape</code>.  
Now, to check that everything went well, explore the left sidebar and expand the one-before-last <code>Cut element</code>. You should see an <code>Extrude</code> element and a <code>Fusion</code> element. Expand the <code>Fusion</code> element, select both of the two <code>Array</code> elements nested within it and right-click to choose <code>Show Selection</code>.
<br>You can now rotate the object around to double-check that everything went smoothly.
</p>
<img src="/cookbook/data-walk/img/2-6.png" />
<img src="/cookbook/data-walk/img/2-7.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">