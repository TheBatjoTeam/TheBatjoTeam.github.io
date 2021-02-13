---
layout: r-tutorials
title: Data Walk
language: en
slug: data-walk
chapter-title: 3D Modeling
chapter: model
section: 1
section-title: "The data curves"
previous: model
next: model2
next-text: "3D Modeling · Part 2   "  
video: "yes"
video-link: "https://player.vimeo.com/video/305384542"
download: "yes"
download-name: "final 3D modeling"
download-link: "https://github.com/TheBatjoTeam/data-walk/tree/master/3d_model"
output-image: "/cookbook/data-walk/img/1-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. After opening FreeCAD and creating a new project by clicking on <code>File > New</code>, open the <code>Spreadsheet Workbench</code>, as shown in the image, by clicking on the dropdown menu where you now see Start. This workbench contains all the commands related to working with data.</p>
<img src="/cookbook/data-walk/img/1-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Import the data into the project by clicking through <code>File > Open</code>. Data can be in .CSV or .XLSX format.

<em><b>Note</b> on .CSV files: while the file extension has to be .CSV in order for the file to be imported, the data actually has to be in.TSV format (tab-separated, not commas). Otherwise, the columns won't be separated correctly.</em>"</p>
<img src="/cookbook/data-walk/img/1-2.png" />
<img src="/cookbook/data-walk/img/1-3.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Create an alias for each cell. This will allow you to bind each value of the data to a physical characteristic of the object (length, width, etc.). Assigning aliases implies manually clicking on each cell containing the data you want to plot (excluding the header row and the first column with the row names) and typing a label name to reference it by.  Despite being a manual task, the operation is quite quick. Yet, it will become quite burdensome if your spreadsheet has hundreds of cells or more. In this case you will need to resort to other techniques, like using FreeCAD MACROS and plugins, or going for another software like Blender<sup>1</sup>.  To make things easier on yourself, when choosing the aliases, give meaningful names that follow a logic order (a1, a2, a3; b1, b2, b3; etc.): you will need to reference them again further on. To assign an alias, right-click on a cell and select <code>Properties</code> Then, click on the <code>Alias</code> tab and type in the name. The cell will now be highlighted in yellow.
<br>
<sup>1</sup> The easiest way is actually to directly import a 2D .SVG line chart. The technique is not proposed for this tutorial because it is useful to learn how to bind data to object's geometries from scratch, regardless of the shape of the object/chart, so that the same process can be used to produce any data-driven shape. If you wish however to go for the quickest route, in this case you can read and adapt <a href="/cookbook/map/model1/">our other tutorial</a> to learn how to import and extrude a .SVG file in FreeCAD (read on from step 7 of the linked tutorial). 
</p>
<img src="/cookbook/data-walk/img/1-4.png" />
<img src="/cookbook/data-walk/img/1-5.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Move to the <code>Part Design Workbench</code> by clicking through the dropdown menu where you now see Spreadsheet. This workbench groups all commands used to model the single parts of the object. Once you have opened this workbench, you need to create a new body (the container for your design) and a new sketch (the 2D drawing of your object). To do this, first click through the menu <code>Part Design > Create Body</code>, then through <code>Part Design > Create Sketch</code>.
Once you've done this, select the <code>XY Plane</code>< from the code>Combo View Panel</code> that should have appeared on the left side of the screen and click <code>OK</code>.
</p>
<img src="/cookbook/data-walk/img/1-6.png" />
<img src="/cookbook/data-walk/img/1-7.png" />
<img src="/cookbook/data-walk/img/1-8.png" />
<img src="/cookbook/data-walk/img/1-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Select the <code>Sketcher Workbench</code>. Then, click through the menu <code>Sketch > Sketcher Geometries > Create Polyline</code>. You can now draw a shape similar to that in the image below. The shape should only approximately reflect the structure of your dataset. The number of points on the segments in the top line should be equal to the number of rows in the data, but that's about it: we'll fix everything else further on, from lengths to heights, straightness of lines, distances and the rest.  <br><em><b>Note</b>: to exit the draw mode and finish your shape or lines, you might need to press <code>ESC</code> on your keyboard.</em>
</p>
<img src="/cookbook/data-walk/img/1-10.png" />
<img src="/cookbook/data-walk/img/1-11.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. The next thing to do is to draw the lines that will serve as guides to position the elements correctly. To do so, you first switch to <code>Construction Mode</code>. <code>Construction Mode</code> allows you to draw lines that are not actually part of the object itself, but that only serve as modeling supports. To switch to <code>Construction Mode</code>, go through the menu <code>Sketch > Sketcher Geometries > Toggle Construction Geometry</code>.  If you have done this correctly, all the lines you now draw will be blue, rather than white. We now draw a grid of lines like in the first image below.  To get there, start by drawing a series of segments running parallel to the base line, each segment starting and ending roughly above the start and end of each segment of the 'line chart'. You can draw such segments by clicking through the menu <code>Sketch > Sketcher Geometries > Create Polyline</code>. You now select all segments by clicking on each of them (selected elements turn green) and then apply the <code>Equality Constraint</code>, so that they are all the same length. The second  image below shows you where to find the constraint commands (the Equality Constraint is represented by the red equal sign), otherwise navigate through <code>Sketch > Sketcher constraints > Constrain equal</code>.
At this point, you need to draw lines connecting the first point of each of these segments to the first point of each segment of the ‘line chart’. These vertical line are the blue ones you see in the image below. To draw such lines, make sure they start and end on the points of the two segments. You'll know you are in the right start or end spot because the points turn yellow when your cursor is over them. You might also need to zoom in closer to make sure you are connecting them. Just like you had done with the green horizontal lines, you now select all of them and apply a constraint, only this time it is the <code>Vertical Constraint</code> (<code>Sketch > Sketcher constraints > Constrain horizontal </code>), as you want the line to be a straight line connecting the top segments to the segments in your line chart.
To know if the drawing is as it should be, check if all the top horizontal segments have a small red equal sign on the top and a red horizontal bar; and all vertical segments have a small vertical red line at the side, like in the image below. Thanks to this process, all the points in the line chart are at equal distance along the line and you can proceed to bind the data to these points.
</p>
<img src="/cookbook/data-walk/img/1-12.png" />
<img src="/cookbook/data-walk/img/1-13.png" />
<img src="/cookbook/data-walk/img/1-14.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. You will use a procedure similar to the one of the previous step to make sure that the distance of the points from the base corresponds to the data value they represent. To do this, first of all draw a segment connecting each point of the line chart to the base, through the command: <code>Sketch > Sketcher Geometries > Create Line</code>. You will know the segment is connected to the base if you draw the line until the base segments becomes highlighted in yellow. You then assign to all these vertical lines the <code>Vertical Constraint</code> you used before, as you want the segment to form a straight line connecting the points in the line chart to the base.
Now you assign another constraint to these lines, the <code>Vertical Distance Constraint</code> (<code>Sketch > Sketcher constraints > Constrain vertical distance</code>), as you want these line to be as long as the data value the points represent. You start by selecting the first vertical line on the left and by clicking on the constraint that lets you fix the vertical distance between two points. A pop-up window will now appear asking you the length. Type in the name of the spreadsheet followed by a dot (in this case <code>Spreadsheet.</code>) followed by the alias of the cell that the selected point should stand for (<code>w1</code> in the image).
Note that by default the values in your data are converted to millimeters. If you have very large or small numbers, you might want to scale them by dividing or multiplying all of them by multiples of 10 (or whatever number you wish, as long as all the data points are scaled by the same number). 
You repeat this step for all the row of the dataset/vertical lines of your sketch. The end result will resemble the second of the image below.
</p>
<img src="/cookbook/data-walk/img/1-15.png" />
<img src="/cookbook/data-walk/img/1-16.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Now that you have defined the height of the object, you will define its width. Since this is meant as a walkable object, you want the distance between two points to be roughly the distance of a step (<code>73cm</code>). Of course, this is a rule of the thumb and you will need to come to terms with other constraints, like the amount of space you have available and the number of datapoints in your spreadsheet. For example, if you have few datapoints and want a big object, you will go for a higher number; likewise, if you have many datapoints and need a smaller object, you will go for a smaller number. To set the width, select the base line of the object and click on the <code>Vertical Constraint</code>. In the pop-up that appears, type in <code>730 * [the_number_of_datapoints - 1]</code>.
</p>
<img src="/cookbook/data-walk/img/1-17.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. At this point, you will add 3 protruding ridges to the base of your shape. These elements will let you fit the object onto its base, like a puzzle, when you will assemble it. First delete the current base segment. Then, through the menu <code>Sketch > Sketcher Geometries > Create Polyline</code>, draw the shape as shown in the picture, approximately. Thirdly, apply constraints to make the top horizontal lines of the same length (select them and pick <code>Equality Constraint</code>), then the three bottom horizontal lines of the same length (select them and pick <code>Equality Constraint</code>) and finally the vertical lines of the same height (select them and pick <code>Equality Constraint</code>). At this point, you want to make the three ridges  of the same height as the depth of the material you are using as a base. In our case, <code>20mm</code>. To do so, select any one of these short vertical segments, choose the <code>Vertical Distance Constraint</code> and type in a value of <code>20mm</code>. At this point, you have drawn the basic shape and you can exit the Sketch by clicking through the menu <code>Sketch > Leave Sketch</code>.
</p>
<img src="/cookbook/data-walk/img/1-18.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. Now that you have built the model for representing the first data series, need to create the model for the second data series. Luckily, you don't need to repeat all the steps. Select the <code>Body</code> component from the left sidebar and copy-paste it. Then, right-click on the first <code>Body </code>component from the left sidebar and select <code>Hide Selection</code>. At this point, all you need to do is edit the vertical constraints assigned in point 7 so that they instead match the aliases of the second data series. When you're done, exit the Sketch by clicking through the menu <code>Sketch > Leave Sketch</code>. You can temporarily unhide the first curve again to see the two side-by-side for comparison.
</p>
<img src="/cookbook/data-walk/img/1-19.png" />
<img src="/cookbook/data-walk/img/1-20.png" />
<img src="/cookbook/data-walk/img/1-21.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. Now it is the moment to transform the line charts into a curve - as this will facilitate how people will walk on it. If you prefer to keep the lines straight, you may skip this step. Select the <code>Draft Workbench</code> and then go through the menu <code>Draft > Utilities > Select Plane</code>. This will let you pick which plane to position your bi-dimensional object on. From the panel that appears on the left side, select the <code>XZ plane</code>. To generate the curve, click through <code>Draft > B-spline</code>. At this point, move the cursor so that it is next to the first point of the line chart, that representing the first datapoint, and click. You will know that you are selecting that point because the segment next to it turns orange and small turquoise icon of a point and a line will appear. Move the cursor to the next point and click. Repeat this for all points of the line. Once you are done, hover your mouse over to the left sidebar and click <code>Close</code> from the <code>B-spline panel</code>.  Once you’ve drawn this first curve, you need to design the bottom of the object, because the spline you have designed, while it did use the previous lines of the sketch as a guide, is in fact a new object. To complete this spline curve into a polygon, go through the menu and select <code>Draft > DWire</code>. You now move your cursor to complete the shape following the white lines of your sketch, like you did to draw the B-Spline, with the difference that now the lines are straight.  When you are done, you need to join the two elements (the <code>DWire</code> lines and the <code>B-spline</code> curves) into a single one. To do this, go to the left-hand panel where you see the <code>BSpline</code> element and the <code>DWire</code> elements and select them both (by <code>Shift-click</code>). Then click on the blue arrow icon pointing upwards, or by clicking through the menu <code>Draft > Upgrade</code>. You will know you have achieved this successfully because the left sidebar panel, where before you saw the <code>BSpline</code> element and the <code>DWire</code> elements, now only has a <code>Wire</code> element. 
Hide this <code>Wire</code> element  and the corresponding <code>Sketch</code> element by right-clicking on each and selecting <code>Hide Selection</code> from the menu that appears. Now select the other sketch, the one representing the other data series. It should have been hidden, so right-click on it and select <code>Show Selection</code> from the menu that appears. At this point repeat the drawing of the <code>B-Spline</code> and <code>DWire</code>, and then their <code>Upgrade</code>, like you did for the previous curve.
</p>
<img src="/cookbook/data-walk/img/1-22.png" />
<img src="/cookbook/data-walk/img/1-23.png" />
<img src="/cookbook/data-walk/img/1-24.png" />
<img src="/cookbook/data-walk/img/1-25.png" />
<img src="/cookbook/data-walk/img/1-26.png" />
<img src="/cookbook/data-walk/img/1-28.png" />
<img src="/cookbook/data-walk/img/1-29.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. In this step, you will transform the curves from bi-dimensional drawings to models of solid shapes. Move to the <code>Part Workbench</code> and then select one of the two <code>Wire</code> objects from the left sidebar.  You might want to change the view so that you are able to see the 3rd dimension. To do so, click on through <code>View > Standard Views > Axonometric</code>. Then click through the menu <code>Part > Extrude</code>. On the panel that appears on the left, under <code>Length</code>, type in <code>20mm</code> and then click <code>OK</code>. This because the curves will be carved out of layers of wood sheets, each being <code>20mm</code> in thickness. If you are using another material or sheets of another thickness, type in that amount. Repeat this extrusion for the other curve.
</p>
<img src="/cookbook/data-walk/img/1-30.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>13</b>.  In the end, the curve object has to be wide and stable enough so that people can walk on it. To achieve this, the curves will be formed by placing 10 of the 20mm-thick sheets of wood. These sheets will be positioned 10mm apart, so that the object is stable but requires less wood material than a completely full volume.  To insert a gap between the curves, switch to the <code>Draft Workbench</code>.  On the left sidebar, select the first <code>Extrude</code> element. On the panel below, where you see the buttons <code>View</code> and <code>Data</code>, click on <code>Data</code>. 
In the grid that appears, open the <code>Placement</code> element and then the <code>Position</code> element nested inside. Once the <code>xyz</code> coordinate values appear (they should all be zero now), type in <code>-10mm</code> for the <code>y</code>.
</p>
<img src="/cookbook/data-walk/img/1-31.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>14</b>. On the left sidebar, select again the first <code>Extrude</code> element. Then go through <code>Draft > Array</code>. On the panel below, where you see the buttons <code>View</code> and <code>Data</code>, click on <code>Data</code>, if it’s not already selected.  
In the grid that appears, change the following variables to match the following values:</p>
<p style="font-size: 12px;"><ul style="font-size: 12px;">
<li><code>Number X</code> : <code>1</code></li>
<li><code>Number Y</code>: <code>10</code></li>
<li><code>Number Z</code>: <code>1</code></li>
<li><code>Interval Y</code>: <code>-40.00mm</code><sup>1</sup></li>
</ul></p>
<p style="font-size: 12px;">You will now have a series of curve objects like in the picture below. You might want to change the view so that you are able to see the 3rd dimension. To do so, click on through <code>View > Standard Views > Axonometric</code>.
<br><sup>1</sup>assuming you are working with sheets of 20.00mm.
</p>
<img src="/cookbook/data-walk/img/1-32.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>15</b>. Select the second Extrude element and repeat the previous two steps (13 and 14), In step 15, once the <code>xyz</code> coordinate values appear (they should all be zero now), you will need to type <code>10mm</code> (not -10mm) as the value for the <code>y</code>. In step 14, when typing in the values for this second <code>Extrude</code> element in the <code>Data</code> panel, change the following variables to match the following values :
</p>
<p style="font-size: 12px;"><ul style="font-size: 12px;">
<li><code>Number X</code> : <code>1</code></li>
<li><code>Number Y</code>: <code>10</code></li>
<li><code>Number Z</code>: <code>1</code></li>
<li><code>Interval Y</code>: <code>40.00mm</code><sup>1</sup> (not -40.00mm)</li>
</ul></p>
<p style="font-size: 12px;">You will now have a series of two curve objects like in the picture below. You might want to change the view so that you are able to see the 3rd dimension. To do so, click on through <code>View > Standard Views > Axonometric</code>.
<br><sup>1</sup>assuming you are working with sheets of 20.00mm.
</p>
<img src="/cookbook/data-walk/img/1-33.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>16</b>. To make it easier to work on the two curves without confusion, and to get a clearer image of the possible final effect, you can color the two curves with distinct colors. This step does not have any implication on the design, it is just a visual effect that is useful during the 3D modeling session.
On the left sidebar, click on the first <code>Array element</code>. On the panel below, where you see the buttons <code>View</code> and <code>Data</code> at the bottom, click on View. 
In the grid that appears, you will see a variable called <code>Shape Color</code>. Edit it by selecting a color to your liking. Below <code>Shape Color</code>, there is the variable <code>Transparency</code>. Type in a value lower than 100 (for example 50), so that you will be able to see both curves even when one is in front of the other. Do the same for the second <code>Array</code> element.
</p>
<img src="/cookbook/data-walk/img/1-34.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>17</b>. Switch back to the <code>Part Workbench</code>. Select both <code>Array</code> elements from the left panel and join them into a single object by going through the menu <code>Part > Boolean > Union</code>. You will see that this has been carried out correctly because you now have a single <code>Fusion</code> element in place of the two different <code>Array</code> elements. When selecting the <code>Fusion</code> element from the left sidebar, you will also notice that the whole object, with both curves, gets selected.
</p>
<img src="/cookbook/data-walk/img/1-35.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">