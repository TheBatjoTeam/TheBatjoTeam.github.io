---
layout: r-overview
title: Light Data Bars
language: en
handle: /cookbook/light-bars
type: intro
slug: light-bars
final-output: "/cookbook/light-bars/img/final-output.png"

benefit1: 'Performative & Participatory'
benefit1-text: "When someone interacts with the data installation, they are at the same time offering a spontaneous performance for the other people nearby."
benefit2: 'Multisensory'
benefit2-text: "The data experience engages multiple sense: pressure and sight."
benefit3: 'Scalable & Reusable'
benefit3-text: "The same workflow can be applied to make as many bars as needed for the dataset. The physical components created can be completely reused for future installations with different data, by simply changing the input data in the Arduino code."
benefit4: 'Popular Chart'
benefit4-text: "The data installation resembles the form and functions of a bar chart, one of the most popular chart types."
difficulty: '1'
time: '1'
cost: '1'
variations: 3

---
 is meant as an installation to promote an informal and participative approach to data. The idea is inspired by the [New York Time's "You Draw it" series](https://www.google.it/search?q=nyt+%22you+draw+it%22&oq=nyt+%22you+draw+it%22&aqs=chrome..69i57.4356j0j1&sourceid=chrome&ie=UTF-8), where the reader is asked to guess the data trend before being revealed the actual numbers. Similarly, this installation features one or possibly several wood bars with LEDs. In an optimal scenario, there would be as many bars as those required to make a meaningful bar chart for the story narrated. Each bar represents a variable and the amount of LEDS that light up for each bar depends on the data. In our design, the bar has 100 LEDs so that it can be used to work with percentages easily (80 LED lights on = 80%), while also allow to normalize numbers in the data range to work with absolute values. For each bar there is a switch which controls the status among two possible options: light the bars according to the actual data (1), or light the bars according to the user's input guess (2). In this installation the user submits its guess for the data by hitting on a pressure sensor with finger, a hand, a toy hammer or any object specifically designed for the installation: the harder or softer the user hits, the higher or lower the number of LEDs that light up. 
 
There are two possible types of user experience through the installation. The user, after the guess, could immediately change the position of the switch to show the actual value for the variable and see how close its guess was. The user could then continue switching back-and forth to calibrate the guess until it matches the actual value.    
Otherwise, the user could move onto the next bar and try to guess the amount of following variable, switching to the actual results for all the bars at the end. 

In the process, the user is also grasping a general feel of quantities through a non-visual sense, while also being surprised by how close or far its guesses are.
 
The installation is useful to convey magnitudes and could be advantageously used for dataset where the metaphors of weight and pressure make sense. For example, it could be used to communicate budget distributions, where the effort it takes to light up a specific bar/variable metaphorically represents the tax effort required to cover such costs. 




## Possible variations   
The installation's interactivity is driven by an Arduino microcontroller and it is therefore easy for a programmer familiar with the language to add more features and customize the interaction and colors by editing existing variables or adding additional code snippets.

One first variation could be to have a single matrix, instead of multiple bars, with several pressure sensors for input, one for each variable. In this scenario, the user's guesses for each variable would be mapped in the same LED matrix, resulting in something similar to a waffle chart or treemap, rather than a bar chart.

Another option is to modify the Arduino code so that it saves each user's input on a SD. The user inputs could then be integrated on a follow-up piece comparing the "crowd's" expectations to the actual dataset. 

An interesting feature of using programmable LEDs to work with data is that the LED behavior can be used to communicate ambiguity or uncertainty in data, for example by having the LEDs blink at different frequencies.

Additionally, it is quite easy to adapt the design and code so that it works with other types of sensors and hand gestures, to harness different modalities and metaphors: temperature sensors, motion sensors, etc.

***Disclaimer**: data in the render image is dummy data, solely made up for demo purposes.*