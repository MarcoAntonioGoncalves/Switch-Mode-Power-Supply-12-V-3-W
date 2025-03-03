# Termistor

A thermistor is a resistor that changes its resistance according to temperature. Its function is to limit the current in the rectifier diodes while the power supply is in a transient state. When powered on from the electrical grid, the filter capacitor is discharged, causing the circuit to momentarily draw a high current, which can damage components. Therefore, to size the appropriate thermistor, it is necessary to observe the maximum surge peak current that the diode is capable of conducting. For the 1N4007, this value is 30A. For safety factors, the maximum current will be multiplied by 0.7 for sizing.

To determine the thermistor's resistance at 25°C, the following relation is used:

$$R_{\text{termistor}} = \frac{V_{\text{peakMax}}}{i_{\text{transitoryDiode}}}$$

Knowing that the maximum peak voltage is 329.51 V and the transient current is 21 A, the resistance value for the thermistor is approximately 15 Ω. Since this commercial value was not found, a thermistor with a resistance of 20 Ω at 25°C was chosen.

In operation, the input current tends to heat the thermistor due to the Joule effect, causing the temperature around it to increase and consequently the resistance to decrease, resulting in lower losses to the circuit.