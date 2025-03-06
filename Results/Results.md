# Results

This section presents measurements of the switched-mode power supply (SMPS) taken with an oscilloscope. Following that, a discussion section will analyze the results. The measurements were made with a 50-ohm load on the power supply.

## Vin

This is the waveform of the input voltage from the electrical grid.

<p align="center">
  <img src="/images/Results/Vin.png" alt="Vin">
</p>

## Vdin

This is the waveform of the voltage across one of the rectifier diodes.

<p align="center">
  <img src="/images/Results/Vdin.png" alt="VDin">
</p>

## Vx

This is the waveform of the output voltage from the rectifier, which serves as the input to the Buck converter. It is also the same waveform as the filter capacitor voltage.

<p align="center">
  <img src="/images/Results/Vx.png" alt="Vx">
</p>

## Vmosf

This is the waveform of the voltage between the drain and source of the MOSFET.

<p align="center">
  <img src="/images/Results/Vmosf.png" alt="Vmosf">
</p>

## VDo

This is the waveform of the voltage across the diode of the Buck converter.

<p align="center">
  <img src="/images/Results/VDo.png" alt="Vdo">
</p>

## VLo

This is the waveform of the voltage across the inductor Lo.

<p align="center">
  <img src="/images/Results/VLo.png" alt="VLo">
</p>

## Vout

This is the waveform of the output from the switched-mode power supply.

<p align="center">
  <img src="/images/Results/Vout.png" alt="Vout">
</p>

## Discussion

The waveforms of the rectifier were exactly as expected. The grid had an RMS voltage of approximately 130V, which was within the expected range, with a frequency of approximately 60 Hz, which is correct for Brazil.

The voltage across the diode behaved as anticipated, conducting during one half-cycle of the sine wave, while being blocked during the other half-cycle.

The rectifier output voltage exhibited a ripple of 5.85%, slightly higher than the design target of 5%. The ripple was calculated by observing only the image of Vx, which shows a different maximum voltage compared to the maximum voltage in the Vin image, likely due to the oscilloscope’s timebase settings during the measurements.

$$ \% \text{Ripple} = \left( \frac{V_{\text{ripple}}}{V_{\text{DC}}} \right) \times 100 $$

$$ V_{\text{ripple}} = V_{\text{max}} - V_{\text{min}} $$

$$ V_{\text{DC}} = \frac{V_{\text{max}} + V_{\text{min}}}{2} $$

In the Buck converter, the MOSFET voltage waveform matched expectations, showing that most of the time the MOSFET is not conducting. This is expected since the converter's gain is relatively small.

The diode voltage waveform exhibited the expected complementary behavior, with the diode conducting most of the time, as theorized, while the MOSFET is off.

The frequencies of these two waveforms closely match the value provided in the datasheet, which specifies a typical frequency of 66 kHz.

The waveform of the voltage across the inductor exhibited the correct shape: when the MOSFET is on, the inductor has a positive voltage, and when the MOSFET is off, the inductor exhibits a negative voltage. This is as expected based on the theory. What deviates from the standard is the frequency measurement, as it should match the frequency of the MOSFET and the diode.

This discrepancy is due to the on/off control method of the LNK306 IC, which causes the MOSFET to remain off for several cycles. As a result, the converter frequency is lower than 66 kHz during certain periods.

Although the IC shows some flaws in its control method, the power supply still performed satisfactorily.

Unfortunately, shunt resistors were not placed on the board to measure currents in the components, which would be an interesting addition for future projects.
