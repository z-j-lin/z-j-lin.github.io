---
layout: project
type: project
image: images/rpie.jpg
title: Automatic Fuel Changer for Bio Diesel Engines
permalink: projects/engine
# All dates must be YYYY-MM-DD format!
date: 2019-12-15
labels:
  - Python
  - Raspberry Pi
  - Hawrdware Programing 
summary: The goal of this project is to use a raspberry pi to automatically switch between fuels on a diesel engine using the general purpose input and output pins on the pi. 
---
## Background
Bio-diesel can burn in most diesel engines with minimum risk to engine failure. Failures in diesel engines from burning bio diesel is the result of un burned residue in the fuel injectors. To solve this issue we will burn bio diesel only when the temperature of the engine reaches a point where the fuel is burned at a higher temperature.  

For this project, I was the programmer responsible for writing the code to implement automatic engine start and fuel switching as well as a predefined shut off procedure. For the automatic engine start I used one of the GPIO ports to send out 3 second pulses signals to a relay controlling a starter motor when a user presses a start button. A wire tapped to the alternator of the engine provided the signal to let the program know that the engine started and that the starting sequece has beeen completed. 

In this project I gained experience with programming hardware in a highlevel scripting language. This was also my frist time writing a program to control hardware. 
 
