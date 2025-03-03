# Bridfe Retifier

A bridge rectifier consists of four diodes connected in such a way that both the positive and negative half-cycles of the AC waveform are rectified. Although there are components that encapsulate all four diodes, this project will use four separate diodes.

The criteria for selecting a diode were discussed in the section about the DC-DC converter and remain the same: it must withstand the average current and the maximum reverse voltage. Unlike the diodes used in the converter, the rectifier diode does not need to be ultra-fast, since the mains frequency is significantly lower than the switching frequency of the converter.

The average current through the diode is 0.0107 A, and the maximum reverse voltage is 329.51 V. Applying the safety coefficient, the selected diode must have a current rating higher than 0.013375 A and a voltage rating greater than 411 V.

The chosen diode is the 1N4007, a well-known and widely used component in rectifier circuits.

<p align="center">
  <img src="/images/components/BridgeRetifier/1n4007.png" alt="1N4007 specifications">
</p>

It can be observed from the datasheet that the 1N4007 diode supports a maximum reverse voltage of 700V, which is much higher than the calculated value. It is also evident that it can conduct a forward current of 1A, which is also much higher than all the calculated and simulated currents for the diode. In summary, it is a reliable component for the function it will serve.

<p align="center">
  <img src="/images/components/BridgeRetifier/FowardVoltage.png" alt="Forward Voltage">
</p>

As discussed in the buck converter section, the curve above is important for obtaining the forward voltage at the operating point and an estimate of the diode's resistance, which are key parameters for thermal calculations. The method to find these quantities has already been discussed earlier. By observing the figure and performing the calculations, it is possible to see that the forward voltage is approximately 0.7V and the resistance is approximately 0.133Ω. Since the frequency is very low, only the conduction losses will be calculated.

<table align="center">
  <thead>
    <tr>
      <th><strong>Parameter</strong></th>
      <th><strong>Value</strong></th>
      <th><strong>Unit</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Max Reverse Voltage </td>
      <td>329,51</td>
      <td>V</td>
    </tr>
    <tr>
      <td>I med</td>
      <td>0,0107</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Power Loss</td>
      <td>0,0079</td>
      <td>W</td>
    </tr>
    <tr>
      <td>Junction Temperature</td>
      <td>50,79</td>
      <td>ºC</td>
    </tr>
  </tbody>
</table>

It is possibile to see that the chosen component has greater limits then the calculated above.