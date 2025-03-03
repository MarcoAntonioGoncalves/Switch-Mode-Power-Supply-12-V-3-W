# Voltage Sensor

The LKN-306 IC operates as a closed-loop control system, with feedback from the voltage sensor. According to the component's datasheet, the PWM adjustment is always made in such a way that the voltage at the feedback pin is 1.65V. To achieve this, a voltage divider should be designed using two resistors so that, with the specified output voltage of the source (12V), the voltage at the feedback pin will be 1.65V.

<p align="center">
  <img src="/images/components/LNK/LNKCircuit.png" alt="Datasheet Circuit">
</p>

The datasheet recommends adding a diode and a capacitor with the same specifications to replicate the output voltage to the voltage divider. The voltage divider results in R1 being 13.8 kΩ and R2 being 2.2 kΩ. A 10kΩ potentiometer will be used for R1, allowing the output voltage of the power supply to be adjustable.