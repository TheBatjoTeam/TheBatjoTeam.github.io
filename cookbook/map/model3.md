---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter: model
chapter-title: 3D Modeling
section: 3
section-title: "The two 3D data layers"
previous: model2
next: model4
next-text: "3D Modeling · Part 4"  
video: "yes"
video-link: "https://player.vimeo.com/video/305841662"
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/map/tree/master/3d_model"
output-image: "/cookbook/map/img/4-output.png"
---

<div>
<p style="font-size: 12px;">
<b>0</b>. As a prerequisite, you need to have installed the <a href="https://github.com/domlysz/BlenderGIS">BlenderGIS Addon</a>, which will allow you to open geo data in Blender.
</p>
<img src="/cookbook/map/img/4-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>1</b>. Open the software Blender. <b>Note that you need a mouse in order to use Blender</b>. Additionally, because the interface could be rather confusing to novice users, we’ll use keyboard shortcuts rather than guiding you through the exact location of buttons and commands. In you are interested in the actual buttons and menus clicked, have a look at the full video. The default layout presents a cube, a light source (represented by the black dot) and a camera (represented by the transparent cone). As a first thing, you need to delete these three things by selecting them and hitting the delete key. Note that, in Blender, you select objects by right-clicking on them (not the usual left-click).  You will end up with only the XY plane in the layout window.
</p>
<img src="/cookbook/map/img/4-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Import the .STL map you had previously modeled in FreeCAD. It will serve as guidance as to where to position the data layers. To do so, click through <code>File > Import > Stl</code> and select the appropriate file.
</p>
<img src="/cookbook/map/img/4-3.png" />
<img src="/cookbook/map/img/4-4.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Import the first .SHP file map layer, the one with the hexagon grid map filtered for the negative values. Do so by going through the menu <code>File > Import > Shapefile</code>. (You won’t see this option if you don’t have the BlenderGIS addon installed). In the pop-up window that appears, fill in the following options and click <code>OK</code>.</p> 
<ul style="font-size: 12px;">
<li><code>Extrusion from field</code>: tick the checkbox</li>
<li><code>Field</code>: choose the filed name of the variable containing the absolute value of the attribute you want to use for elevation</li>
<li><code>Extrude along: Z axis</code></li>
<li><code>Separate objects</code>: tick the checkbox</li>
<li><code>CRS</code>: select the appropriate CRS (matching the CRS in which you exported the layer) </li>
</ul>
<p style="font-size: 12px;">
<b>By default, all the hexagonal polygons you have just imported will be select. Do not deselect them</b>.  </p>
<img src="/cookbook/map/img/4-5.png" />
<img src="/cookbook/map/img/4-6.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. After the import, the camera will be very zoom out, in order to include the new file in view, and you might not see the .stl map you imported in step 4. Don’t worry, it’s still there and in this step you will scale the hexagonal polygon layer to the same size as the .stl map. Start by choosing a top view, by clicking on the key <code>7</code> on the keyboard. Then press the <code>Z</code> key to switch to <code>Wireframe mode</code>. In this visualization mode, the polygons become transparent and so you can see the map below to match their position. Press the <code>S</code> key on your keyboard, which activates the scale command. Move your mouse cursor until you achieve the desired size, so that the polygons match the shape of the map below. In the course of the scaling process, you might need to stop and readjust the position of the hexagonal grid. You can do so by pressing the <code>G</code> key and moving the cursor to move the object and then pressing the <code>S</code> key again to scale it further.
</p>
<img src="/cookbook/map/img/4-7.png" />
<img src="/cookbook/map/img/4-8.png" />
<img src="/cookbook/map/img/4-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Press the <code>A</code> key to deselect your hexagonal polygons. Delete any of the hexagonal polygons that are outside of the square map area, as they are not part of the map you will send in production. You can delete them faster by activating a box selection by pressing <code>B</code> on your keyboard. The selection might take a bit to process depending on its size. When the polygons are selected they’ll turn orange and you can press the <code>delete</code> key to remove them.
</p>
<img src="/cookbook/map/img/4-10.png" />
<img src="/cookbook/map/img/4-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Select the .stl base map and make it hidden and not selectable by clicking on the eye icon and on the cursor icon shown in the first image below. Press <code>Z</code> again to switch from <code>Wireframe</code> mode to <code>Solid mode</code> and see what the 3D hexagon grid with negative values looks like.  If you navigate to the bottom of the grid, you will see that these hexagons don’t have a base. You will need to fix these holes in the mesh because digital fabrication machines, unlike digital 3D visualizations, need complete solids to work with. 
</p>
<img src="/cookbook/map/img/4-12.png" />
<img src="/cookbook/map/img/4-13.png" />
<img src="/cookbook/map/img/4-14.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Select all the hexagonal polygons by pressing the <code>A</code> key. Hit the <code>spacebar</code> and a search box will appear. Search for <code>join</code> and click on <code>Object:Join</code> among the search results. This will transform all the single hexagonal polygons into a single object. Press the <code>Tab</code> key, to switch into <code>Edit mode</code>. You will know that you are in <code>Edit mode</code> because the edges of your objects will have turned black. <code>Edit mode</code> allows you to interact and modify the structure of the mesh. 
</p>
<img src="/cookbook/map/img/4-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Select all the hexagonal polygons again by pressing the <code>A</code> key.  Then press the <code>F</code> key to activate the <code>Face</code> command, which automatically generates a face to fill all the vertices that are not yet connected. In practice, this will create a base to close all the 3D hexagonal polygons and transform them into complete hollow solids. 
</p>
<img src="/cookbook/map/img/4-16.png" />
<img src="/cookbook/map/img/4-17.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Press the <code>Tab</code> key again to exit the <code>Edit mode</code> and switch to <code>Object mode</code>. On the right-hand panel you will find the icon to access the <code>Modifiers</code> menu, which resembles a wrench (see image below). Click on it and go to the <code>Add Modifier</code> dropdown menu. Select the <code>Triangulate</code> modifier and then click the <code>Apply</code> button. Modifiers are algorithms/commands that modify the mesh. The <code>Triangulate</code> modifier splits the polygons of the selected mesh into triangles. In short, this command allows you to generate a more complex, detail-dense mesh, making it less likely to trigger glitches when imported in other software. You can check that the triangulation took place efficiently by clicking the <code>Tab</code> key and verifying that the mesh is now made up of triangles. 
</p>
<img src="/cookbook/map/img/4-18.png" />
<img src="/cookbook/map/img/4-19.png" />
<img src="/cookbook/map/img/4-20.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. Hit the <code>spacebar</code> and a search box will appear. Search for <code>separate</code> and click on <code>Mesh:Separate</code> among the search results. On the pop-up that appears, select the <code>By loose parts option</code>. As a result, the hexagons will go back to being single objects, canceling the join you had applied in step 9. (The reason of the join was solely to apply the <code>Face</code> and <code>Triangulate</code> commands once, rather than for each hexagonal polygon).
</p>
<img src="/cookbook/map/img/4-21.png" />
<img src="/cookbook/map/img/4-22.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Press the <code>A</code> key to select all polygons again. On the <code>Transform</code> menu on the left side of the screen, click on the <code>Mirror</code> command. When the command becomes active, press the <code>Z</code> key to mirror it along the XY plane. The reason for this is that this layer represents the negative values, which will go below the map.
</p>
<img src="/cookbook/map/img/4-23.png" />
<img src="/cookbook/map/img/4-24.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. As a final check, unhide the base by clicking the hide icon shown in the image below. You can now double check that the data hexagons are correctly positioned in regard to the base map.
</p>
<img src="/cookbook/map/img/4-25.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>13</b>. Select all the hexagons by pressing the <code>A</code> key. To save the file, go through <code>File > Export > Wavefront (.obj)</code>. When the save as window opens up, there will be a few options on the left panel. Leave everything with the default values, except:</p>
<ul style="font-size: 12px;">
<li><code>Up</code>:  choose <code>Z Up</code></li>
<li><code>Selection only</code>: checkbox checked</li>
</ul>
<p style="font-size: 12px;">
Refer to the image below to see what all the options should look like. Then click on <code>Export obj</code> from the top right corner.  Then, also save your file as a Blender project, with the <code>.blend </code>extension, by going through <code>File > Save as</code>.
</p>
<img src="/cookbook/map/img/4-26.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>14</b>. Hide the mesh with negative values hexagons by clicking on the eye icon and make it not selectable by clicking on the cursor icon shown in the image below. You are now ready to work with the positive values layer.
</p>
<img src="/cookbook/map/img/4-27.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>15</b>. Repeat steps 3 to 12 of this tutorial section, only by uploading the .SHP file with the map layer filtered for positive values. Then, skip step 13 and proceed with step 14 and 15 to complete the 3D modeling of the positive and negative data layers.
</p>
<img src="/cookbook/map/img/4-28.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>16</b>. Switch software and open FreeCAD. These last steps are needed to attach the hexagon polygons onto a thin support base, so that they can then be 3D printed. Create a new project by going through <code>File > New</code>. Then import the first file (the one with negative values) by going through <code>File > Import</code>. In the select module that appears, select <code>Wavefront OBJ - Arch module (importOBJ)</code>.
</p>
<img src="/cookbook/map/img/4-29.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>17</b>. When the import is complete, you will see a series of elements on the left sidebar (names will vary depending on the name of the .shp files you first imported in Blender). These elements, while present on the sidebar, will not yet be visible in the view. Move to the <code>Part Workbench</code>. To make the elements visible, select them all from the left sidebar panel and click through <code>Part > Create shape from mesh</code>. A pop-up window will ask you to fill in a value for <code>sewing tolerance</code>. Leave the default option (0,10). The result will be a solid generated from the mesh you had exported from Blender.  Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the <code>Mesh</code> elements from the left sidebar (they have a small greenish icon next to their name) and leave only the <code>Shape</code> elements (blue icon).
</p>
<img src="/cookbook/map/img/4-30.png" />
<img src="/cookbook/map/img/4-31.png" />
<img src="/cookbook/map/img/4-32.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>18</b>. Now select all the <code>Shape</code> elements from the left sidebar and go through the menu <code>Part > Refine shape</code>. Wait a few seconds for the process to end. Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the older <code>Shape</code> elements from the left sidebar and leave only the new refined <code>Shape</code> elements. 
</p>
<img src="/cookbook/map/img/4-34.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>19</b>. Now select all the refined <code>Shape</code> elements from the left sidebar and go through the menu <code>Part > Convert to solid</code>. Wait a few seconds for the process to end. Without deselecting the previously selected elements, hit the <code>delete</code> key to remove all the refined Shape elements from the left sidebar and leave only the new refined <code>Shape</code> elements - you’ll recognize them because they have the suffix <code>(solid)</code> appended at the end of the name. In practice, all these latter steps have left the shapes visually unchanged. What has been modified is the mathematical structure used to generate them, so that now they can be easily used for digital fabrication.
</p>
<img src="/cookbook/map/img/4-35.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>20</b>. Switch to the <code>Part Design workbench</code> to create the base on which the hexagons will sit. Create a new body (the container for your design) and a new sketch (the 2D drawing of your object). To do this, first click through the menu <code>Part Design > Create Body</code>, then through <code>Part Design > Create Sketch</code>. Select the <code>XY</code> plane from the left sidebar menu.
</p>
<img src="/cookbook/map/img/4-36.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>21</b>. You should now have been directly redirected to sketch editing mode, or the <code>Sketcher Workbench</code>. Click through the menu <code>Sketch > Sketcher Geometries > Create rectangle</code>. You can now draw a rectangle/square similar to that in the image below. Don’t worry about dimensions, we'll fix them else further on.
</p>
<img src="/cookbook/map/img/4-37.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>22</b>. Now select the top segment of the rectangle by clicking on it (selected elements turn green) and then apply the <code>Horizontal Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal distance</code>). A pop-up window will prompt you to fill in the length value of the selected segment. Type in <code>500 mm</code> (remember, the base is a 50x50cm block).  At this point, you want to apply the <code>Equality Constraint</code> between this top segment and one of the side segments. This constraint forces the sides of the rectangle to be the same length as the top and bottom, and will result in your shape becoming a 50x50 cm square. To apply this constraint, select the top segment of the rectangle and the right side segment. Click through <code>Sketch > Sketcher constraints > Constrain equal</code>.
</p>
<img src="/cookbook/map/img/4-38.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>23</b>. Position the square at the center of your plane. To do so, select the origin point and one of the corners of the square. Apply the <code>Horizontal Distance Constraint</code> and type in <code>250mm</code>. Select the origin and corner of the square again, and now apply the <code>Vertical Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal distance</code>). Type in <code>250mm</code> in the pop-up window that appears. Close the Sketch.
</p>
<img src="/cookbook/map/img/4-39.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>24</b>. Select the sketch from the left side panel (see image below). Change to the <code>Part Workbench</code>. Go through the menu <code>Part > Extrude</code>. In the left panel you will be asked to type in a <code>Length Along</code> parameter. Fill it in with <code>6 mm</code> (the height of the wooden sheet you will use as a support layer for the data + a minimal height of 3mm for the 3D printed layer of hexagons). Leave the other parameters as they are and click <code>OK</code>.
</p>
<img src="/cookbook/map/img/4-40.png" />
<img src="/cookbook/map/img/4-41.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>25</b>. Change view by going through <code>View > Standard Views > Front</code>. Select the <code>Extrude</code> element from the left side panel.  Navigate to the <code>Data</code> menu at the bottom of the left panel sidebar. Go to the <code>Placement > Position > Z</code> and increase/decrease the value until its sits right below the hexagonal polygon objects (in our case, we had to use a value of  <code>-26.5 mm</code>). 
</p>
<img src="/cookbook/map/img/4-42.png" />
<img src="/cookbook/map/img/4-43.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>26</b>. From the left sidebar select both the square base and the 3D hexagon solids. Click through <code>Part > Boolean > Union</code>. This might take a bit, depending on your CPU. You will now have a single <code>Fusion</code> element in your left sidebar, grouping all the other elements. 
</p>
<img src="/cookbook/map/img/4-44.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>27</b>. Move to the <code>Part Design workbench</code>. Select the <code>Fusion</code> element and click on <code>Part Design > New body</code>. This will create a new container body element that uses the selected <code>Fusion</code> element as base. 
</p>
<img src="/cookbook/map/img/4-45.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>28</b>. Click on the top face of the object from the 3D view to select it. Then go through the menu <code>Part Design > New Sketch</code>. This will create a new sketch on top of the face you had selected.
</p>
<img src="/cookbook/map/img/4-46.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>29</b>. As you can see, some hexagonal polygons overflow the boundaries of the 50x50 cm square base, and we need to cut them out. Go through the menu <code>Sketch > Sketcher geometries > External geometry</code>. Then click on the top and bottom segments of the base square to select them. This will import the selected segments as guidelines in the sketch. Now click on <code>Sketch > Sketcher geometries > Rectangle</code> and draw a square as big as the square base of your object. Then draw another square or rectangle; the dimensions don’t matter as long as it is bigger than the hexagon layer (see image below). Close the sketch. Go through the menu <code>Part Design > Pocket</code>. Fill in the following options on the left menu that appears:</p>
<ul style="font-size: 12px;">
<li><code>Type > Through all</code></li>
<li><code>Symmetric to plane</code>: checkbox checked</li>
</ul>
<p style="font-size: 12px;">
Click <code>OK</code> to apply the <code>Pocket</code> command. The hexagonal solids will now be clipped to the margins of the 50x50 cm square.
</p>
<img src="/cookbook/map/img/4-47.png" />
<img src="/cookbook/map/img/4-48.png" />
<img src="/cookbook/map/img/4-49.png" />
<img src="/cookbook/map/img/4-50.png" />
<img src="/cookbook/map/img/4-51.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>30</b>. Select the last Body element from the left sidebar, the one containing this last object created. Go through <code>File > Export</code>. Select .STL as the file type and export your project.
</p>
<img src="/cookbook/map/img/4-52.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>31</b>. Repeat steps 16 - 30 with the second data layer (the one with positive values).
</p>
<img src="/cookbook/map/img/4-53.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">