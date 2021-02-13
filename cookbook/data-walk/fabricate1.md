---
layout: r-tutorials
title: Data Walk
language: en
slug: data-walk
chapter: fabricate
chapter-title: Fabrication
section: 1
section-title: "The two data curves and the base support (CNC milling GCode)"
previous: fabricate
next: fabricate2
next-text: "Fabrication · Part 2"
download: "no"
video: "yes"
video-link: "https://player.vimeo.com/video/305380160"
output-image: "/cookbook/data-walk/img/4-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. Extract the unique basic shapes of the final object. In this case there are three of them: the engraved base (1), one of the ten curves representing the first data series (2), and one of the ten curves representing the second data series (3). So first, hide all elements except these three. You can tap the <code>spacebar</code> to quickly hide the element selected on the left sidebar. </p>
<img src="/cookbook/data-walk/img/4-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Switch to the <code>Draft Workbench</code>. Select the one of the two data curves and clone it through the menu <code>Draft > Clone</code>. Repeat the same procedure to create a clone also for the other data curve and for the base. This way, from now on you will work and perform commands only on these cloned elements independently, without the risk of messing up the original design. Now hide everything except these three cloned elements.</p>
<img src="/cookbook/data-walk/img/4-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. We now start working on each single one of these three elements, to prep them for fabrication via CNC milling machine. You will start with one of the two data curves, so hide the other one and the base. The curve is now in a vertical position on the XZ plane. Since it will be carved out from a wood sheet laying flat horizontally, you need to move the curve so that it lays flat on the XY plane. To achieve this, select the curve and click though <code>Draft > Utilities > Select plane</code>. On the selection panel that appear on the left, select <code>YZ plane</code>. Navigate to the right view (<code>View > Standard views > Right</code>). Rotate the selected object (<code>Draft > Rotate</code>). Click-select the bottom right corner as the starting point of your rotation. Hold down the <code>Shift</code> key, so that your mouse movements are snapped along the Z axis. Move the mouse upwards so that a black lines appears along the right edge of your shape. Click anywhere above the starting point and release the <code>Shift</code> key. Now, when you move the cursor, the shape will begin to rotate towards the X axis. Hold down the <code>Shift</code> key again, and the shape will rotate exactly by 90°. Click again anywhere and the rotation will be complete, resulting in an output like the one in the last of the images below. </p>
<img src="/cookbook/data-walk/img/4-3.png" />
<img src="/cookbook/data-walk/img/4-4.png" />
<img src="/cookbook/data-walk/img/4-5.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Switch viewpoint so that you are now in vertical view, by going through <code>View > Standard views > Top</code>. Switch to the <code>Path Workbench</code>. This workbench allows you to generate the machine-readable paths that instruct the CNC milling machine on the movements necessary to replicate the designed object.</p>
<img src="/cookbook/data-walk/img/4-6.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Select the curve object and go through the menu <code>Path > Job</code>. In the dialog box that appears, leave the default options and click OK. 
</p>
<img src="/cookbook/data-walk/img/4-7.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. A transparent rectangle enclosing your shape should have appeared on the main window. 
The rectangle is called “stock” and it represents the area of space from which the shape will be carved out or engraved. At the same time, a new selection panel on the left sidebar has appeared. In this panel, you need to set the size of the margins you want to apply around your shape. The boundaries of the shape plus these margins define the size of the stock. In this case, we apply a margin of <code>10mm</code> on both the <code>X axis</code> and <code>Y axis</code>. For the <code>Z axis</code>, on the other hand, we apply a margin of <code>0 mm</code>. This way, the machine will cut all the way to the bottom of the sheet of wood. Once you have defined to stock, you need to define the origin point of the machine’s movements. With your mouse, select the bottom left corner of the stock and click on the command <code>Set Origin</code> from the left selection panel. If this has been carried out correctly, you will notice that the Cartesian plane with the red, green and blue arrows has moved so that its origin corresponds to the corner you have just set as the origin. See image below for clarification. 
</p>
<img src="/cookbook/data-walk/img/4-8.png" />
<img src="/cookbook/data-walk/img/4-9.png" />
<img src="/cookbook/data-walk/img/4-10.png" />
<img src="/cookbook/data-walk/img/4-11.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. At this point, you have to declare what type of milling tool you are going to use to perform the cutting operation. Go through the menu <code>Path > Tool Manager</code>. A pop-up window will appear, with a tool library containing information on several milling tools their technical characteristics. Note that this library is build manually and gradually, as you add new tools you need to work with. In your case, thus, it is likely that the pop-up window will show you an empty library. To add a new tool to the library, click on <code>New Tool</code>. You will be promoted with a form that allows you to define the specs of the tool you will be using and add it to your tool library. For this project, you will need to define a milling tool that has at least the following specs: a type of <code>EndMill</code> and a diameter of <code>3mm</code>, as shown in the last of the following images. Clicking on <code>OK</code> will add this tool to your tool library. Once the tool has been added to the library, mark the corresponding box in the tool library and click on <code>Create Tool Controller(s)</code>. This way, the specified tool will be exported along with the other path instructions and will be used by the milling machine for its cutting task.
</p>
<img src="/cookbook/data-walk/img/4-12.png" />
<img src="/cookbook/data-walk/img/4-13.png" />
<img src="/cookbook/data-walk/img/4-14.png" />
<img src="/cookbook/data-walk/img/4-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Select the object again and go through the menu <code>Path > Contour</code>. On both the dialog box and the left selection panel that appear, leave the default options and click <code>OK</code>. You will now notice some green lines around the shape you will cut. These lines are the path that the CNC machine will follow to cut out the shape from the sheet of wood you provide it with. 
</p>
<img src="/cookbook/data-walk/img/4-16.png" />
<img src="/cookbook/data-walk/img/4-17.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. Select the Contour from the left sidebar and go through <code>Path > Path Dressup > Dogbone Dress-up</code>. In short, this is essentially a way to compensate the fact that the milling tools are round, and thus would cut rounded corners unless you specify this command. 
</p>
<img src="/cookbook/data-walk/img/4-18.png" />
<img src="/cookbook/data-walk/img/4-19.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. At this point, you also need to instruct the machine to perform a <code>Tag Dress-up</code>. This is a way to assure that the cut-out object will stay fixed in place till the end of the cutting operation. This is achieved by instructing the machines to skip cutting certain small sections around the contour of the object, so that it stays locked into its frame. To apply this instruction, select the contour and click on <code>Path > Path Dressup > Tag Dress-up</code>. 
On the selection panel that appears on the left sidebar, you will be asked where to position the tags, their width, their height and their angle. You can leave most of the default position, as this is calculated by an algorithm that figures out the best one quite accurately. As for width and height, type in a value of <code>10mm</code>;  <code>45</code> for the angle and <code>0</code> for the radius. This is to make sure the tags are not too big, otherwise it becomes hard for you to remove the cut out piece from the original frame. The last of the following images shows you what the representation of a tag looks like in FreeCAD.
</p>
<img src="/cookbook/data-walk/img/4-20.png" />
<img src="/cookbook/data-walk/img/4-21.png" />
<img src="/cookbook/data-walk/img/4-22.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>11</b>. At this point, you’ve finished prepping the first piece for fabrication, and need to repeat the same steps 2 - 12 of this tutorial for the other 2 shapes: first for the second curve and then for the engraved base. When you get to the engraved base, remember that you can skip step 3, as the object is already laying flat horizontally. Finally, when you have generated the tag dress-up for the base, continue with the following steps of the tutorial: because of the engraved text, which is not a complete cut operation but an engraving, the base of the object will need some additional steps before being ready for the machine.
</p>
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>12</b>. From the base, select all the lines representing the object’s x axis ticks and click through the menu <code>Path > Pocket Shape</code>. On the left selection panel, leave all options with the default values, except for <code>Pattern</code>, where you should select <code>Offset</code>. The axis ticks should now have turned green. Repeat this step also for all the text that needs to be engraved (in this case, only the x axis tick labels, with the years). If you have a good CPU, you could also select and pocket all the text and graphics elements in one go.
</p>
<img src="/cookbook/data-walk/img/4-23.png" />
<img src="/cookbook/data-walk/img/4-24.png" />
<img src="/cookbook/data-walk/img/4-25.png" />
<img src="/cookbook/data-walk/img/4-26.png" />
<img src="/cookbook/data-walk/img/4-27.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>13</b>. Now you have to cut out the slits where the curves will be inserted. Select the four edges of the first slit and go through the menu <code>Path > Edge Profile</code>. Click <code>OK</code> on two dialog boxes that pop up and on the left option panel, in all three cases leaving the default settings. You will now see the usual green lines indicating the path the machine will follow to make the cut. Select the <code>Profile_Edges</code> element from the left sidebar and go through <code>Path > Path Dressup > Dogbone Dress-up</code>. Select the same element again and click on <code>Path > Path Dressup > Tag Dress-up</code>.  On the selection panel that appears on the left sidebar, you will be asked where to position the tags, their width, their height and their angle. You can leave the default position, as this is calculated by an algorithm that figures out the best one quite accurately. As for width and height, type in a value of <code>10mm</code>;  <code>45</code> for the angle and <code>0</code> for the radius.
</p>
<img src="/cookbook/data-walk/img/4-28.png" />
<img src="/cookbook/data-walk/img/4-29.png" />
<img src="/cookbook/data-walk/img/4-30.png" />
<img src="/cookbook/data-walk/img/4-31.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>14</b>. Other than repeating the previous step for all the other slits, we can apply an <code>Array</code> command to automatically reiterate it. Select the <code>Profile_Edges</code> element from the left sidebar and go through <code>Path > Path Modification > Array</code>. An <code>Array</code> element will appear in the left sidebar, below the <code>Profile_Edges</code> element.  Select the <code>Array</code> element and click on the <code>Data</code> tab at the bottom of the left sidebar. Modifying the following values to match:</p>
<ul style="font-size: 12px;">
<li><code>Copies</code>: <code>19</code></li>
<li><code>Offset > y</code>: <code>-40</code></li>
</ul>
<p style="font-size: 12px;">
You will now have the first series of 20 slits at their right position, with the contour, dogbone dress-up and tag dress-up already applied. Repeat step 15 and 16 for the other 2 columns of slits, so that the final output looks like the latter of the following images.
</p>
<img src="/cookbook/data-walk/img/4-32.png" />
<img src="/cookbook/data-walk/img/4-33.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>15</b>. Your shapes are now ready for the export. On the left sidebar, you should have three <code>Job</code> elements, one for each of the unique shapes you have worked on (the base, the first data curve, and the second data curve). To make the next steps easier, you might want to reduce all the nested element so that you only have the three <code>Job</code> elements on the left sidebar, like in the first image below. Select the first <code>Job</code> element and click on <code>File > Export</code>. Select your destination folder, assign a name, and then select <code>GCode (*.nc *.gc *.ncc *.ngc *.cnc *.tap *gcode)</code> as a file type extension. After clicking <code>Save</code>, you will be asked to <code>Choose a processor</code>. Usually, the most versatile option is to choose <code>linuxcnc_post</code>. As a precaution, it is recommended that you first check-in with the lab where you will fabricate your objects, to make sure that you choose the option that suits their machines best. Upon confirmation, a pop-up screen will appear with the text of your GCode. Repeat this step for the other two <code>Job</code> elements.  Note that, while generating the GCode for the two data curves will likely only take a few seconds,  the engraved base is much more complex. Depending on how powerful your CPU is, you might have to wait a few minutes before you receive confirmation of the GCode creation.
</p>
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">