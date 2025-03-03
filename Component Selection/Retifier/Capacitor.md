# Capacitor 

Just like in the DC-DC converter, the filter capacitor must have a nominal voltage higher than the peak voltage of the power supply, withstand an effective current greater than the one flowing through it, and have a capacitance value greater than the calculated one. However, unlike the DC-DC converter, the capacitor for the rectifier does not need to be from the AX series and can be a general-purpose capacitor.

The capacitance calculation resulted in 26.48 µF, so three 10 µF capacitors will be used in parallel, resulting in a total capacitance of 30 µF. The nominal voltage, after applying the safety coefficient, is 411 V, and the effective current flowing through the component is 0.088 A, which results in 0.110 A with the safety coefficient applied.

A 400 V capacitor will be selected. Although this is slightly lower than the calculated value, it should still perform adequately since the maximum voltage of the power supply without the safety coefficient is 329.51 V.

The selected capacitors are from Nichicon, and below is an image from the datasheet.

<p align="center">
  <img src="/images/components/FilterCapacitor/FilterCapacitor.png" alt="Nichicon datasheet">
</p>

It is observed that a Nichicon 10 µF 400V capacitor can withstand an RMS current of 72 mA, which is lower than the calculated value. Therefore, multiple capacitors are required to handle the effective current. Since three capacitors are being used in parallel, the maximum current capacity of the combination is 216 mA, which is more than sufficient even after applying the safety coefficient.

Unfortunately, the datasheet does not provide information on the equivalent series resistance (ESR) for capacitors with a nominal voltage above 100V. Therefore, for loss calculations, the ESR value for a 10 µF 100V capacitor will be used, which is 1.8 Ω.

Since the three capacitors are in parallel, the current will be evenly divided among them, and each capacitor will experience the same power dissipation. The formulas for this calculation have already been discussed in buck converter section.

<table align="center">
  <thead>
    <tr>
      <th><strong>Parameter</strong></th>
      <th><strong>Simulated/Calculated</strong></th>
      <th><strong>Safety Coefficient</strong></th>
      <th><strong>Component</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Capacitance (µF)</td>
      <td>26.48</td>
      <td>X</td>
      <td>30</td>
    </tr>
    <tr>
      <td>Nominal Voltage (V)</td>
      <td>329.51</td>
      <td>411.88</td>
      <td>400</td>
    </tr>
    <tr>
      <td>Irms (A)</td>
      <td>0.088</td>
      <td>0.110</td>
      <td>0.216</td>
    </tr>
    <tr>
      <td>Dissipated Power (W)</td>
      <td>0.0046</td>
      <td>X</td>
      <td>X</td>
    </tr>
  </tbody>
</table>
