## Diode Do

The diode chosen for the converter must be capable of conducting the average current with a certain safety margin and withstand a reverse voltage greater than the maximum reverse voltage calculated previously. Another important point is the reverse recovery time, which is a very important parameter when this component operates at high frequencies.

Reverse recovery time is the time required for the diode to stop conducting current after the voltage is reversed. This occurs because there is a parasitic capacitance in parallel with the diode, causing the component to stop conducting only after the capacitance is completely discharged. This time can be a limiting factor for high-frequency operation, so the component must have a reverse recovery time smaller than the designed value. Diodes with this characteristic belong to the ultra-fast family, so the chosen component will belong to this class.

The maximum reverse operation time was obtained according to a rule of thumb used by many designers:

$$ T_{rr} < \frac{1}{f_s} \cdot 0.005 $$

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
      <td>Reverse Recovery Time (nS)</td>
      <td>75.75</td>
      <td>nS</td>
    </tr>
    <tr>
      <td>Maximum Reverse Voltage (V)</td>
      <td>-411.89</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Average Current (A)</td>
      <td>0.287</td>
      <td>A</td>
    </tr>
  </tbody>
</table>

It should be noted that the values are higher than they would typically be because a safety coefficient of 1.25 was applied, making the design more reliable and secure.

The chosen diode belongs to the ultra-fast family, and it is the UF4007. Its specifications are as follows:

<p align="center">
  <img src="/images/components/Diodo/SpecificationsUF4007.png" alt="UF4007 specification">
</p>

The most important parameters are in the table below:

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
      <td>Reverse Recovery Time (nS)</td>
      <td>75</td>
      <td>nS</td>
    </tr>
    <tr>
      <td>Maximum Reverse Voltage (V)</td>
      <td>-1000</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Average Current (A)</td>
      <td>1</td>
      <td>A</td>
    </tr>
  </tbody>
</table>

It is evident that the component's datasheet values satisfy the calculated values.

## Thermical Calculation

Just like the MOSFET, the thermal calculation of the diode is necessary to verify if its junction temperature during operation does not exceed the maximum value defined by the datasheet. To do this, some information such as the voltage at the operating point and the diode resistance is required, along with the energy stored in the parasitic capacitance. The datasheet and some equations will be used to obtain these parameters.

To obtain the maximum voltage, it is necessary to know the maximum current that the diode is subjected to. Once calculated, simply refer to the graph in the figure below and find the voltage that corresponds to the calculated current. It is calculated using the formula below.

$$ I_{doMax} = I_{Ro} + \frac{\Delta L_o}{2} $$

<p align="center">
  <img src="/images/components/Diodo/FowardVoltage.png" alt="Forward Voltage">
</p>

To obtain the diode's resistance in conduction, the same graph is used. It is known that the derivative of the Current vs. Voltage curve gives the resistance. Therefore, two points close to each other will be selected so that they approximately form a straight line. The first point is (0.3; 1.2), and the second point is (0.8; 1.4). The equation is below:

$$ R_{Do} = \frac{V_2 - V_1}{I_2 - I_1} $$

To obtain the energy stored in the capacitor in parallel with the diode, the following equations are required:

$$ \frac{di}{dt} = -\frac{V_o}{L_o} $$

$$ Q_{rr} = \frac{T_{rr}^2 \cdot \left( \frac{di}{dt} \right)}{3} $$

The losses in the diode are calculated with the equations below:

$$ P_{\text{cond}} = V_f \cdot I_{\text{DoMed}} + R_{\text{do}} \cdot I_{\text{efc}}^2 $$

$$ P_{\text{bloq}} = Q_{\text{rr}} \cdot F_s \cdot |V_{\text{DoMax}}| $$

$$ P_{\text{total}} = P_{\text{cond}} + P_{\text{bloq}} $$

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
      <td>Maximum Current</td>
      <td>0.28</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Forward Voltage (Vf)</td>
      <td>1.2</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Diode Resistance</td>
      <td>0.4</td>
      <td>Ω</td>
    </tr>
    <tr>
      <td>di/dt</td>
      <td>-4490</td>
      <td>A/s</td>
    </tr>
    <tr>
      <td>Qrr</td>
      <td>8.42</td>
      <td>nC</td>
    </tr>
    <tr>
      <td>Conduction Power (Pcond)</td>
      <td>0.298</td>
      <td>W</td>
    </tr>
    <tr>
      <td>Blocking Power (Pbloq)</td>
      <td>1.83E-04</td>
      <td>W</td>
    </tr>
    <tr>
      <td>Total Power</td>
      <td>0.299</td>
      <td>W</td>
    </tr>
  </tbody>
</table>

With the necessary information gathered, it is now possible to calculate the junction temperature of the diode without the presence of a heatsink. The table below contains the required information for the calculation. The equation that gives the junction temperature is exactly the same as the one used for the MOSFET.

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
      <td>Maximum Junction Temperature</td>
      <td>150</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Maximum Junction Temperature (C.S)</td>
      <td>112.5</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Ambient Temperature</td>
      <td>50</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Junction-to-Ambient Resistance</td>
      <td>60</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Junction Temperature Without Heatsink</td>
      <td>67.90</td>
      <td>°C</td>
    </tr>
  </tbody>
</table>

It is clear that the junction temperature is well below the maximum temperature, even when considering the safety factor. Therefore, it can be concluded that the UF4007 diode is suitable for operation.