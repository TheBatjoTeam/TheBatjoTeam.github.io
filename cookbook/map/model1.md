---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter-title: 3D Modeling
chapter: model
section: 1
section-title: "The base map"
previous: model
next: model2
next-text: "3D Modeling · Part 2   "  
video: "yes"
video-link: "https://player.vimeo.com/video/305834052"
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/map/tree/master/3d_model"
output-image: "/cookbook/map/img/1-output.png"

---
<div>
<p style="font-size: 12px;">
<b>1</b>. Opening FreeCAD and create a new project by clicking on <code>File > New</code>. Open the <code>Part Design Workbench</code>, as shown in the image, by clicking on the dropdown menu where you now see <code>Start</code>. This workbench contains all the commands used to model the single parts of the object.</p>
<img src="/cookbook/map/img/1-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Create a new body (the container for your design) and a new sketch (the 2D drawing of your object). To do this, first click through the menu <code>Part Design > Create Body</code>, then through <code>Part Design > Create Sketch</code>.
Once you've done this, select the <code>XY Plane</code> from the <code>Combo View Panel</code> that should have appeared on the left side of the screen and click <code>OK</code>.
</p>
<img src="/cookbook/map/img/1-2.png" />
<img src="/cookbook/map/img/1-3.png" />
<img src="/cookbook/map/img/1-4.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. You should have been automatically redirected to the <code>Sketch Workbench</code>, if not select it manually from the workbench dropdown. Then, click through the menu <code>Sketch > Sketcher Geometries > Create rectangle</code>. You can now draw a rectangle similar to that in the image below. Don’t worry about dimensions, we'll fix them else further on. 
</p>
<img src="/cookbook/map/img/1-5.png" />
<img src="/cookbook/map/img/1-6.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Select the top segment of the rectangle by clicking on it (selected elements turn green) and then apply the <code>Horizontal Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal distance</code>). A pop-up window will prompt you to fill in the length value of the selected segment. Type in <code>500 mm</code>.  At this point, you want to apply the <code>Equality Constraint</code> between this top segment and one of the side segments. This constraint forces the sides of the rectangle to be the same length as the top and bottom, and will result in your shape becoming a 50x50 cm square. To apply this constraint, select the top segment of the rectangle and the right side segment and go through <code>Sketch > Sketcher constraints > Constrain equal</code>.
</p>
<img src="/cookbook/map/img/1-7.png" />
<img src="/cookbook/map/img/1-8.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Position the square at the center of your plane. To do so, select the origin point and one of the corners of the square. Apply the <code>Horizontal Distance Constraint</code> and type in 250mm</code>. Select the origin and the corner of the square again, and now apply the <code>Vertical Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain vertical distance</code>). Type in <code>250mm</code> in the pop-up window that appears. Close the Sketch.
</p>
<img src="/cookbook/map/img/1-9.png" />
<img src="/cookbook/map/img/1-10.png" />
<img src="/cookbook/map/img/1-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Select the sketch from the left side panel (see image below). Go through the menu <code>Part Design > Pad</code>. In the left panel you will be asked to type in a length parameter. Fill it in with <code>3mm</code> (the height of your plexiglas sheet), and check the box with the option <code>Reverse</code>, this way the square will be padded towards the bottom of the XY plane.  Click <code>OK</code>. 
</p>
<img src="/cookbook/map/img/1-12.png" />
<img src="/cookbook/map/img/1-13.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Import the .SVG file with the map you wish to engrave. To do so, click through <code>File > Import > Select file</code>. Make sure you click on the option to <code>open SVG as geometry (importSVG)</code> in the pop-up that appears. The map vectors should now be visualized on the XY plane. 
</p>
<img src="/cookbook/map/img/1-14.png" />
<img src="/cookbook/map/img/1-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Move the imported vectors on top of the square base you have previously modeled. To do so, switch to the <code>Draft Workbench</code> and select the top view by going through <code>View > Standard Views > Top</code>. Select all the elements that are part of the imported .SVG by selecting all of them on the left sidebar pane (see image below). Move them by clicking through the menu <code>Draft > Move</code>. On the panel that has appeared on the left, make sure you deselect the <code>Copy</code> option. You will then define the movement of all the selected elements by choosing (clicking) the starting point and ending point of the movement.
</p>
<img src="/cookbook/map/img/1-16.png" />
<img src="/cookbook/map/img/1-17.png" />
<img src="/cookbook/map/img/1-18.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Once you are satisfied with the position of the vectors, switch to the <code>Part Workbench</code> and select the axonometric view by going through <code>View > Standard Views > Axonometric</code>. Hide the padded square element by selecting it from the left sidebar and right clicking <code>Hide Selection</code> (or hit the <code>spacebar</code>). From the left sidebar, select all the polygon elements and wire elements that are part of the imported vector map. Click on the menu <code>Part > Extrude</code>. In the selection panel that has appeared on the left, set the following parameters:</p>
<ul style="font-size: 12px;">
<li><code>Custom direction > Z: -4</code></li>
<li><code>Length > Along > 0.5 mm</code> (this is how deep the map will be engraved on the plexiglas or the material you are engraving it upon).</li>
</ul>
<p style="font-size: 12px;">
Click <code>OK</code>. Depending on your machines, it might take a few seconds, but at the end of the processing you will see a 3D model of the vectors and several new <code>Extrude</code> elements on the left sidebar.
</p>
<img src="/cookbook/map/img/1-19.png" />
<img src="/cookbook/map/img/1-20.png" />
<img src="/cookbook/map/img/1-21.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. Unite all the extruded polygons that make up your map into a single element. To do so, select all the <code>Extrude</code> elements on the left sidebar and then go through the menu <code>Part > Boolean > Union</code>. This process might also take a bit of time to complete, depending on your CPU. When it’s done, you will see that, on the left sidebar,  a <code>Fusion</code> element has replaced all the single <code>Extrude</code> elements.</p>
<img src="/cookbook/map/img/1-22.png" />
<img src="/cookbook/map/img/1-23.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Unhide the padded square by selecting it on the left sidebar and right-clicking on <code>Show selection</code>. Now select both the <code>Pad</code> element and the <code>Fusion</code> element from the left sidebar, making sure that the <code>Pad</code> element is the first one you select. Go through <code>Part > Boolean > Cut</code>.  Again, depending on your CPU and the complexity of the vector map, this process might take up even minutes. At the end of the operation, if you look at the left sidebar, you will notice that both the <code>Pad</code> element (the square) and the <code>Fusion</code> element (the map) have been grouped under a new <code>Cut</code> element.
</p>
<img src="/cookbook/map/img/1-24.png" />
<img src="/cookbook/map/img/1-25.png" />
<img src="/cookbook/map/img/1-26.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. Select the <code>Cut</code> element, go through <code>File > Export</code> and save it as an <code>STL Mesh (*.stl *ast)</code>. Then, also save the whole project as a FreeCAD file, with the <code>.fctd</code> extension.
</p>
<img src="/cookbook/map/img/1-27.png" />
</div>
<div class="clear"></div>