# Capacitor Co

The capacitor Co must be capable of handling the effective current it will be subjected to, have a voltage rating higher than the output voltage, and a capacitance greater than the value calculated in the theorical calculations. Additionally, it should exhibit low impedance at high frequencies, minimizing losses and improving overall performance

## Calculated Parameters for the Capacitor

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
      <td>$i_{\text{CoRms}}$</td>
      <td>0.022</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Voltage Rating</td>
      <td>15</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Capacitance</td>
      <td>1.28</td>
      <td>µF</td>
    </tr>
  </tbody>
</table>

## Selection

The AX series capacitors are well-suited for high-frequency operation, making them an ideal choice for Co. Since the calculated capacitance value is not commercially available, a higher standard value of 22 µF, 50V will be used. Below is the SANYO catalog containing detailed specifications for the selected capacitor. The chosen component is in the third line of the table.

<p align="center">
  <img src="/images/components/Capacitor%20Co/System%20Diagram.png" alt="System Diagram for Power Supply">
</p>

<p align="center">
  <img src="/images/components/Capacitor%20Co/Capacitors%20Paramenters.png" alt="Capacitor Paramenteres">
</p>

Below is a table with the specifications of the selected component. The minimum number of capacitors required to handle the necessary effective current and the dissipated power were calculated using the formulas below, while the remaining parameters were obtained from the catalog.

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
      <td>Capacitance</td>
      <td>22</td>
      <td>µF</td>
    </tr>
    <tr>
      <td>Effective Current</td>
      <td>0.110</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Voltage Rating</td>
      <td>50</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Number of Capacitors (N)</td>
      <td>1</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Impedance</td>
      <td>0.7</td>
      <td>Ω</td>
    </tr>
    <tr>
      <td>Dissipated Power</td>
      <td>0.00022</td>
      <td>W</td>
    </tr>
  </tbody>
</table>


Comparing the calculated values with those of the real component, it is evident that the selected component has higher limits than those calculated, making it ideal for the project.

## Equations

$$ N = \left\lceil \frac{i_{\text{CoRms}}}{i_{\text{CoRmsComponent}}} \right\rceil$$

$$ P_{\text{cap}} = \text{Impedance } \cdot I_{\text{CoRms}}^2$$







