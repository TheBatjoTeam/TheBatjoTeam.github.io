---
layout: r-tutorials
title: 3D Data Map
language: en
slug: map
chapter: fabricate
chapter-title: Fabrication
section: 1.e
section-title: "The legend - engravings (CNC Milling GCode)"
previous: fabricate4
next: fabricate6
next-text: "Fabrication · Part 1.f"  
video: "yes"
video-link: "https://player.vimeo.com/video/305858410"
download: "no"
output-image: "/cookbook/map/img/12-output.png"

---

<div>
<p style="font-size: 12px;">
<b>1</b>. Open FreeCAD and load the <code>.fctd</code> file containing the support grid. </p>
<img src="/cookbook/map/img/12-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Switch to the <code>Path Workbench</code>. This workbench allows you to generate the machine-readable paths that instruct the CNC milling machine on the movements necessary to replicate the designed object. Select the whole object and go through the menu <code>Path > Job</code>. In the dialog box that appears, leave the default options and click <code>OK</code>. </p>
<img src="/cookbook/map/img/12-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. A transparent rectangle enclosing your shape should have appeared on the main window. 
The rectangle is called “stock” and it represents the area of space from which the shape will be carved out or engraved. At the same time, a <code>Job edit</code>< pane will appear on the left. In this panel, you need to set the size of the margins you want to apply around your shape. The boundaries of the shape plus these margins define the size of the stock. In this case, we apply a margin of <code>5mm</code> on both the <code>X axis</code> and <code>Y axis</code>. For the <code>Z axis</code>, on the other hand, we apply a margin of <code>0 mm</code>. This way, the machine will cut all the way to the bottom of the sheet of wood.  Once you have defined to stock, you need to define the origin point of the machine’s movements. With your mouse, select the bottom left corner of the stock and click on the command <code>Set Origin</code> from the left selection panel. If this has been carried out correctly, you will notice that the Cartesian plane with the red, green and blu arrows has moved so that its origin corresponds to the corner you have just set as the origin. See image below for clarification.
</p>
<img src="/cookbook/map/img/12-3.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Declare what type of milling tool you are going to use to perform the cutting operation. Go through the menu <code>Path > Tool Manager</code>. A pop-up window will appear, with a tool library containing information on several milling tools their technical characteristics. Note that this library is build manually and gradually, as you add new tools you need to work with. In your case, thus, it is likely that the pop-up window will show you an empty library. To add a new tool to the library. Click on <code>New Tool</code>. You will be promoted with a form that allows you to define the specs of the tool you will be using and add it to your tool library. For this project, you will first need to define a milling tool that has at least the following specs: a type of <code>EndMill</code> and a diameter of <code>0.5mm</code>. Clicking on OK will add this tool to your tool library. Once the tool has been added to the library, mark the corresponding box in the tool library and click on <code>Create Tool Controller(s)</code>. This way, the specified tool will be exported along with the other path instructions and will be used by the milling machine for its cutting task.
</p>
<img src="/cookbook/map/img/12-4.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Because the created toll is a high-precision tool, you also need to set the speed of the movement of spindle. Double-click on the <code>Precision tool</code> element that is on the left sidebar. In the <code>Tool Controller</code> pane that appears on the left, set both  the <code>Horiz. Feed</code> and the <code>Vert. Feed</code> to 5.00 mm/s.</p>
<img src="/cookbook/map/img/12-5.png" />
<img src="/cookbook/map/img/12-6.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. Select a first batch of elements/letters/numbers that need to be engraved. (If you have a good CPU, you could also select everything in one go). Then go through the menu <code>Path > Pocket</code>. In the dialog box that appears, select the precision tool you had previously created (0.5mm diameter) and click <code>OK</code>. On the left, A <code>Pocket Shape</code> selection panel will now appear, change the <code>Pattern parameter</code> to <code>ZigZafOffset</code> and click <code>OK</code>. Zoom in to see the effect. This command tells the milling tool to “scratch” the surface by making a series of parallel linear movements. 
If needed, repeat this step for until you have applied on all the text and graphics element that you wish to engrave.
</p>
<img src="/cookbook/map/img/12-7.png" />
<img src="/cookbook/map/img/12-8.png" />
<img src="/cookbook/map/img/12-9.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. At this point, you’ve finished prepping the piece for engraving and you are ready for the export. On the left sidebar, you should have one <code>Job</code> element. Select it and click on <code>File > Export</code>. Select your destination folder, assign a name, and then select <code>GCode (*.nc *.gc *.ncc *.ngc *.cnc *.tap *gcode)</code> as a file type extension. After clicking <code>Save</code>, you will be asked to <code>Choose a processor</code>. Usually, the most versatile option is to choose <code>linuxcnc_post</code>. As a precaution, it is recommended that you first check-in with the lab where you will fabricate your objects, to make sure that you choose the option that suits their machines best. Upon confirmation, a pop-up screen will appear with the text of your GCode. Depending on how powerful your CPU is,  you might have to wait a few minutes before you receive confirmation of the GCode creation.
</p>
<img src="/cookbook/map/img/12-10.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">