## Switch Power Supplys

Switching power supplies are electrical devices that convert energy from one form to another using electronic switching, typically with transistors, to control the flow of current. They are highly efficient because they operate at high frequencies, minimizing energy losses and allowing for a compact design. The process involves rectifying alternating current (AC) to direct current (DC), followed by fast switching control and filtering to reduce ripple in the output, using a Dc-Dc Converter.

It's circuit can be simplified into a few main parts. A rectifier, which serves to convert alternating current (AC) into direct current (DC), a DC-DC converter, which reduces the input voltage, and a control circuit, which maintains the output voltage at the desired value and generetes the PWM to the eletronic switch.
There are also RF filters, but they are not implemented in this project.

![Simplified Block Diagram](../images/Switch%20Power%20Supply%20Simplified%20Block%20Diagram.png)

Switching power supplies are generally superior to linear power supplies due to their higher efficiency, smaller size, and lower heat dissipation. Unlike linear regulators, which dissipate excess energy as heat, switching power supplies use high-frequency switching circuits to regulate voltage with minimal energy loss. This results in significantly higher efficiency, often exceeding 80-90%, compared to linear supplies, which typically operate at around 50% efficiency or lower. Additionally, switching power supplies are more compact and lightweight because they require smaller transformers and heatsinks. These advantages make them ideal for modern electronic applications, including embedded systems, battery-powered devices, and industrial equipment.


