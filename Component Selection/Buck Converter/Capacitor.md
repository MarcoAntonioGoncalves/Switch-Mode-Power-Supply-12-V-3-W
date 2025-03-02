# Capacitor Co

The capacitor Co must be capable of handling the effective current it will be subjected to, have a voltage rating higher than the output voltage, and a capacitance greater than the value calculated in the theorical calculations. Additionally, it should exhibit low impedance at high frequencies, minimizing losses and improving overall performance

## Calculated Parameters for the Capacitor

| **Parameter**       | **Value** | **Unit** |
|--------------------|---------|---------|
| $i_{\text{CoRms}}$ | 0.022   | A       |
| Voltage Rating   | 15      | V       |
| Capacitance     | 1.28    | µF      |

## Selection

The AX series capacitors are well-suited for high-frequency operation, making them an ideal choice for Co. Since the calculated capacitance value is not commercially available, a higher standard value of 22 µF, 50V will be used. Below is the SANYO catalog containing detailed specifications for the selected capacitor. The chosen component is in the third line of the table.

![System Diagram for Power Supply](/images/components/Capacitor%20Co/System%20Diagram.png)

![Capacitor Paramenteres](/images/components/Capacitor%20Co/Capacitors%20Paramenters.png)

Below is a table with the specifications of the selected component. The minimum number of capacitors required to handle the necessary effective current and the dissipated power were calculated using the formulas below, while the remaining parameters were obtained from the catalog.

| **Parameter**       | **Value** | **Unit** |
|--------------------|---------|---------|
| Capacitance       | 22      | µF      |
| Effective Current | 0.110   | A       |
| Voltage Rating   | 50      | V       |
| Number of Capacitors (N) | 1  | - |
| Impedance        | 0.7     | Ω       |
| Dissipated Power | 0.00022 | W       |

Comparing the calculated values with those of the real component, it is evident that the selected component has higher limits than those calculated, making it ideal for the project.

## Equations

$N = \left\lceil \frac{i_{\text{CoRms}}}{i_{\text{CoRmsComponent}}} \right\rceil$

$P_{\text{cap}} = \text{Impedance } \cdot I_{\text{CoRms}}^2$







