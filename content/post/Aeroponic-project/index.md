+++
author = "Aeroponic project"
title = "Aeroponic project"
date = "2020-09-20"
description = "Aeroponic project"
categories = [
    "Aeroponic project"
]
tags = [
    "Aeroponic",
]
image = "/img/salade_main.jpg"
+++

# Why the project?

In those days we have to think about the future. If we want to slow down our pollution rate, we have to change our way of thinking an our way of living. In north country like Canada, we depend on south country to feed us. The transport of our food is done by truck over thousands of kilometers. Thus, our food is no longer totally fresh. Furthermore, the pollution produced by these transports is not negligible. With those facts north country have to find a way to produce fresh food all year long. 


![aa2](/img/oli_salade_main.jpg)
<p align="center">
  <img width="460" height="300" src="/img/oliSalade.jpeg">
</p>
# Why Aeroponic?s

Aeroponic is the most efficient system for growing fruit and vegetables. This system uses mist sprayers to atomized water to transmit nutrients to the roots of suspended plants in a closed environment. Comparing to other systems likes hydroponic and aquaponic, this one used less water as the roots are in the air instead of being immersed in water. Moreover it's lighter that other systems because your main water tank can be smaller. Furthermore less water mean you need less nutrients to reach the same amount of ppm than in a bigger tank. Another great point is that growing method don't need chemicals to control pest and insects. The harvesting is simple because the roots are not stock in a matrix like earth.

In light of the fact that I used to be an athlete and that I have a mechanical engineering background, I thrive on pushing beyond limits. NASA developed that system, so I had give it a try. I wanted to test it because there is not a lot of data about aeroponic. Also, I wanted the most efficient growing system that exist, efficient in the sense of comparing plant to plant. I know that a stage hydroponic system is highly efficient and can be more efficient because the space needed for the roots can be smaller.


**The systeme overall**

For an aeroponic systeme you need a pump, a shut off valve, a presurized water tank, tubing, fittings, solenoid valves, microcontroler or timer, net pot, plants container, water tank.

# What I used for my project

**Pump:** Aquatec 8800 High Flow Booster Pump CDP-HFO 3/8"JG-110BP-24V AC Universal Plate +Aquatec Transformers For 8800 Series Booster Pumps 120V 

**Presurized water tank:**

**In Line Check Valve:**

**tubing:** John Guest 3/8" and 1/4" Polyethylene Tubing 

**fitting:** John Guest PI Series Connectors 

**Shut off valve:** Aquatec Pressure Switch 80 PSI 3/8" JG 

**Solenoid valves:** Rain Bird CP075 and a Rain Bird Transformer

**Microcontroler:** Arduino Mega 2560 R3 Microcontrôleur

My first need was to time solenid valves. I could buy a timer, but I preferred to program it to be able to change the time for whatever I want. After that I though that it could be nice to have sensors to reed the pressure, the temperature, the humidity, the ph and the ppm. After I had programmed that, I added 4 pumps, 3 peristaltic pumps for the ph up, the ph down and the nutrients and one submersible to brew my nutrient basin. With that, the ph and ppm can adjust by itself. For instance when the ph sensors read a lower ph than the command the ph up pump start for 2 seconds to add ph up, after that, the submersible pump brew the water for 2 minutes and to finish the sensor read again. If the ph is no ok after the adjustment cycle an other cyle start over. I also add 4 water sensors, one neer my pump, one neer my pressure tank and two under my plant containers. If a leek happened the solenoid valves will stop so that I will minimize the damages. Next, I add a LCD screen to read my sensors. After a couple of times I though that it could be cool to have a real interface user to be able to see what happened, to follow my sensor readings over time. For instance if I noticed that my peek pressure start to decrease I would know there is something weird on my pump, maybe it's a leek or maybe I need to change it. Following data is a good tool to manage the preventive maintenances.  

**Computer:** Raspberry pi 

After scratching my head for a couple of weeks I finally finished my first interface user.
I used a Raspberry pi to program the interface with python and tkinter. Whit it I can now access the arduino to follow data via graphics and change some parameters like cycle times, ph level, ppm level, etc.  
                                                    

![aa](/img/all_elec.jpg)

peristaltic pumps

![aa](/img/3_pump_.jpg)
**sensors:** water level sensors, DS18B20 Waterproof Temperature Sensor, Module Kit, VintLabs DHT22 AM2302 Temperature and Humidity Sensor Module for Arduino, ELEGOO 4 Channel DC 5V Relay Module with Optocoupler for Arduino.


**Net pot:** Hydroponics plant pot


**plants container:**


**Water tank:**


**The Pump: Aquatec 8800 booster pump**

This pump is very powerfull not very expensive. You can build up 125 psi whits this pump. To maintain a high pressure and to save the life of the pump it's a must to have a pressurized water tank. 

![aa](/img/salade_main.jpg)


