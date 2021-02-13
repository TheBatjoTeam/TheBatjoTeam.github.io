---
layout: r-tutorials
title: 3D Data Maps
language: en
slug: map
chapter: fabricate
chapter-title: Fabrication
section: 2b
section-title: "The 3D data layers and the 3D legend reference (3D Printing)"
previous: fabricate7
next: assemble
next-text: "Assembly"  
video: "no"
output-image: "/cookbook/map/img/15-output.png"

---
<p><em>For this part of the project, it is advised that you first contact the person who will operate the machines to produce the output. This because every machine has its own specs, capabilities, and possibly even software. The following paragraphs show the workflow that works for the specific machine used to produce our prototype, a Prusa i3 mk3. A desktop 3D printer is quite safe to use also for beginners to digital fabrication, unlike the CNC milling machine.</em></p>

<div>
<p style="font-size: 12px;">
<b>1</b>. Copy the GCode files of all the objects you need to 3D print onto the SD card of your 3D printer. Then, insert the SD card into the machine. 
</p>
<img src="/cookbook/map/img/15-1.JPG" />
<img src="/cookbook/map/img/15-2.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Prepare the PLA filament. Unpack it from its bag and cut the starting tip of the filament so that it is pointy.
</p>
<img src="/cookbook/map/img/15-3.JPG" />
<img src="/cookbook/map/img/15-4.JPG" />
<img src="/cookbook/map/img/15-5.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Load the PLA filament spool into its holder. <b>Make sure that it does not tangle while you are handling it</b>. 
</p>
<img src="/cookbook/map/img/15-6.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Insert the lead of the filament into the hole on top of the extruder. 
</p>
<img src="/cookbook/map/img/15-7.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. On the front display of the 3D printer, navigate the main menu and select <code>Preheat</code>. Once the extruder and the building place reach the needed temperature, navigate menu again and select <code>Load Filament</code>. The extruder will now start working and pull the filament inside its body. After a few seconds, you will see the PLA filament coming out of the nozzle. If you notice that it is flowing down smoothly, then the loading was successful, otherwise <code>Preheat</code> and <code>Load Filament</code> again.
</p>
<img src="/cookbook/map/img/15-8.JPG" />
<img src="/cookbook/map/img/15-9.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. From the main menu, navigate to <code>Print from SD</code>. Select the file you want to print and click <code>OK</code> to start printing.  In all, you will print a total of 32 sections: 16 for the layer with negative values and 16 for the layer with the positive values. Within the same data grid, each of the 16 sections has a unique combination of border radiuses, each combination matching the combination of only one section of the 3D data layer. This way, you will only be able to fit the right data section into the right grid section. To save time, rather than putting the puzzle together at the end, it is convenient that you print the data layer sections in a logical order and position them on the corresponding section of the support grid as soon as they're printed. For extra safety, you could even add a piece of tape with the id of each piece that you’ll then remove once the pieces are glued on the support grid. <br><br> It will take about 2.25 hours to print each piece. When a piece is printing, you don’t need to actively do anything with the printer and can even leave the room. However, if you can, it is a good idea to work close by or at least check on it once in a while so that you can intervene and restart the printing if, for any reason, something has gone wrong.
</p>
<img src="/cookbook/map/img/15-10.JPG" />
<img src="/cookbook/map/img/15-11.JPG" />
<img src="/cookbook/map/img/15-12.JPG" />
<img src="/cookbook/map/img/15-13.JPG" />
<img src="/cookbook/map/img/15-14.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. When the piece is completely printed, delicately remove it from the building plate. The piece might be attached quite firmly, so you might need a spatula to aid you in the operation. When you have detached the whole piece, use some pliers to remove the supports that connected the hanging parts of the piece to the building plate. PLA plastic is a very easy to recycle plastic: so make sure you discard the scraps and waste appropriately, for example by bringing it to PLA filament recycling facilities or at least by throwing it away in the plastic recycle bins. </p>
<img src="/cookbook/map/img/15-15.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>8</b>. For convenience, position the 3D printed section into its place on the support grid, and keep track of which sections you have printed so far and which are still missing.</p>
<img src="/cookbook/map/img/15-16.JPG" />
<img src="/cookbook/map/img/15-17.JPG" />
<img src="/cookbook/map/img/15-18.JPG" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">