# Mosfet

When selecting the MOSFET, there are some key points to consider. Usually, it's sufficient to choose one with a drain-to-source voltage greater than the maximum calculated voltage and a drain current higher than the effective current that will flow through the component.

However, integrated circuits that contain an internal MOSFET are often used. These circuits perform closed-loop control of the output voltage and generate the PWM signal to switch the MOSFET. Using these components reduces the overall project cost, decreases the final PCB size, minimizes the number of components required for soldering, and provides an easy solution for generating the PWM signal that controls the switch. Due to these advantages, the LNK306-DG IC will be used in this project.

This IC contains an internal MOSFET and a PWM pulse generator, as well as a closed-loop control circuit for the output voltage, ensuring that it remains stable and at the designed value.

It is necessary to verify if the internal MOSFET can support a drain-to-source voltage higher than the calculated value for the worst-case scenario, as well as whether it can safely conduct the current required for the operation of the power supply.

Unlike usual, this IC does not provide the drain current that the switch can conduct in its datasheet. Instead, it provides the current variation rate that will trigger the overcurrent protection circuit. Therefore, to verify if the IC is suitable for use in the power supply, it is necessary to calculate the variation rate of the current and use the datasheet information for verification. It is calculated using the equation below:

$$
\frac{di}{dt} = \frac{V_{\text{peakMax}} - \Delta V_{\text{Cin}} - V_o}{L_o}
$$

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
      <td>Drain-Source Voltage (Vds)</td>
      <td>411.88</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Maximum Current</td>
      <td>0.25</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Average Current</td>
      <td>0.025</td>
      <td>A</td>
    </tr>
    <tr>
      <td>RMS Current</td>
      <td>0.089</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Di/Dt</td>
      <td>144.85</td>
      <td>mA/µs</td>
    </tr>
  </tbody>
</table>

It should be noted that the values are higher than they would typically be because a safety coefficient of 1.25 was applied, making the design more reliable and secure.

<p align="center">
  <img src="/images/components/Mosfet/AbsoluteMaxRatings.png" alt="Absolute Max Ratings">
</p>

It can be observed in the datasheet of the IC that its internal MOSFET has a maximum voltage rating of 700 V, which is more than sufficient for the project. Regarding the current, it will be necessary to refer to the figures below.

<p align="center">
  <img src="/images/components/Mosfet/NormalizedCurrentLimit.png" alt="Normalized Current Limit">
</p>
<p align="center">
  <img src="/images/components/Mosfet/CircuitProtection.png" alt="Circuit Protection">
</p>

To verify whether the current will be a problem for using this IC, it is necessary to calculate the di/dt in the MOSFET, which has already been done above, and check the resulting current limit value. If the current limit is lower than the calculated value, it means that the IC cannot be used.

Through the first figure, it can be observed that two points are provided: (95;450) and (610;508). The point on the X-axis represents the calculated di/dt, while the point on the Y-axis represents the maximum di/dt that will trigger the protection circuit. These points were chosen because they cover the worst-case scenario for the operation of the LNK306. It can be seen in the figure that the curve is a straight line, and with two points from this line, it is possible to find the equation that represents it. The equation and the resulting maximum current limit are shown below:

$$
\frac{di}{dt_{\text{máx}}} = 0,1126 \cdot \frac{di}{dt_{\text{calc}}} + 439,30
$$

$$
\frac{di}{dt_{\text{máx}}} = 455,61 \, \text{mA/μs}
$$

It is evident that the obtained value is significantly higher than the previously calculated value, allowing the internal MOSFET of the IC to conduct the required current for the operation of the switch-mode power supply without triggering the protection circuit.

## Thermical Calculation

To ensure proper MOSFET operation, its junction temperature during power supply operation must remain below the maximum temperature specified in the datasheet. To approximate the junction temperature without a heatsink, it is necessary to know the thermal resistance in °C/W between the junction and the ambient, as well as the ambient temperature in which the component operates. Additionally, the MOSFET's internal resistance while conducting and its rise and fall times are required. The obtained result should be compared with the maximum junction temperature supported by the IC, which is 150°C according to the datasheet. The maximum junction temperature was multiplied by 0.7 and further adjusted with the project's safety coefficient.

The information in the table below was extracted from the datasheet. The calculations performed were aimed at determining the power dissipation and the junction temperature without a heatsink.

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
      <td>135</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Maximum Junction Temperature (S.C.)</td>
      <td>101.25</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Ambient Temperature</td>
      <td>50</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Junction-to-Ambient Thermal Resistance</td>
      <td>70</td>
      <td>°C/W</td>
    </tr>
    <tr>
      <td>Junction Temperature Without Heatsink</td>
      <td>64.71</td>
      <td>°C</td>
    </tr>
    <tr>
      <td>Rds On</td>
      <td>12.9</td>
      <td>mΩ</td>
    </tr>
    <tr>
      <td>Rise Time Tr</td>
      <td>50</td>
      <td>ns</td>
    </tr>
    <tr>
      <td>Fall Time Tf</td>
      <td>50</td>
      <td>ns</td>
    </tr>
    <tr>
      <td>Conduction Power Pcond</td>
      <td>0.065</td>
      <td>W</td>
    </tr>
    <tr>
      <td>Switching Power Pcom</td


## Equations to Calculte Temperature

$$ T_j = P_{\text{total}} \cdot R_{\text{ja}} + T_a $$

$$ P_{\text{cond}} = R_{\text{ds(on)}} \cdot I_{\text{sRms}}^2 $$

$$ P_{\text{com}} = \frac{F_s \cdot (T_r + T_f) \cdot I_{\text{sMax}} \cdot V_{\text{peakMin}}}{2} $$

$$ P_{\text{total}} = P_{\text{cond}} + P_{\text{com}} $$










