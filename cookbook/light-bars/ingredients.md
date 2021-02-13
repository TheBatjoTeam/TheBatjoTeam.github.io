---
layout: r-ingredients
title: Light Data Bars
language: en
slug: light-bars


materials: 12
material1: "1 Microcontroller <a href='https://store.arduino.cc/arduino-uno-rev'>Arduino Uno</a> (one microcontroller will work for up to 8 light bars)."
material2: "1 Strip of 100 individually Addressable LEDs for each bar (model: WS2812B or similar). The quantity will depend on how many bars you want to create and how tall you want each bar to be. We used 100 LEDs per bar, to make it intuitive to visualize percentages. Buy the LEDS already in a strip that you can cut the desired length, so that you won't need to solder each LED individually. The strip you but might contain more LEDs than you need, but it can be easily cut into the desired length. For example, we bought a 200 LED strip, which we then cut into two."
material3: "1 Pressure sensor for each bar (model: FSR 402)"
material4: "1 electronic switch for each bar"
material5: "1 Breadboard"
material6: "A pack of Jumper wires"
material7: "2 Resistors (resistance: 10K Ω)"
material8: "1 kg of transparent PLA filament for each bar"
material9: "1 kg of colored PLA filament for each bar"
material10: "2 (ply)wood sheets of 50 x 70 x 0.3 cm"
material11: "1 (ply)wood sheet of 50 x 70 x 15 cm"
material12: "~ 8 screws (3mm diameter, 10mm length)"
material13: "Wood glue"
material14: "Strong glue suited to attach plastic material to wood"

hardware: 4
hardware1: "CNC Milling Machine"
hardware2: "3D printer"
hardware3: "Hot-glue gun"
hardware4: "Screwdriver"


software: 3
software1: "FreeCAD"
software2: "Arduino IDE"
software3: "Slic3r"

estimated-time-modeling: "~ 1 work day (8h) for 3D modeling; ~ 1 work day (8h) for electronics and Arduino setup"
estimated-time-fabrication: "depends greatly on the machine and its operators, estimate about 4h of CNC milling and 9h of 3D printing."
estimated-time-assembly: "~ 1 work day / 8h"

estimated-cost-material: " ~ €140 per bar"
estimated-cost-machines: "If you don’t own the machines, consider renting them at your local lab - estimate to book time slots for approximately 4h of CNC and 9h of 3D printing in total, but discuss the project first with the lab manager / machine operator because it will vary greatly depending on the specs of the available machine."
---
<p style="font-size: 12px"><em>These estimates refer to the creation of 1 wooden bar with 100 LEDs, 1 case element for the Arduino, 1 pressure sensor support case. Scale appropriately to have an idea of how much time and material you need depending on your situation.</em></p>

### What data to start with
The code we provide in this tutorial works for a JSON dataset containing one key-value pair for each bar you want to visualize. You could also work with other data formats, if you are familiar with the Arduino programming language and can edit the provided code.