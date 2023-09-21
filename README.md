# DisasterArea
Open Hardware pedal based on the Fuzz Face but, like the Base13, has a true +9v supply and a buffered output.

The operation of a PNP fuzz from a +9v rail can be achieved by AC coupling into an amplifier circuit that is referenced to +9v rather than ground, but this is susceptible to excess noise in the context of a pedal that is likely to be operated with a high gain - not a great scenario. In this case, a -9v rail is created using inverters (MAX1044 or ICL7660S). Given the noisy nature of fuzz circuits, it is generally important for both ground and any rails to be very clean - a 9v battery being ideal but less convenient than a 9v PSU. Accordingly, this design cascades 2 inverters to create a-ve rail of around 16v to 18v which then provides enough headroom to use a -9v regulator for the -9v rail.

Critical to the behaviour of both the Fuzz Face and the Rangemaster is the fact that the input impedance is low and interacts directly with the pickup coils. For this reason, the input is deliberately not buffered into the effect but the input signal is wired in parallel to a high impedance buffer with a separate output. The reason for this is to provide a clean signal to drive the detector of a noise gate (e.g. the ISP Decimator).

I have listed the Germanium transistors as OC44 but there are many Germanium types that would fit the bill. It's handy to have a transistor tester (I use the Peak Atlas DCA55) to measure the hfe and it's also a good idea to check the bias points (Germanium transistors can be quite leaky) - [Electrosmash](https://www.electrosmash.com/fuzz-face) is a good resource for getting the setup perfect.

Component list
--------------

|Name|Component|Value|
|:---|:---|:---|
|R1|Resistor|47K|
|R2|Resistor|470K|
|R3|Resistor|1M|
|R4|Resistor|22K|
|R5|Resistor|100K|
|R6|Resistor|100R|
|R7|Resistor|33K|
|R8|Resistor|4K7|
|R9|Resistor|33K|
|R10|Resistor|3K9|
|R11|Resistor|22K|
|R12|Resistor|22K|
|R13|Resistor|100R|
|C1|Radial Electrolytic|47uF|
|C2|Radial Electrolytic|22uF|
|C3|Polyester Capacitor|100nF|
|C4|Radial Electrolytic|10uF|
|C5|Radial Electrolytic|10uF|
|C6|Radial Electrolytic|10uF|
|C7|Radial Electrolytic|10uF|
|C8|Radial Electrolytic|22uF|
|C9|Polyester Capacitor|3.9nF|
|C10|Radial Electrolytic|2.2uF|
|C11|Radial Electrolytic|2.2uF|
|C12|Radial Electrolytic|2.2uF|
|C13|Polyester Capacitor|10nF|
|C14|Polyester Capacitor|10nF|
|J1|Switched 5.5mm Barrel Jack||
|LED1|5mm LED||
|Q1|OC44 hfe 70-80||
|Q2|2N3904||
|Q3|OC44 hfe 110-130||
|Q4|2N3904||
|U1|ICL7660S||
|U2|ICL7660S||
|U3|7909 TO220||
|U4|RC4558||
|VR1|RD901F Potentiometer|B5K|
|VR2|RD901F Potentiometer|A100K|
|VR3|RD901F Potentiometer|A100K|
