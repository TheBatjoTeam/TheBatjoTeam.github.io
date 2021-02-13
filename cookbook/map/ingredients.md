---
layout: r-ingredients
title: 3D Data Map
language: en
slug: map


materials: 6
material1: "1 plexiglas sheet (min. 55 x 55  x 0.3 cm). You can choose the color you wish"
material2: "3 wood sheet (58 x 65 x 1 cm)"
material3: "3 spools (3kg.) of PLA filament. We used black, but you can choose to use different colors"
material4: "~  4 screws (6mm diameter)"
material5: "Wood paint (optional)"
material6: "Wood glue"

hardware: 4
hardware1: "CNC Milling Machine"
hardware2: "Laser cutter (optional)"
hardware3: "3D printer"
hardware4: "Screwdrivers"


software: 4
software1: "FreeCAD"
software2: "Blender + BlenderGIS Addon"
software3: "Inkscape"
software4: "Slic3r"

estimated-time-modeling: "~ 1 work day / 8h"
estimated-time-fabrication: "depends greatly on the machine and its operator. (approximately 3 days with standard machines, but the time can be cut down considerably if you have access to larger machines)"
estimated-time-assembly: "less than 1 work day / 4h"

estimated-cost-material: "€100"
estimated-cost-machines: "If you don’t own the machines, consider renting them at your local lab - estimate to book time slots for approximately 8 hours of CNC milling and 65 hours of 3d printing in total, but discuss the project first with the lab manager / machine operator because it will vary greatly depending on the specs of the available machine."
---

<p style="font-size: 12px"><em>These estimates refer to the creation of 1 CNC-engraved plexiglas map (50 x 50 cm); 2 PLA data layers (50 x 50 cm each) with legend; 1 supporting frame element for the plexiglas map (56 x 73 cm); 7 PLA insertion slits to hook the layers onto the map.
Scale appropriately to have an idea of how much time and material you need depending on your situation.</em></p>

### What data to start with

To follow with the proposed tutorial, you should have at least 3 geo files:

- **One .SVG** base map with the boundaries you wish to engrave in the plexiglas map. In this case, we used only land/water boundaries, but you can also have buildings, roads, administrative boundaries, etc. **Make sure the layers are simplified as much as possible and that the geometries are all valid**, otherwise, it will be hard for FreeCAD to handle the amount of vectors. In our case, we uploaded .SHP cartography files into QGIS and exported them as .SVG through the print composer. We then used Inkscape to select the square area we want to engrave on the 50x50 cm plexiglas surface.    
 
![svg-map](/cookbook/map/img/svg-clip.png){:width="100%"}


- **Two .SHP** files with a hexagon grid containing 1 attribute for each hexagonal polygon. In our case, we used QGIS to create such file. We started from census tract data for the 1991 and 2011 census in Venice and mapped the values to a 250x250 m hexagon grid. We then subtracted the 1991 value for each hexagonal polygon from the 2011 value, resulting in a hexagonal grid layer where each polygon contained population change between 1991 and 2011. We the split the layer so that one contained only hexagons with positive change and one only those with  negative change. In the layer with negative values, we add a column containing the absolute values. We then exported both of these layers as separate .SHP and used them for the tutorial. It does not matter if these shapefiles stretch beyond the square area of your SVG map: you will refine them to match the dimensions of the SVG map during the tutorial. You are welcome to reproduce the tutorial with other types of shapefiles containing different polygons than hexagons, for example census tract, cities, contour lines, etc.    
***NOTE**: the software used needs to work with distinct solids with no overlapping lines. In the default hexagonal grid created by mapping software, the polygons have in fact overlapping lines. To make sure that the hexagons are workable for the 3D modeling software, you have to add a buffer between them before exporting the .SHP file. Giving the buffer zone a very minimal number is enough, as this removes the overlapping while creating a gap that is essentially imperceptible to the eye.*   

![buffer](/cookbook/map/img/buffer.png){:width="100%" :padding="15px"}    

![positive](/cookbook/map/img/positive-layer.png){:width="100%"}   

![negative](/cookbook/map/img/negative-layer.png){:width="100%"}