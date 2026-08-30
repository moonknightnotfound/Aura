# Ambient RF HARVESTER:
As a battery-less and power-source-less project.The harvester has the role to provide Electrical Power to the entire device to perform backscatter. So the harvester circuit has the function to harvest electrical energy from the ambient rf signals present in the surrounding environment.

1] Antenna:
The Antenna has the function to capture the Ambient RF signals.The antenna acts as a transducer, converting ambient electromagnetic waves into alternating current (AC). 

2] Impedance Matching Network:
The Impedance Matching network has the function to maximize the ambient rf signals induction in the antenna.RF signals bounce back if impedances don't match. The impedance matching network (an LC circuit) ensures the 50-ohm antenna perfectly transfers its power to the rectifier without reflection losses. 

3] RF-to-DC Rectifier:(Voltage Multiplier):
The Voltage Multiplier circuit has to two functions:
1.Converting or rectifying the induced AC voltage into DC voltage.
2. Multiply or increase the voltage as the input induced voltage is in the range of microvolts to 0.5 V, which is very less. So the circuit brings the voltage at the level which runs our device.

4] Power Management IC:
This Power management IC regulates the amount of power to be supplied to the microcontroller.
It’s function is to accumulate the power from the voltage multiplier circuit and then when the power accumulated will be sufficient for the microcontroller to do backscatter operation, so at that time the pmic will discharge and microcontroller will perform its work.

5] Energy Storage:
As a battery-free device the energy storage will be done by using super-capacitor. It will be connected to PMIC.

6] Load(Microcontroller):
The Microcontroller will use the harvested power to perform backscatter.

