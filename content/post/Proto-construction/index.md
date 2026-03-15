+++
author = "Olivier Boisvert"
title = "The bulding of the prototype"
date = "2021-04-02"
description = "How I built the prototype"
tags = [
    "Aeroponic",

]
categories = [
    "Aeroponic",
   
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
image = "/img/top_const.jpg"
+++

For the prototype, my goal is to make a light and "easy to build" module. The reason is simple, one of the strengths of aeroponics is that the system consumes at least 80% -95% less water than hydroponics. Thus an aeroponic system is much lighter. As a result, it can be installed on less strong roofs easier. Roofs will not have to support a large amount of weight of water.

My first idea was to build a structure in PVC because this material is NSF. Subsequently I used HDPE panels, also NSF, in order to be able to support the pots of the plants. In order to create a retention basin I used an EPDM canvas, also NSF. I used stainless steel screws to hold the panels and boat buttons to hold the canvas. The installation was very long, and inconclusive, more than I pierced the canvas during the process. Also, the thin thickness of the panels, let the light get through them.

# April 2, 2021
{{< figure src="/img/nsys2.jpg" caption="First attempt frame">}}



# April 2, 2021

{{< figure src="/img/nsys5.jpg" caption="First attempt frame with EDMP tarpaulin">}}



I started my prototype again with a wooden support in order to hold an EDPM canvas in order to make a shallow retention basin. I recovered an HDPE panel to make the bottom of the basin. I rounded two of the four wooden seats in order to send the water to the center of the module. Then I used another kind of panel to hold the plants together. They are made of PVC and are food grade, NSF. The advantage of these panels is that they are easy to cut, come in several widths (8 to 16 inches) and lengths (8 to 16 feet). In addition to the fact that the company that manufactures these panels has matching moldings !. Ha, and of course the light doesn't pass through so bacteria won't grow.

# May 23, 2021

{{< figure src="/img/nsys7.jpg" caption="First attempt frame with EDMP tarpaulin">}}
#
{{< figure src="/img/nsys10.jpg" caption="Inside the **pyramid**">}}

#

Next step was to put a slider module controlled by a stepper motor above this module in order to mist as much surface as possible. So if I manufacture 16-foot modules in the future, mechanical maintenance will be simple compared to installing hundreds of misting nozzles.

{{< figure src="/img/nsys11.jpg" caption="Below the frame">}}

{{< figure src="/img/nsys12.jpg" caption="The sliding mechanism">}}

{{< figure src="/img/nsys15.jpg" caption="Overview of the system">}}



# May 24, 2021

The slide prototype is finished. I tested the system with a wooden bearing system that I turn manually. It remains for me to change this part with brackets and a stepper motor in order to operate it by a microcontroller.

Next steps:
-Install the motor, test it with a -microcontroller, and the various components to make it work.
-Attach the code to the main micro-controller
-Program an interface in order to control it manually and change its cycle times.


I added a motor and gears to move the sliding part

{{< figure src="/img/nsys24.jpg" caption="Motor, drive, and mechanism">}}


I added two limit switches to limit the movement and added it do the code. Now the system slide and mist, stop at a limit swith ( stop the power suply and the misters), waits 2 minutes and start over. 

{{< figure src="/img/nsys27.jpg" caption="Limit swiches">}}

#
{{< figure src="/img/nsys28.jpg" caption="System with limit switches">}}

#

I drilled the holes and cut pieces of NSF vinyl pipes to seal them.
{{< figure src="/img/nsys29.jpg" caption="System with holes">}}
{{< figure src="/img/nsys32.jpg" caption="System in action">}}


I tried clear vinyl pipes, the sealing effect was perfect but the light was diffused by this material. I changed all these seals for NSF black vinyl pipes and it worked. 
With the sliding system next to the main system I could get the piping system through the side instead of above. Thus, It's more difficult for the light to get into the system even impossible. To be sure that the system is light proof I added PVC molding around the EDPM fabric. 

{{< figure src="/img/nsys33.jpg" caption="The side groove">}}
#
{{< figure src="/img/nsys34.jpg" caption="The inside groove">}}
#
{{< figure src="/img/nsys38.jpg" caption="Finished overview of the pyramid">}}
#

# July 6, 2021
{{< figure src="/img/nsys42.jpg" caption="Final motor mechanism">}}

**see Final prototype post for the next update**
__________________________________