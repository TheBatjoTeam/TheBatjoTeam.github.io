---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter: fabricate
chapter-title: Fabrication
section: 1.c
section-title: "The two 3D data layers (3D printing GCode)"
previous: fabricate2
next: fabricate4
next-text: "Fabrication · Part 1.d"  
video: "yes"
video-link: "https://player.vimeo.com/video/305852157"

more_video: 2
video-link1: "https://player.vimeo.com/video/305852373"
video-link2: "https://player.vimeo.com/video/305855615"

download: "yes"
download-name: "STL"
download-link: "https://github.com/TheBatjoTeam/map/tree/master/3d_model/stl"
output-image: "/cookbook/map/img/10-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. In FreeCAD, open the <code>.fctd</code> file containing the data grid support layer. Move to the <code>Draft workbench</code>, select the final object and go through <code>Draft > Clone</code>. You will now see a new <code>Clone</code> element in the left sidebar. Do the same for the <code>.fctd</code> file containing the 3D data layer. Create a new FreeCAD project and copy-paste these <b>two</b> <code>Clone</code> elements in the new file. </p>
<img src="/cookbook/map/img/10-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Change view by going through <code>View > Standard Views > Front</code>. From the left side panel, select the <code>Clone</code> element representing the 3D data layer.  Navigate to the <code>Data</code> menu at the bottom of the left panel sidebar. Go to the <code>Placement > Position > Z</code> and increase/decrease the value until its sits right below the data grid support layer (in our case, we had to use a value of  <code>-20.5 mm</code>). </p>
<img src="/cookbook/map/img/10-2.png" />
<img src="/cookbook/map/img/10-3.png" />
<img src="/cookbook/map/img/10-4.png" />
<img src="/cookbook/map/img/10-5.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Move to the <code>Part workbench</code>. Select both the <code>Clone</code> element of the 3D data and the <code>Clone</code> element of the support grid (in this order!)  and go through <code>Part > Boolean > Cut</code>. The result will be a new <code>Cut</code> element, consisting of the 3D data layer with the grid pattern of the support layer cut into it.
</p>
<img src="/cookbook/map/img/10-6.png" />
<img src="/cookbook/map/img/10-7.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Move to the <code>Part Design</code> workbench. Select the Cut</code> element and click on <code>Part Design > New body</code>. This will create a new container <code>Body</code> element that uses the selected <code>Cut</code> element as base. Click on the face of the object shown in the second image below. Then go through the menu <code>Part Design > New Sketch</code>. This will create a new sketch on top of the face you had selected.
</p>
<img src="/cookbook/map/img/10-8.png" />
<img src="/cookbook/map/img/10-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Toggle to <code>Construction Mode</code>. <code>Construction Mode</code> allows you to draw lines that are not actually part of the object itself, but that only serve as modeling supports. To switch to <code>Construction Mode</code>, go through the menu <code>Sketch > Sketcher Geometries > Toggle Construction Geometry</code>. Everything you draw now will be blue to indicate that the <code>Construction Mode</code> has been activated. Now navigate through <code>Sketch > Sketcher geometries > Create polyline</code>. Draw a series of horizontal and vertical segments like in the image below, 4 four segments for each side of the square data layer.</p>
<img src="/cookbook/map/img/10-10.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Go through the menu <code>Sketch > Sketcher geometries > External geometry</code>. Then click on the top and bottom segments of the square base of the 3D data layer to select them (see image below). This will import the selected segments as guidelines in the sketch.</p>
<img src="/cookbook/map/img/10-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Click on the top right vertex of the constructed square and on the top right vertex of the square base (see image below). Make them coincidental by going through <code>Sketch > Sketcher constraints > Constrain coincident</code>. Repeat for the other vertices of the squares until the blue segments drawn in construction mode are coincidental with the edges of the square data layer.
</p>
<img src="/cookbook/map/img/10-12.png" />
<img src="/cookbook/map/img/10-13.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Navigate again through <code>Sketch > Sketcher geometries > Create polyline</code>. Draw a series of horizontal and vertical segments like in the image below, so that the end result is a grid pattern of squares similar to those of the data layer, covering half of the data layer. (For the other half, we’ll mirror this pattern to save time).
</p>
<img src="/cookbook/map/img/10-14.png" />
<img src="/cookbook/map/img/10-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Navigate through <code>Sketch > Sketcher geometries > Create polyline</code> and draw the two diagonal lines shown in the first image below. Select these two diagonal lines and make them of equal length by applying the <code>Equality Constraint</code> (<code>Sketch > Sketcher constraints > Constrain equal</code>) (see second image below). Repeat this operation for all the blue squares (See last image below: small red equal signs are next to all the blue diagonal lines)
</p>
<img src="/cookbook/map/img/10-16.png" />
<img src="/cookbook/map/img/10-17.png" />
<img src="/cookbook/map/img/10-18.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. Select the 4 blue construction lines that make up the first square (see image below). Click on <code>Toggle Construction Mode</code>. This will convert the selected lines from blue construction lines to white sketched lines. Now close the sketch.
</p>
<img src="/cookbook/map/img/10-19.png" />
<img src="/cookbook/map/img/10-20.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Switch to the <code>Part workbench</code>. From the left sidebar, select the sketch and go to <code>Part > Extrude</code>. In the selection panel that has appeared on the left, set the following parameters:
<ul style="font-size: 12px;">
<li><code>Length > Along > 50 mm</code></li>
<li><code>Symmetric</code>: checkbox checked</li>
</ul>
</p>
<p style="font-size: 12px;">
Click <code>OK</code>. Depending on your machines, it might take a few seconds, but at the end of the processing you will see a 3D block corresponding to the first section of the data you will 3D print.
</p>
<img src="/cookbook/map/img/10-21.png" />
<img src="/cookbook/map/img/10-22.png" />
<img src="/cookbook/map/img/10-23.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">


<div>
<p style="font-size: 12px;">
<b>12</b>. Select the 3D block, which is the last <code>Extrude</code> element on the left sidebar. Navigate through <code>Part > Mirroring</code>. On the <code>Mirroring</code> pane that appears on the left, select <code>XZ</code> as plane and click <code>OK</code>.  You will now have a second extruded block at the bottom.
</p>
<img src="/cookbook/map/img/10-24.png" />
<img src="/cookbook/map/img/10-25.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>13</b>. Now select the first and second blocks (on the left sidebar, the <code>Extrude</code> element and <code>Extrude (Mirror #1) element)</code>. Navigate through <code>Part > Mirroring</code>. On the <code>Mirroring</code> pane that appears on the left, select <code>YZ</code> as plane and click <code>OK</code>. You will now have a third and fourth extruded block on the other side.
</p>
<img src="/cookbook/map/img/10-26.png" />
<img src="/cookbook/map/img/10-27.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>14</b>. From the left sidebar, select the last <code>Body</code> element and copy-paste it. Hide the previous original <code>Body</code> element and the four <code>Extrude</code> elements representing the four 3D blocks. Then, expand the new <code>Body</code> element copy, navigate to the <code>Sketch</code> element contained and double-click to open it. </p>
<img src="/cookbook/map/img/10-28.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>15</b>. Select the three segments of the first square, shown in green in the image below. Go through the menu <code>Sketch > Sketcher Geometries > Toggle Construction Geometry</code>. This will convert the sketched lines back to blue construction lines. Now select the segments that form the square right below this one (see second image below) and again <code>Toggle Construction Geometry</code> to convert these construction lines to sketched lines. Close sketch. 
 </p>
<img src="/cookbook/map/img/10-29.png" />
<img src="/cookbook/map/img/10-30.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>16</b>. Repeat steps 11-13 and you will now have an object like the image below. </p>
<img src="/cookbook/map/img/10-31.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>17</b>. From the left sidebar, select the last <code>Body</code> element and copy-paste it. Hide the previous original <code>Body</code> element and the four <code>Extrude</code> elements representing the four 3D blocks. Then, expand the new <code>Body</code> element copy, navigate to the <code>Sketch</code> element contained and double-click to open it. </p>
<img src="/cookbook/map/img/10-32.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>18</b>. Select the three segments white of the second square you’ve worked on, shown in green in the first image below. Go through the menu <code>Sketch > Sketcher Geometries > Toggle Construction Geometry</code>. This will convert the sketched lines back to blue construction lines. Now select the segments that form the square right next to the previous one (see second image below) and again <code>Toggle Construction Geometry</code> to convert these construction lines to sketched lines. Close sketch. </p>
<img src="/cookbook/map/img/10-33.png" />
<img src="/cookbook/map/img/10-34.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>19</b>. Repeat steps 11-13 and you will now have an object like the image below. </p>
<img src="/cookbook/map/img/10-35.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>20</b>. From the left sidebar, select the last <code>Body</code> element and copy-paste it. Hide the previous original <code>Body</code> element and the four <code>Extrude</code> elements representing the four 3D blocks. Then, expand the new <code>Body</code> element copy, navigate to the <code>Sketch</code> element contained and double-click to open it.</p>
<img src="/cookbook/map/img/10-36.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>21</b>. Select the three segments white of the third square you’ve worked on, shown in green in the first image below. Go through the menu <code>Sketch > Sketcher Geometries > Toggle Construction Geometry</code>. This will convert the sketched lines back to blue construction lines. Now select the segments that form the square right on top of the previous one (see second image below) and again <code>Toggle Construction Geometry</code> to convert these construction lines to sketched lines. Close sketch. </p>
<img src="/cookbook/map/img/10-37.png" />
<img src="/cookbook/map/img/10-38.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>22</b>. Repeat steps 11-13 and you will now have an object like the image below. </p>
<img src="/cookbook/map/img/10-39.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>23</b>. From the left sidebar, unhide all the <code>Extrude</code> elements you had previously hidden.
 </p>
<img src="/cookbook/map/img/10-40.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>24</b>. In order to make it easier to proceed with the following steps, you should rename each of the 16 3D blocks with a unique id. To rename a block, select the <code>Extrude</code>  element and right-click. The following image shows the naming convention used in this tutorial.
</p>
<img src="/cookbook/map/img/10-41.png" />
<img src="/cookbook/map/img/10-42.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>25</b>. Hide all the elements from the left sidebar, except the first Cut element (the data layer with the grid cuts) and the A1 extruded block. Select the two of them and go through <code>Part > Boolean > Intersection</code>. The result will be a 12.75 x 12.75 block containing the first section of the data layer.
</p>
<img src="/cookbook/map/img/10-43.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>26</b>. Repeat step 25 for all the 15 other blocks. The result is shown in the following image. Notice the names of the elements in the left sidebar, which follow the logic of <code>A1_cut, A2_cut,</code> etc.
</p>
<img src="/cookbook/map/img/10-44.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>27</b>. Select each of the <code>Cut</code> elements and export them one by one as STL files by going through <code>File > Export</code>. When choosing a filename, it’s easier if you stick to the A1, A2, etc. naming convention. Additionally, save the whole project as a FreeCAD file (<code>.fcstd</code>).
</p>
<img src="/cookbook/map/img/10-45.png" />
<img src="/cookbook/map/img/10-46.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>28</b>. Open Slic3r. Slic3r is a software that processes a 3D model and generated instructions for the 3D printer, for example by slicing the volume into thin layers, creating supports for hanging elements, etc. The version of Slic3r used in this tutorial is a custom version tailored to the 3D printer used, a Prusa i3 mk3. The interface and the settings are however part of any Slic3r version you used. If you are using a general version of Slic3r, then you will need to set the configurations appropriately for your specific 3D printer. It’s wise to talk to the owner/operator of the 3D printer in this phase.
</p>
<img src="/cookbook/map/img/10-47.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>29</b>. Click on the <code>Add</code> button from the top toolbar and import the .stl file for the first section of the data layer. The following steps will depend on whether the imported section is flat (representing a piece with no data, see second image) or presents one or more 3D hexagons (see third image).
</p>
<img src="/cookbook/map/img/10-48.png" />
<img src="/cookbook/map/img/10-49.png" />
<img src="/cookbook/map/img/10-50.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>30a.</b> <b>Flat object with no 3D data hexagons</b>. The base of the object is narrower than its top. For this reason, for optimal printing, you need to flip it, so that the wider part (the top) will sit on the printer’s bed. To do so, click on the object (it will turn green) and navigate through <code>Object > Rotate > Around Y axis</code>. In the dialog box that appears, type in a rotation angle of <code>180°</code>.  
</p>
<img src="/cookbook/map/img/10-51.png" />
<img src="/cookbook/map/img/10-52.png" />
<img src="/cookbook/map/img/10-53.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>30b.</b> <b>Object with 3D data hexagons</b>. You don’t need to flip the object and can proceed with the next step.</p>
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>31a.</b> <b>Flat object with no 3D data hexagons</b>. In the dropdown menus on the right, change the values to match the following options:</p>
<ul style="font-size: 12px;"><li><code>Print settings >  0.20mm FAST</code>. This setting defines the height of each of the layers the objects gets sliced into for 3D printing. </li>
<li><code>Filament > PLA</code>. This setting defines the type of filament you will use to 3D print, and thus the temperature that the extruder has to reach in order to melt it and lay it.</li>
<li><code>Printer ></code> make sure the setup matches the printer you will use.</li>
<li><code>Fill density > 10%</code>. This value means that the only 10% of  the piece will be filled, resulting in a light object with minimal material use. Because this is a decorative element that won’t need to endure particular pressure, a 10% fill density is certainly enough.</li>
<li><code>Supports > none</code>. This because the object doesn’t require any printing supports for hanging parts.</li>
</ul>
<p style="font-size: 12px;">
When you have defined all these parameters, click on <code>Slice now</code>.
</p>
<img src="/cookbook/map/img/10-54.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>31b.</b> <b>Object with 3D data hexagons</b>. In the dropdown menus on the right, change the values to match the following options:</p>
<ul style="font-size: 12px;">
<li><code>Print settings >  0.20mm FAST</code>. This setting defines the height of each of the layers the objects gets sliced into for 3D printing. </li>
<li><code>Filament > PLA</code>. This setting defines the type of filament you will use to 3D print, and thus the temperature that the extruder has to reach in order to melt it and lay it.</li>
<li><code>Printer > </code> make sure the setup matches the printer you will use.</li>
<li><code>Fill density > 10%</code>. This value means that the only 10% of  the piece will be filled, resulting in a light object with minimal material use. Because this is a decorative element that won’t need to endure particular pressure, a 10% fill density is certainly enough.</li>
<li><code>Supports > Support on build plate only</code>. This because the base of the object is narrower than the top, but we can’t flip it since there are 3D hexagons on the top. Setting this parameter will create supports for the hanging part of the base.</li>
</ul>
<p style="font-size: 12px;">
When you have defined all these parameters, click on <code>Slice now</code>.
</p>
<img src="/cookbook/map/img/10-55.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>32a.</b> <b>Flat object with no 3D data hexagons</b>. Click on the <code>Preview</code> tab, from the lower left side of the window. This will show you a preview of the movements the machine will make. You can play with the sliders on the right to check if the output is as desired.
</p>
<img src="/cookbook/map/img/10-56.png" />
<img src="/cookbook/map/img/10-57.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>32b.</b> <b>Object with 3D data hexagons</b>. Click on the <code>Preview</code> tab, from the lower left side of the window. This will show you a preview of the movements the machine will make. You can play with the sliders on the right to check if the output is as desired. As you can see there are some green lines: they represent the supports you created in the previous step.
</p>
<img src="/cookbook/map/img/10-58.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>33.</b> Click on the <code>Export G-code</code> button on the right and save the file.
</p>
<img src="/cookbook/map/img/10-59.png" />
<img src="/cookbook/map/img/10-60.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">