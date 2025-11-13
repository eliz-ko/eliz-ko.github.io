---
layout: default
title: "Current Sensing PCB"
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

![current_sensing_image_schematic](/assets/current_sensing_image_schematic.png)


Current Detection 

**Tools:** KiCad  
**Role:** Electrical Engineer

[⬅ Back to Home](/)
