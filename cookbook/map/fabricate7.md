---
layout: r-tutorials
title: 3D Data Maps
language: en
slug: map
chapter: fabricate
chapter-title: Fabrication
section: 2a
section-title: "The base map, the support frame for the base map, the support grid for the data layers (CNC Milling)"
previous: fabricate6
next: fabricate8
next-text: "Fabrication · Part 2b"  
video: "no"
output-image: "/cookbook/map/img/14-output.png"

---
<p><em>For this part of the project, it is advised that you first contact the person who will operate the machines to produce the output. This because every machine has its own specs, capabilities, and possibly even software. The following paragraphs show the workflow that works for the specific machine used to produce our prototype, a Stepcraft 2/800. The tutorial is included solely to educate on how such machines work. We absolutely don’t advise you to follow this part of the tutorial on your own, unless you have previous experience with operating a CNC milling machine, which comes with some safety concerns and necessary technical setup prior to each operation.</em></p>

<div>
<p style="font-size: 12px;">
<b>1</b>. Start with one of the installation components that need to be milled. Place the plexiglas or wooden sheet on the surface of the CNC milling machine, according to what is the material of the object you want to mill. <b>If working with plexiglas, do not remove the protective film</b> until you have finished the milling process and any other handling or transportation that could damage it.<br> Make sure the machine has a so-called “sacrificial layer”, usually a piece of MDF which will protect the actual surface of the machine from accidental collisions with the milling tool. When the plexiglas/wooden sheet is in position, check that it rests completely flat on the sacrificial layer, without any bump. Once the sheet is laying place, it need to be fixed in place so that it doesn’t move around during the milling operation. Many machines will have something to firmly attach the material to the machine, in the Stepcraft 2/800 it's the screwable bars shown in the picture If this support is missing, you can screw the wood sheet that you will mill directly to the machine’s sacrificial layer, being extra careful that the screws are not placed in areas where the milling tool will move upon.
</p>
<img src="/cookbook/map/img/14-1.JPG" />
<img src="/cookbook/map/img/14-2.JPG" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Pick the milling tools needed for your project. You might remember that you had already assigned them in FreeCAD, from the <code>Tool Library</code>, when generating the G-Code (step 8 -9). Find the milling tool that corresponds to the Job contained in the GCode and attach it to the spindle <b>firmly</b>. If you don’t pick the right milling tool, then the whole milling operation could be compromised. If your object requires both engraving tasks and cutting tasks, thus two types of jobs and likely two types of milling tools, it is better to start with the engraving first. This because once the piece is cut out from the original material, it is kept in place only by the tabs and so it is less stable. Engraving a material is a high precision task that need as much stability as possible.</p>
<img src="/cookbook/map/img/14-3a.JPG" />
<img src="/cookbook/map/img/14-3.JPG" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Now set the origin point for the spindle’s movements. Again, this should match the position you had set in FreeCAD, when generating the GCode and defining the stock. So, if in FreeCAD you had set the origin in the bottom left corner, now you should position the spindle in the bottom left corner, so that the paths followed by the spindle do not exceed the work surface. The origin point consists of a X, a Y and a Z coordinate point. Unless it’s a very complicated pattern, you can set the position along the X and Y axis also simply by eye-measurement. The position along the Z axis, that is how high the milling bit is from the surface of the working material, is a bit more complicated. Some machines have an automatic system for this positioning. Otherwise, an accurate positioning can be obtained manually, by placing a regular sheet of paper underneath the tip of the milling tool and moving the spindle down until the milling tool touches the paper. You will know you have reached the correct positioning when:</p>
<ul style="font-size: 12px;">
<li>If you pull the paper towards you, it will move out from underneath the milling tool without tearing</li>
<li>If you push it away from you, it will get stuck and bend without slipping away (see second of the following two pictures for reference).</li></ul>
<img src="/cookbook/map/img/14-4.JPG" />
<img src="/cookbook/map/img/14-5.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. From the software, generally provided by the manufacturer, load the GCode file corresponding to the milling job you want to perform. Remember that, if your Gcode contains both engraving tasks and cutting tasks, it is better to start with the engraving. Turn on the spindle carefully and then start the milling operation from the software interface on your computer.</p>
<img src="/cookbook/map/img/14-6.JPG" />
<img src="/cookbook/map/img/14-7.JPG" />
<img src="/cookbook/map/img/14-8.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. If the object has both an engraving and a cutting task, wait for the engraving task to finish. With most of the machines, the software will stop the milling on its own and warn you to switch to the other milling tool, for example, when milling the plexiglas base map, the 3mm diameter one required to cut out the square edges of the map. Always ask your machine operator if this is the case also for the machine you’ re working on, or if you need to pay attention and manually stop it when it is time to change the tool.
</p>
<img src="/cookbook/map/img/14-9.JPG" />
<img src="/cookbook/map/img/14-10.JPG" />
<img src="/cookbook/map/img/14-10a.JPG" />
<img src="/cookbook/map/img/14-10b.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. When all the milling operations are completed, you can remove the milled shapes from the original material. Because of the tabs that kept it in place during the milling, you will likely need the help of a chisel for this task. In this phase, you might also notice that, due to irregularities in the material’s thickness, in some places the shape might not have been cut thoroughly. In this case, you can easily use a cutter. 
</p>
<img src="/cookbook/map/img/14-11.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. As a last step, you should sand the wooden pieces to make them smooth. This is both to make sure that there aren’t any dangerous chippings and to prepare the pieces for a layer of paint, if you plan to apply any.</p>
<img src="/cookbook/map/img/14-12.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

