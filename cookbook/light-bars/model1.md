---
layout: r-tutorials
title: Light Data Bars
language: en
slug: light-bars
chapter-title: 3D Modeling and Electronics
chapter: model
section: 1
section-title: "Arduino Circuit and Program Code"
previous: model
next: model2
next-text: "3D Modeling and Electronics · Part 2   "  
video: "no"
download: "yes"
download-name: "schematics and Arduino code"
download-link: "https://github.com/TheBatjoTeam/light-bars/tree/master/electronics_code"
output-image: "/cookbook/light-bars/img/1-output.png"

---
<p><i>This tutorial contains step-by-step instructions on how to configure one data-driven light bar. To add more bars, switches and sensors to your Arduino, continue adding electronic components by repeating the steps 3-5 for the additional LEDs, sensors and switches. At the bottom of the tutorial you will also find schematics illustrating how to connect the different components when working with multiple bars. One Arduino will support up to 8 bars. If there are more than 8 bars in your design, you will need to get additional Arduinos. Additionally, keep in mind that one Arduino, when connected to the computer, has enough power to supply only 1 bar at the time. For this reason, as soon as you start working with the second bar, you will need to attach and plug an additional power supply.</i>
<br><b>Do not connect the Arduino to the computer while you are creating the circuit, but wait until you have all the electronics components in place, or you could damage your board and circuit.</b></p>

<div>
<p style="font-size: 12px;">
<b>0</b>. For reference, this is the basic schematics of the circuit for one light bar. At the bottom of the tutorial you will also find the schematics for a circuit with multiple bars.</p>
<img src="/cookbook/light-bars/img/1-0.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>1</b>. Find a clear flat surface and layout all the materials needed for the circuit:</p>
<ul style="font-size: 12px;">
<li>1 Microcontroller Arduino Uno</li>
<li>1 Strip of 100 individually Addressable LEDs for each bar (model: WS2812B or similar)</li>
<li>1 Pressure sensor for each bar (model: FSR 402)</li>
<li>1 electronic switch for each bar</li>
<li>1 Breadboard</li>
<li>A pack of Jumper wires</li>
<li>2 Resistors (resistance: 10K Ω)</li>
</ul>
<img src="/cookbook/light-bars/img/1-1.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>2</b>. Connect the breadboard and the Arduino. <br><br>
A <b>breadboard</b> is a base that allows you to connect electronic components without the need to solder them together: you simply plug the components directly to the pins (holes) to create circuits. A standard breadboard has two horizontal strips, one at the top and one at the bottom, delimited by a red line and a black line. The pins within these strips are all horizontally connected. All the other pins at the center, on the other hand, are connected vertically.<br><br>
An <b>Arduino microcontroller</b> is a physical programmable circuit board. You code its functioning through the open-source <b>Arduino IDE</b> installed on your computer, which you then also use to upload the code to the physical microcontroller.<br><b>Do not connect the Arduino to the computer while you are creating the circuit, but wait until you have all the electronics components in place, or you could damage your board and circuit.</b>
<br><br>
A <b>jumper wire</b> is an electrical wire with connector/pins at its ends and is used to connect components together without soldering. To make the connection, you insert the jumper wire's pins into the pins of the electrical components you have to connect. Each wire can have a combination of male/female connectors at its two ends and you should choose the wire according to the pins of the components you are attaching: a male connector attaches to a female connector and vice-versa. All the pins of the breadboard are female, as are all the pins of the Arduino we are working with, so they require jumper wires with male connectors. Despite the different colors, all the wires are the same. It is however advised that you match the colors used in the image below, as they follow an established convention: red wires for positive charge (+), black wires for ground charge (-).
<br><br>
The first step is to provide power to the circuit. To do so, attach the jumper wires as shown in the image below. In this case, both the breadboard and the Arduino pins you need to connect have a female connector, so you need to use jumper wires with male connectors. Specifically, you should first use the red wire to connect the <code>5V</code> pin on the Arduino board to a pin in the top line of the breadboard. Then, use the black wire to connect the <code>GND</code> pin (Ground) to a pin in the line below the previous. Afterwards, use another red wire to connect a positive pin in the strip at the top of the board with a positive pin in the strip at the bottom of the board. Finally, use a black wire to connect a ground pin in the strip at the top of the board with a ground pin in the strip at the bottom of the board.</p><img src="/cookbook/light-bars/img/1-2.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>3</b>. Connect the LED strip to both the Arduino and the breadboard. <br><br>The <b>LED strip</b> you are working with is made up of <b>individually-addressable LEDs</b>, which means you can control the on/off status, color, blinking behaviour, etc. for each of them independently. <br>(<i><b>Note</b>: depending on your materials and design, you might have to first cut the LED strip into the desired length.</i>)<br>
The LED strip has 3 jumper wires already attached at its two extremes. Each of these wires corresponds to one of the three pins: one for ground charge (<code>GND</code>), one for positive charge (<code>5V</code>), and one for the data input controlling the LED's appearance and behaviour (generally labeled as <code>Din</code>, which stands for Data Input).<br><br>
To make the connections, attach the wires as shown in the image below. The actual position of the pins on the LED strip might vary depending on the model, but you should match the connections between the pins:</p>
<ul style="font-size: 12px;">
<li>Red wire to connect the <code>5V</code> pin of the LED strip to a pin in the top line of the breadboard</li>
<li>Black wire to connect the <code>GND</code> pin of the LED strip to a pin in the second line of the breadboard</li>
<li>Yellow<sup>*</sup> wire to connect the <code>Din</code> pin of the LED strip to the <code>~ 5</code> ('digital 5') pin on the Arduino board. <br><sup>*</sup>You can use any color you wish, preferably other than red or black, for readability.</li>
</ul>
<img src="/cookbook/light-bars/img/1-3.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>4</b>. Connect the pressure sensor to both the Arduino and the breadboard. <br><br>The <b>pressure sensor</b> or force sensor is essentially made up of tiny circuits that bend when subject to pressure. The bend is imperceptible to humans, but it creates a difference of potential between the power poles of the sensor. Such difference can be quantified, depending on the amount of force applied, and used as data - in this case as input data for the LED strip. The pressure sensor has two pins at its end for the power supply. Unlike the other cases encountered, there is no specific pin assigned for the (+) and (-) charge, and they can be used interchangeably.
<br><br>
To connect the pressure sensor, you first need a jumper wire with one female and one male connector. The female connector attaches to the sensor, the male connector to the breadboard. Use a red jumper wire to connect one pin of sensor to a pin in the bottom line of the breadboard. Then, use a black wire and attach the female connector to the sensor. At this point, things change slightly in comparison to what you've done before. This black wire sends a charge that has been modified by the pressure applied to the sensor. You need to send this information to the Arduino, so that it can calculate and quantify the pressure applied to the sensor to use it in its program. To do so, the black wire can't be connected directly to the <code>ground</code> strip of the breadboard, but it needs an intermediate step: connect it to one of the pins in central area of the breadboard. Then take a green wire and insert it in a pin which sits on the same vertical line as the previously inserted connector. Attach the other end of this green wire to the <code>A0</code> ('analog 0') pin of the Arduino board. As a final step, close the circuit by using a 10K resistor and a black wire, as shown in the image below.  </p>
<img src="/cookbook/light-bars/img/1-4.png" /></div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>5</b>. Connect the switch to both the Arduino and the breadboard. <br><br>The <b>switch</b> is used as an analog input to give commands to the Arduino. In practice, the switch connects or disconnects the electrical flow. In this case, we are using it to tell the Arduino whether it should light up the LEDs according to the actual JSON data stored in its memory or according to the data from the pressure sensor. <br><br>Because switches are used in many different contexts, it could be that your switch is not specifically designed for a breadboard and so doesn't have the usual male/female connectors you've seen on the other components so far. This is not a problem, as you can <a href='https://www.instructables.com/id/Use-scissors-to-strip-wires!/'>peel the jump wires with a wire stripper or with scissors</a> and then twist the copper around the connectors of the switch, as the first image below shows. If you know how to solder, you could also solder them in place. <br>
Connect the wires of the switch to the end to the Arduino as shown in the second image below. In short, you are replicating the reasoning behind the way you connected the pressure sensor in the step before: </p>
<ul style="font-size: 12px;">
<li>Use a red wire for the input charge (+)</li>
<li>Use a black wire and a purple wire to send the electrical signal (or absence of it) to the Arduino, linking the purple wire to the <code>2</code> ('digital 2') pin of the Arduino board</li>
<li>Use a resistor and a black wire to close the circuit</li>
</ul>
<p style="font-size: 12px;">The circuit is now ready and you can go to your computer to begin coding the program that will control the board.</p>
<img src="/cookbook/light-bars/img/1-5.png" />
<img src="/cookbook/light-bars/img/1-6.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>6</b>. To program the Arduino board, make sure you have installed the <a href = 'https://www.arduino.cc/en/Main/Software'>Arduino IDE</a> on your computer. This will also install an <code>Arduino</code> folder in your <code>Home</code> directory. Inside the <code>Arduino</code> folder, there will be several subdirectories, including one called <code>libraries</code>. This is where you will unzip the libraries needed for your Arduino program, after you have downloaded them. For this project, you will need the following two libraries:</p>
<ul style="font-size: 12px;">
<li><a href='https://github.com/bblanchon/ArduinoJson'>ArduinoJson</a></li>
<li><a href='https://github.com/FastLED/FastLED'>FastLED</a></li>
</ul>
<p style="font-size: 12px;">Once you have installed the libraries, launch the Arduino IDE.</p>
<img src="/cookbook/light-bars/img/1-7.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>7</b>. Copy-paste the code below into your Arduino IDE window or download the file from the GitHub repo and open it on your own computer. The code is commented so that you can see what customization options you can apply (number of LEDs in the strip, colors for lights driven by the JSON data vs. color for lights driven by the sensor data, transition delays, etc.). To make it work for your dataset, you should replace the JSON variable on line <code>58</code> with the text of your own JSON and change the reference to the column names accordingly.</p>
<pre data-src="/js/light-bars.ino" class="language-arduino line-numbers" data-download-link> </pre>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<hr style="color: #ccc" size="1">
<p style="font-size: 12px;">
<b>8</b>. Once the code is in place, you can check it for errors by clicking the checkmark button in the top-left of the toolbar (see first image below). The bottom console will warn you of any errors to fix (see second image below). <br>
Once the code is verified, you can upload it into Arduino. First connect the board to the computer via USB (see third image below). On the <code>Arduino IDE</code>, click on the right-arrow button on the toolbar (see fourth image below). Wait for the upload to finish. Now you can test the actual functioning of the program and board by playing around with the switch and sensor. (See last image below).</p>
<img src="/cookbook/light-bars/img/1-8.png" />
<img src="/cookbook/light-bars/img/1-9.png" />
<img src="/cookbook/light-bars/img/1-10.png" />
<img src="/cookbook/light-bars/img/1-11.png" />
<img src="/cookbook/light-bars/img/1-12.png" />
<img src="/cookbook/light-bars/img/1-13.png" />
<img src="/cookbook/light-bars/img/1-14.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">

<div>
<p style="font-size: 12px;">
<b>9</b>. To add more bars to the circuit, repeat steps 3-5 for each additional bar. You can refer to the following schematics as a guide to add the components. As the drawing shows, you need to add an external power supply to light multiple bars.</p>
<img src="/cookbook/light-bars/img/1-15.png" />
</div>
<div class="clear"></div>
<hr style="color: #ccc" size="1">
