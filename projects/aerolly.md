layout: project
type: project
image: images/aeroponics.jpg
title: IOT Aeroponics Machine Learning Data Collection
permalink: projects/aerolly
# All dates must be YYYY-MM-DD format!
date: 2020-03-1
labels:
  - Aeroponics
  - Smart Farming
  - Machine Learning
summary: A system for growing plants in a more efficient and controlled way with precise nutrient, water, and light inputs.
---
<img class="ui image centered image" src="../images/grow_system_design.png">


## The Project
Conventional farming inherently has a plethora of inefficiencies in the sonsumption of water, land, and fertilizer. An alternative to conventional farming is aeroponics, a method of soil less growing where plant roots is suspended in a enclosure equiped with misting nozzles where plant nutrient mixed with water is periodically sprayed directly on the plant roots. Unlike conventional farming where water can be evaporated into the air, and nutrients can leach out of the planting area, the unused water, and nutrients can be recaptured and reused. We also plan to use IOT to automate the growing process and machine learning to generate parameters for each plant so that anyone can use our system to grow food.

## Data Collection 
The goal of collecting data is to find the right set of parameters for nutrient spray duration, nutrient conecentration, light intensity and  duration, and plant growth rate. The idea of aeroponics is that optimal nutrient absorption happens when the droplets making contact with the root hair is below 50 microns, and that roots are exposed to air so that it can absorb oxygen as part of the plants respiration process. If the duration of sprays are set too long and happen too often, the roots will constantly be drenched which defeats the purpose of aeroponics. To have optimal growth the duration and frequency of watering needs to be spot on and further more the concentration of nutrient also needs to be optomized since too little nutrient will cause the plants to grow slowly and too much can cause the plant to die. Light intensity and duration is also another important paramenter since too little light would cause the plants to grow rather slowly and having too much light wouldn't necessarily increase growth rate but instead increase operation cost for a farm.

## Machine Learning 
Our plan to generate a useful model to use for each plant was to use linear regression and support vector machine to categorize different sets of parameters that yield the best growth rate. This proved challenging due to our limited resources, we were not able to track the plants biomass continuously without harvesting and weighing the plants. We initially tried measuring the height of the plants which was very time consuming. In the future if I were to do this again I would use phenospex planteye to capture more accurate growth data and automate the data collection process. Another change I would make is to use reinforcement learning and use multiple specimens all with varying parameters to exhaust as many parameters so that we can learn more with fewer generations of plants. 

## Technical Details 
<img class="ui image centered image" src="../images/grow_system_prototype.png">

## Control System
The control system consists of a Raspberry Pi 3B (R-pi), a 4-input digital relay board that controls the on/off state of the pump, and a solenoid that controls the watering. The Raspberry pi communicates with the relay switch board via 5v logic. On the output end of the relay switch, we have 4 sets of terminals that allow us to switch on a 12V DC power supply for 4 different 12V devices. The relay board is currently used to turn on the solenoid controlling water flow for the sprinklers, and the 12V water pump. Since the raspberry pi had network connectivity we were able to connect it to a server that stored control variables which we were able to control using a webpage. This allowed us to monitor the system over the internet.  
<img class="ui image centered image" src="../images/aerolly_web_interface.png">
## Raspberry Pi 
A R-pi board is used to provide control and network communication for the system. Our goal of the system is to automate as much of the system as we can from automated watering, to scheduled automated data collection cycles. To provide automated control and mobile monitoring of the system we have a scheduling process running that sends commands to a command handler process that is also running on the R-pi. The command handler is set to listen to a Redis Pub/Sub queue allowing for input parameters to be stored on a web-based server. Currently the R-pi is connected to a virtual private network, communicating with a server on that same network with a web page attached so that we can view sensor readings from the system remotely, the web page is shown in figure 3. 
