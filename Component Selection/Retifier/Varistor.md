# Varistor

The varistor serves to protect the circuit from voltage spikes. This type of component has a nominal voltage value, and when this value is exceeded, it operates as if it were a short circuit, causing the current to flow through it instead of reaching the circuit.

Below, you can see a Voltage vs. Current graph comparing a varistor with a standard resistor.

<p align="center">
  <img src="/images/components/Varistor/VaristorCurve.png" alt="Varistor IXV curve">
</p>

To select the varistor, it is necessary to consider the maximum RMS operating voltage of the switched-mode power supply and choose a component with a nominal voltage higher than this value. For this project, the RMS voltage is 233 V, so the selected varistor must have a nominal voltage of at least 291.25 V (after applying the safety coefficient).

The chosen component is the S05K300, which has a nominal voltage of 300 V, providing a sufficient margin even with the applied safety coefficient.

<p align="center">
  <img src="/imges/components/Varistor/Varistor.png" alt="Varistor">
</p>