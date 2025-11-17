---
layout: default
title: "Current Sensing PCB"
nav: false
---

# 💡 Current Sensing PCB

This PCB was designed for my robotics team to detect motor current and show overload status.

![Current Sensing PCB](../assets/current-sensing.jpg)

The schematic has three different parts:
  - Current Sensing
  - Current Detection
  - Current Overload

Current Sensing 
The current sensing process goes as follows: 
Current enters shunt resistor -> small voltage representing the current comes out -> voltage goes into an amplifier -> amplified voltage goes to other sections to be read

There are various ways to detect and measure current within a circuit but the one we chose for this application was the shunt resistor method. 
A shunt resistor is a resistor with a very small resistance (ours had a resistance of 1 milli-ohm or 0.001 ohm) which can be used to take some current in
and then output a very small voltage. Using Ohm's Law, V = IR, you can find the current by inputting the known resistance and the voltage measured on the other side into the equation.

However, due to the small resistance value, the outputted voltage would be too small to be properly detected by the comparators in the other sections. Thus, it needs to be amplified. We selected an amplifier which has 4 different gain options. Essentially, based on the gain option selected, the outputted voltage will be increased by some amount. We chose the 10x gain option which for every volt, it increases the outputted voltage by 10 times. So, if the inputted voltage is 0.15 volt, the outputted voltage would be 1.5 volts. This decision was based off the calculations done for each gain option, where the 10x option seemed to be the best as it would ouput voltage just high enough to be sensed and also low enough to not have any signficiant noise. 

![Schematic screenshot of Current Sensing](/assets/current_sensing_image_schematic.png)

To understand the next sections, you need to understand the logic behind how comparators work: 


Current Detection 
The current detection process goes as follows:
Current sensing signal is inputted along with a voltage created by a resistor divider which is meant to represent the value 5 amps or the minimum current needed to turn the motors -> they are compared in a comparator -> if current is larger than 5 A turn on the LED, else keep the LED off 

![Schematic screenshot of Current Detection](/assets/current_detection_image_schematic.png)

Current Overload
The current overload process goes as follows:
Current sensing signal is inputted along with a voltage created by a resistor divider which is meant to represent the value of 20 amps or the maximum current which can be supplied to the motors -> they are compared in a comparator -> if current is larger than 20 A turn on the LED, else keep the LED off

![Schematic screenshot of Current Detection](/assets/current_overload_image_schematic.png)

**Tools:** KiCad  
**Role:** Electrical Engineer / Electrical Team Member

[⬅ Back to Home](/)
