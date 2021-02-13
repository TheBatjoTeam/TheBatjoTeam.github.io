---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter: model
chapter-title: 3D Modeling
section: 5
section-title: "The legend"
previous: model4
next: fabricate
next-text: "Fabrication"  
video: "yes"
video-link: "https://player.vimeo.com/video/305843077"
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/map/tree/master/3d_model"
output-image: "/cookbook/map/img/6-output.png"
---

<div>
<p style="font-size: 12px;">
<b>1</b>. Of the two <code>.blend</code> files containing the hexagon mesh with either positive or negative values, choose the one containing the biggest absolute value (you would know this by looking at the data in your spreadsheet or QGIS attribute table). Open the file with Blender. Note that you need a mouse to work with Blender. Press the <code>Z</code> key to switch to <code>Wireframe</code> mode. In this visualization mode, the polygons become transparent and so you can see the map below to match their position. Activate the front view by pressing the <code>1</code> key on your keyboard.
</p>
<img src="/cookbook/map/img/6-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Select the tallest of the hexagon solids (the one with the biggest absolute value) and copy-paste it somewhere else in the layout, preferably further away from the other solids so that you don’t confuse it. Select all the other solids except this last one and make them not selectable and hidden from view by clicking the eye icon and the cursor icon in the right-hand panel.
</p>
<img src="/cookbook/map/img/6-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Copy-paste the previously duplicated solid hexagon another time. Select this new copy and scale it to half the height of the original by going on the right <code>Transform</code> menu and on the <code>Dimension</code> box replace the value for <code>Z</code> with half the current value.  <br><em>Note: to make things confusing, there is a Transform menu also on the right, which however contains different commands.</em>
</p>
<img src="/cookbook/map/img/6-3.png" />
<img src="/cookbook/map/img/6-4.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Select the first of the copied hexagon solids and copy it a second time. Select this new copy and scale it so that it proportionally represents the minimum absolute value of the dataset, in our case 1. To do so, go on the right <code>Transform</code> menu and on the <code>Dimension</code> box replace the value for <code>Z</code> with the value corresponding to: the current value divided by the actual max. absolute value in your dataset. You will now have three 3D hexagons: one representing the max. value, one representing the middle value, and one representing the min. value. You can of course tweak this as you wish, for example by having the middle hexagon representing the mean, median, or mode.
<br><em>Note that the <code>Z</code> values of the heights might not correspond to the data value they represent: this because when you had created the 3D model of the grid, you had scaled it to fit into the 50x50 cm base.</em>
</p>
<img src="/cookbook/map/img/6-5.png" />
<img src="/cookbook/map/img/6-6.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Select these three hexagonal solids and go through <code>File > Export > Wavefront (.obj)</code>. When the save as window opens up, there will be a few options on the left panel. Leave everything with the default values, except:</p>
<ul style="font-size: 12px;">
<li><code>Up</code>:  choose <code>Z Up</code></li>
<li><code>Selection only</code>: checkbox checked</li>
</ul>
<p style="font-size: 12px;">
Then click on <code>Export obj</code> from the top right corner. 
</p>
<img src="/cookbook/map/img/6-7.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Make a duplicate of the file containing the grid support for the data layer (see previous section of the tutorial to download it) and open it in FreeCAD. Switch to the <code>Part Design workbench</code>. Click on the last <code>Body</code> element so that it is selected (highlighted in green) and go through the menu <code>Part Design > New body</code>. Click on the top face of the grid object from the 3D view to select it. Then go through the menu <code>Part Design > New Sketch</code>. This will create a new sketch on top of the face you had selected.
</p>
<img src="/cookbook/map/img/6-8.png" />
<img src="/cookbook/map/img/6-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Go through the menu <code>Sketch > Sketcher geometries > External geometry</code>. Then click on the top and bottom segments of the slot where the legend will be placed (see image below). This will import the selected segments as guidelines in the sketch. Now click on <code>Sketch > Sketcher geometries > Rectangle</code> and draw a rectangle as big as the slot (using the purple lines as guidelines). Close the sketch.
</p>
<img src="/cookbook/map/img/6-10.png" />
<img src="/cookbook/map/img/6-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Switch to the <code>Part workbench</code>. Go through the menu <code>Part > Extrude</code>. In the left panel, set the following values:
<ul style="font-size: 12px;">
<li><code>Custom direction > Z: -1</code></li>
<li><code>Length Along</code>: <code>3 mm</code> (the height of the wooden sheet you will use as a support layer for the data)</li>
</ul> </p>
<p style="font-size: 12px;">
Leave the other parameters as they are and click <code>OK</code>.
</p>
<img src="/cookbook/map/img/6-12.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Select the last <code>Body</code> element containing the data support grid and hide it from view by hitting the <code>spacebar</code>. Select the rectangle that you have extruded in the previous step, which should now be the only visible object. Switch to the <code>Part Design workbench</code>. Go through the menu <code>Part Design > New body</code>. Click on the top face of the rectangle and go through the menu <code>Part Design > New Sketch</code>. This will create a new sketch on top of the face you had selected. Go through the menu <code>Sketch > Sketcher geometries > External geometry</code>. Then click on the left and right edges of the rectangle. This will import the selected segments as guidelines in the sketch. Now click on <code>Sketch > Sketcher geometries > Rectangle</code> and draw a rectangle bigger than the base rectangle. Select the top left corner of the big rectangle and the top left corner of the smaller base rectangle. Apply a <code>Vertical Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain vertical distance</code>) with a value <code>5mm</code>. Select the same two corners and now apply a <code>Horizontal Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal distance</code>) with a value <code>5mm</code>. Apply both the vertical and horizontal distance constraints, with the same value of 5mm also between the bottom right corner of the big rectangle and the bottom right corner of the smaller base rectangle. Close the sketch.
</p>
<img src="/cookbook/map/img/6-13.png" />
<img src="/cookbook/map/img/6-14.png" />
<img src="/cookbook/map/img/6-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. Select the sketch from the left sidebar and go through <code>Part Design > Pad</code>. On the left side parameters panel, set a <code>Length</code> of <code>3mm</code>.
</p>
<img src="/cookbook/map/img/6-16.png" />
<img src="/cookbook/map/img/6-17.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Import the three hexagonal polygons you had created in Blender, by going through <code>File > Import</code>. In the select module that appears, select <code>Wavefront OBJ - Arch module (importOBJ)</code>.
</p>
<img src="/cookbook/map/img/6-18.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. When the import is complete, you will see a series of elements on the left sidebar (names will vary depending on the name of the .shp files you first imported in Blender). These elements, while present on the sidebar, will not yet be visible in the view. Move to the <code>Part Workbench</code>. To make the elements visible, select them all from the left sidebar panel and click through <code>Part > Create shape from mesh</code>. A pop-up window will ask you to fill in a value for <code>sewing tolerance</code>. Leave the default option (0,10). The result will be a solid generated from the mesh you had exported from Blender.  Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the <code>Mesh</code> elements from the left sidebar (they have a small greenish icon next to their name) and leave only the <code>Shape</code> elements (blue icon).
Now select all the <code>Shape</code> elements from the left sidebar and go through the menu <code>Part > Refine shape</code>. Wait a few seconds for the process to end. Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the older <code>Shape</code> elements from the left sidebar and leave only the new refined <code>Shape</code> elements. 
Now select all the refined <code>Shape</code> elements from the left sidebar and go through the menu <code>Part > Convert to solid</code>. Wait a few seconds for the process to end. Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the refined <code>Shape</code> elements from the left sidebar and leave only the new refined <code>Solid</code> elements - you’ll recognize them because they have the suffix <code>(solid)</code> appended at the end of the name. In practice, all these latter steps have left the shapes visually unchanged. What has been modified is the mathematical structure used to generate them, so that now they can be easily used for digital fabrication.
</p>
<img src="/cookbook/map/img/6-19.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>13</b>. Switch to the <code>Draft workbench</code>. Navigate to the top view by going through <code>View > Standard views > Top</code>. Then rotate the objects by going through <code>Draft > Rotate</code> and align the three hexagons so that they are parallel to the rectangle you previously modeled.  Now move the three hexagons closer to the rectangle by going through <code>Draft > Move</code>.
</p>
<img src="/cookbook/map/img/6-20.png" />
<img src="/cookbook/map/img/6-21.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>14</b>. Go witch to the <code>Part Design workbench</code>. Select the last <code>Body</code> element from the left sidebar. Click on the top face of the rectangle and go through the menu <code>Part Design > New Sketch</code>. Inside the base rectangle, draw three segments like in the image below, by going through <code>Sketch > Sketcher geometries > Create line</code>.  Make the three of them of equal length by selecting them all and applying the <code>Equality Constraint</code> (<code>Sketch > Sketcher constraints > Constrain equal</code>). Make each of these three lines of the same length as one of the edges of the hexagonal polygons, in this case 10,19mm. To do so, click on one of the three segments and apply a <code>Horizontal Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal distance</code>). Type in <code>10,19mm</code> as the <code>length</code>.
</p>
<img src="/cookbook/map/img/6-22.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>15</b>. Toggle to <code>Construction Mode</code>. <code>Construction mode</code> allows you to draw lines that are not actually part of the object itself, but that only serve as modeling supports. To switch to <code><code>Construction Mode</code>, go through the menu Sketch > Sketcher Geometries > Toggle Construction Geometry</code>. Everything you draw now will be blue to indicate that the <code>Construction</code> Mode has been activated. Now navigate through <code>Sketch > Sketcher geometries > Create line</code>. Draw two lines connecting the three lines previously drawn, like in the image below. Select the two blue lines make them of equal length by applying the <code>Equality Constraint</code> (<code>Sketch > Sketcher constraints > Constrain equal</code>).
</p>
<img src="/cookbook/map/img/6-23.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>16</b>. Without exiting <code>Construction Mode</code>, draw other lines to match those in the illustration below and apply the <code>Equality Constraint</code> (to the four diagonal lines); a  <code>Horizontal Distance Constraint</code>  of <code>60mm</code> (between the extreme points of the long horizontal line made up of 5 segments); and a <code>Vertical Distance Constraint</code> of <code>17,64mm</code> (to the two vertical lines). This will position the three white segments in the correct position. Close the sketch.
</p>
<img src="/cookbook/map/img/6-24.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>17</b>. Switch to the <code>Draft workbench</code>. Select the highest hexagon polygon. Go through <code>Draft > Move</code>. In FreeCAD, you define movements by clicking the starting point and arrival point of the movement. In this case, first click on the bottom right corner of the base of the polygon (see first image below), then click on the right ending point of the first segment (see second image below). In practice, this will align the hexagonal polygon to the white line. Repeat for the other two hexagonal polygons.  You can also check by navigating to the top view by going through <code>View > Standard views > Top</code> (see third image below). 
</p>
<img src="/cookbook/map/img/6-25.png" />
<img src="/cookbook/map/img/6-26.png" />
<img src="/cookbook/map/img/6-27.png" />
<img src="/cookbook/map/img/6-28.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>18</b>. Navigate through  <code>Draft > Utilities > Select plane</code>. Select the <code>XZ plane</code>. Select the three hexagonal polygons. Go through <code>Draft > Move</code>. Move them vertically until they snap on top of the base rectangle. 
</p>
<img src="/cookbook/map/img/6-29.png" />
<img src="/cookbook/map/img/6-30.png" />
<img src="/cookbook/map/img/6-31.png" />
<img src="/cookbook/map/img/6-32.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>19</b>.  Switch to the <code>Part workbench</code>. Select the three hexagonal polygons and the base from the left sidebar. Navigate through  <code>Part > Boolean > Union</code>. A new <code>Fusion</code> element, grouping all others, should now have appeared on the left sidebar. 
</p>
<img src="/cookbook/map/img/6-33.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>20</b>. You can unhide the support grid you had hidden in step 9 to see the final result in context. Then, select the last <code>Fusion</code> element from the left sidebar, the one containing this last object created. Go through <code>File > Export</code>. Select .STL as the file type and export your project.
</p>
<img src="/cookbook/map/img/6-34.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>21</b>. At last, you will add an engraving with the numbers that correspond to each hexagonal element of the legend. First, hide the last <code>Fusion</code> element so that you only see the data support grid, without the 3D legend. Move to the <code>Drawing Workbench</code> and click through the menu <code>Drawing > Insert new drawing > A0 Landscape.</code> A <code>Page</code> element will appear on the left sidebar and the window where your designed object was will radically change. It will now show a blank page (don’t panic).
</p>
<img src="/cookbook/map/img/6-35.png" />
<img src="/cookbook/map/img/6-36.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>22</b>. From the left sidebar, select the last <code>Body</code> element, the one corresponding to data support grid. Click through the menu <code>Drawing > Insert Orthographic Views</code>. A new interface with some options and checkboxes will appear on the left sidebar. Change the defaults so that the options and values match those in the image below. Then click <code>OK</code>.
</p>
<img src="/cookbook/map/img/6-37.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>23</b>. Click the <code>Page</code> element on the left sidebar, then go through the menu <code>Drawing > Export page</code>. Name the file and select a destination path. This will save the page as an .SVG graphics file.
</p>
<img src="/cookbook/map/img/6-38.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>24</b>. Open the .SVG file with a vector graphics software and add all the graphical elements you desire. Because this part is not strictly about 3D digital fabrication, but rather about 2D vector graphics, and because it can be done with any vector graphics software you might already be familiar with, we will skip the step-by-step text tutorial. You can watch the video (minutes 17:30 - 23:29) to see how we proceeded to create the graphics using Inkscape. Or you can also download the resulting .SVG graphics file from Github and edit/reuse it directly.  If you are making your own .SVG graphics, make sure you convert all objects and texts to paths before proceeding to the export.  <br><br>
<b>If you or your lab has a laser cutting machine, you can already use this .SVG file to engrave the base of the installation with these graphics. This will definitely save you time. </b><br> Otherwise, if you only have access to a CNC milling machine, you need to follow through with the next steps of tutorial.
</p>
<img src="/cookbook/map/img/6-39.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>25</b>. Once you have the graphics in place, you switch back to the FreeCAD project and import the .SVG file by going through <code>File > Import</code>. In the pop-up that appears next, make sure you select the option <code>SVG as geometry (importSVG)</code>.  
</p>
<img src="/cookbook/map/img/6-40.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>26</b>. Switch to the <code>Draft Workbench</code> and select the top view by going through <code>View > Standard Views > Top</code>. Select all the elements that are part of the imported .SVG by selecting all of them on the left sidebar pane (see image below). Move them by clicking through the menu <code>Draft > Move</code>. On the panel that has appeared on the left, make sure you deselect the <code>Copy</code> option. You will then define the movement of all the selected elements by choosing (clicking) the starting point and ending point of the movement. The ending point should result in the graphics being aligned with the hole where the 3D legend will fit into.
</p>
<img src="/cookbook/map/img/6-41.png" />
<img src="/cookbook/map/img/6-42.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>27</b>. Once you are satisfied with the position of the vectors, switch to the <code>Part Workbench</code> and select the axonometric view by going through <code>View > Standard Views > Axonometric</code>. Hide the data support grid by selecting it from the left sidebar and right clicking through <code>Hide Selection</code> (or hit the <code>spacebar</code>). 
With your mouse cursor, from the 3D layout, select all the outlines of the letters and numbers that are part of your graphic. Make sure you also don’t select the “holes” (technically: the counters) of the letters and numbers. With all of them selected, click on the menu <code>Part > Extrude</code>. In the selection panel that has appeared on the left, set the following parameters:</p>
<ul style="font-size: 12px;">
<li><code>Custom direction > Z: -1</code> </li>
<li><code>Length > Along > 1 mm</code> (this is how deep the text will be engraved on the material you are engraving it upon)</li>
</ul>
<p style="font-size: 12px;">
Click <code>OK</code>. Depending on your machines, it might take a few seconds, but at the end of the processing you will see a 3D model of the vectors and several new <code>Extrude</code> elements on the left sidebar.
</p>
<img src="/cookbook/map/img/6-43.png" />
<img src="/cookbook/map/img/6-44.png" />
<img src="/cookbook/map/img/6-45.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>28</b>. Unite all the <code>Extrude</code> elements that make up your graphics in a single element. To do so, select all the <code>Extrude</code> elements on the left sidebar and then go through the menu <code>Part > Boolean > Union</code>. This process might also take a bit of time to complete, depending on your CPU. When it’s done, you will see that, on the left sidebar,  a <code>Fusion</code> element has replaced all the single <code>Extrude</code> elements.
</p>
<img src="/cookbook/map/img/6-46.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>29</b>. Unhide the data support grid by selecting the corresponding <code>Body</code> element on the left sidebar and right-clicking through <code>Show selection</code>. Now select both this <code>Body</code> element and the <code>Fusion</code> element from the left sidebar, making sure that the <code>Body</code> element is the first one you select. Go through <code>Part > Boolean > Cut</code>.  Again, depending on your CPU, this process might take a few seconds. At the end of the operation, if you look at the left sidebar, you will notice that both the <code>Body</code> element (the support grid) and the <code>Fusion</code> element (the graphics) have been grouped under a new <code>Cut</code> element.
</p>
<img src="/cookbook/map/img/6-47.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>30</b>. As you can see, because of how extrusion works, it didn’t handle all the letters and numbers as desired. This is due to the fact that the command has no way of detecting the difference between a line and what we perceive as a “hole”/counter. To remedy this, first select all the outlines of the counters in your text. With all of them selected, click on the menu <code>Part > Extrude</code>. In the selection panel that has appeared on the left, set the following parameters:
<ul style="font-size: 12px;">
<li><code>Custom direction > Z: -2</code> </li>
<li><code>Length > Along > 2 mm</code> (so that they are engraved deeper than the letters, which had a value of 1, but are not cut all the way through the material, which has a thickness of 3mm)</li>
</ul></p><p style="font-size: 12px;">
Click <code>OK</code> . Depending on your machines, it might take a few seconds, but at the end of the processing you will see a 3D model of the vectors and several new <code>Extrude</code>  elements on the left sidebar.
</p>
<img src="/cookbook/map/img/6-48.png" />
<img src="/cookbook/map/img/6-49.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>31</b>. As a last step, you need to unite all the extruded number/letter counters (the last <code>Extrude</code> elements) with the data support grid with the graphics engraved (the last <code>Cut</code> element).  To do so, select both this <code>Cut</code> element and the <code>Extrude</code> element from the left sidebar, <b>making sure that the <code>Cut</code> element is the first one you select.</b> Go through <code>Part > Boolean > Union</code>.  Again, depending on your CPU, this process might take a few seconds. At the end of the operation, if you look at the left sidebar, you will notice that both the <code>Cut</code> element (the engraved support grid) and the <code>Extrude</code> element (number/letter counters) have been grouped under a new <code>Fusion</code> element. Your file is now ready to go into fabrication, so make sure you save it and export it as .STL</p>
<img src="/cookbook/map/img/6-50.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">