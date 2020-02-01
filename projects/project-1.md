---
layout: project
type: project
image: images/Robotics_300x300.jpg
title: FIRST Robotics Competition 
permalink: projects/robotics
# All dates must be YYYY-MM-DD format!
date: 2014-02-06
labels:
  - Robotics
  - Engineering
  
summary: My team designed and built a robot that was able to pick up a excercise ball and launch it into a goal 8 feet high.
---

<div class="ui small rounded images">
  <img class="ui image" src="../images/micromouse-robot.png">
  
</div>



For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

Here is some code that illustrates how we read values from the line sensors:

```js
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```





