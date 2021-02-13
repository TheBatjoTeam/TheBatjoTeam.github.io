---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter: fabricate
chapter-title: Fabrication
section: 1.a
section-title: "The base map (CNC milling GCode)"
previous: fabricate
next: fabricate2
next-text: "Fabrication · Part 1.b"  
video: "yes"
video-link: "https://player.vimeo.com/video/305845761"
download: "no"
output-image: "/cookbook/map/img/7-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. Open FreeCAD and load the <code>.fctd</code> file containing the base map. </p>
<img src="/cookbook/map/img/7-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Switch to the <code>Path Workbench</code>. This workbench allows you to generate the machine-readable paths that instruct the CNC milling machine on the movements necessary to replicate the designed object.</p>
<img src="/cookbook/map/img/7-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Select the whole object and go through the menu <code>Path > Job</code>. In the dialog box that appears, leave the default options and click <code>OK</code>. 
</p>
<img src="/cookbook/map/img/7-3.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. A transparent rectangle enclosing your shape should have appeared on the main window. 
The rectangle is called “stock” and it represents the area of space from which the shape will be carved out or engraved. At the same time, a <code>Job edit</code> pane will appear on the left. In this panel, you need to set the size of the margins you want to apply around your shape. The boundaries of the shape plus these margins define the size of the stock. In this case, we apply a margin of <code>5mm</code> on both the <code>X axis</code> and Y<code> axis</code>. For the <code>Z axis</code>, on the other hand, we apply a margin of <code>0 mm</code>. This way, the machine will cut all the way to the bottom of the sheet of wood.  Once you have defined to stock, you need to define the origin point of the machine’s movements. With your mouse, select the bottom left corner of the stock and click on the command <code>Set Origin</code> from the left selection panel. If this has been carried out correctly, you will notice that the Cartesian plane with the red, green and blue arrows has moved so that its origin corresponds to the corner you have just set as the origin. See image below for clarification.
</p>
<img src="/cookbook/map/img/7-4.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Declare what type of milling tool you are going to use to perform the cutting operation. Go through the menu <code>Path > Tool Manager</code>. A pop-up window will appear, with a tool library containing information on several milling tools their technical characteristics. Note that this library is build manually and gradually, as you add new tools you need to work with. In your case, thus, it is likely that the pop-up window will show you an empty library. To add a new tool to the library. Click on <code>New Tool</code>. You will be promoted with a form that allows you to define the specs of the tool you will be using and add it to your tool library. For this project, you will first need to define a milling tool that has at least the following specs: a type of <code>EndMill</code> and a diameter of <code>1.2mm</code>. Clicking on OK will add this tool to your tool library.  Click on <code>New Tool</code> again and now add a milling tool with type <code>EndMill</code> and a diameter of <code>3mm</code>. Once the tool has been added to the library, mark the corresponding box in the tool library and click on <code>Create Tool Controller(s)</code>. This way, the specified tool will be exported along with the other path instructions and will be used by the milling machine for its cutting task.
</p>
<img src="/cookbook/map/img/7-5.png" />
<img src="/cookbook/map/img/7-6.png" />
<img src="/cookbook/map/img/7-7.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Because the <code>1.2mm diameter</code> toll is a high-precision tool, you also need to set the speed of the movement of spindle. Double-click on the <code>Precision tool</code> element that is on the left sidebar. In the <code>Tool Controller</code> pane that appears on the left, set both  the <code>Horiz. Feed</code> and the <code>Vert. Feed</code> to 5.00 mm/s.
</p>
<img src="/cookbook/map/img/7-8.png" />
<img src="/cookbook/map/img/7-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Start on a section of the <code>base map</code> and click on the inside of a few of the faces that will be engraved. Then go through the menu <code>Path > Face</code>. In the dialog box that appears, select the first precision tool you had previously created (1.2mm diameter) and click <code>OK</code>. On the left, a <code>Millface</code>  selection panel will now appear, change the <code>Pattern</code>< parameter to <code>ZigZafOffset</code> and click <code>OK</code>. Zoom in to see the effect (see last image below). This command tells the milling tool to “scratch” the surface by making a series of parallel linear movements. 
Repeat this step for all the engraved faces of your map (in this case, being Venice full of canals, there are quite many of them). You are working in sections to avoid making the software crash. If you feel that you have a powerful CPU, you can increase the size of the selection or even directly select all the faces in one go.
</p>
<img src="/cookbook/map/img/7-10.png" />
<img src="/cookbook/map/img/7-11.png" />
<img src="/cookbook/map/img/7-12.png" />
<img src="/cookbook/map/img/7-13.png" />
<img src="/cookbook/map/img/7-14.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. Select the edges of the square base. Click through <code>Path > Edge profile</code>. This will instruct the machine to create a cut operation around the selected edges. In the <code>Tool Controller</code> dialog that appears, select the second precision tool you had previously created (3mm diameter) and click <code>OK</code>. There will now be some green lines around the square base, representing the path the milling tool will follow. 
</p>
<img src="/cookbook/map/img/7-15.png" />
<img src="/cookbook/map/img/7-16.png" />
<img src="/cookbook/map/img/7-17.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. You need to instruct the machine to perform a Tag Dress-up. This is a way to assure that the cut-out object will stay fixed in place till the end of the cutting operation. This is achieved by instructing the machines to skip cutting certain small sections around the contour of the object, so that it stays locked into its frame. To apply this instruction, select the edges of the base and click on <code>Path > Path Dressup > Tag Dress-up</code>. 
On the selection panel that appears on the left sidebar, you will be asked where to position the tags, their width, their height and their angle. On the selection panel that appears on the left sidebar, you will be asked where to position the tags, their width, their height and their angle. You can leave the default position, as this is calculated by an algorithm that figures out the best one quite accurately. For <code>width</code> and <code>height</code>, type in a value of <code>10mm</code>;  <code>45</code> for the angle and <code>0</code> for the radius. This is to make sure the tags are not too big, otherwise it becomes hard for you to remove the cut out piece from the original frame. The last of the following images shows you what the representation of a tag looks like in FreeCAD.
</p>
<img src="/cookbook/map/img/7-18.png" />
<img src="/cookbook/map/img/7-19.png" />
<img src="/cookbook/map/img/7-20.png" />
<img src="/cookbook/map/img/7-21.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>10</b>. You’ve finished prepping the piece for fabrication and your model is now ready for the export. On the left sidebar, you should have one <code>Job</code> element. Select it and click on <code>File > Export</code>. Select your destination folder, assign a name, and then select <code>GCode (*.nc *.gc *.ncc *.ngc *.cnc *.tap *gcode)</code> as a file type extension. After clicking <code>Save</code>, you will be asked to <code>Choose a processor</code>. Usually, the most versatile option is to choose <code>linuxcnc_post</code>. As a precaution, it is recommended that you first check-in with the lab where you will fabricate your objects, to make sure that you choose the option that suits their machines best. Upon confirmation, a pop-up screen will appear with the text of your GCode. Depending on how powerful your CPU is,  you might have to wait a few minutes before you receive confirmation of the GCode creation.
</p>
<img src="/cookbook/map/img/7-22.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">