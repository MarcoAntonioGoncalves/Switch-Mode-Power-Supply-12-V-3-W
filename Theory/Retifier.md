# Full Wave Retifier

The design employs a full-wave rectifier with a capacitive filter. The equations for this design were derived from the book Projeto de Fontes Chaveadas by Ivo Barbi. A simplified analysis method was applied, which, while causing slight discrepancies between the simulated and calculated results, remains reliable for the design, especially considering that the ripple in the capacitor is kept under 20%.

# Equations

* ## Input Power
    $P_{\text{in}} = \frac{P_{\text{out}}}{\eta}$
* ## Filter Capacitor
    $C = \frac{P_{\text{in}}}{F_{\text{grid}} \left( V_{\text{peakMin}}^2 + V_{\text{cMin}}^2 \right)}$
* ## Reload Capacitor Time or Diode Conduction Time
    $t_c = \frac{\cos^{-1}\left( \frac{V_{\text{cMin}}}{V_{\text{peakMin}}} \right)}{2 F_{\text{grid}} \pi}$
* ## Peak Input Current
    $I_p = \frac{C \left( V_{\text{peakMin}} - V_{\text{cMin}} \right)}{t_c}$
* ## Rms Value of Alterned Component of Input Current
    $I_{\text{ClRms}} = I_p \sqrt{ 2 t_c F_{\text{grid}} - \left( 2 t_c F_{\text{grid}} \right)^2 }$
* ## Rms Output Current
    $I_{\text{outRms}} = \frac{P_{\text{in}}}{V_{\text{cMin}}}$
* ## Rms Capacitor Current
    $I_{\text{cRms}} = \sqrt{ I_{\text{outEfc}}^2 + I_{\text{Clef}}^2 }$
* ## Avarage Diode Current
    $I_{\text{dAvg}} = \frac{P_{\text{in}}}{2 V_{\text{cMin}}}$
* ## Rms Diode Current
    $I_{\text{dRms}} = I_p \sqrt{ \frac{t_c}{T} }$
* ## Peak Diode Current
    $I_{\text{dPeak}} = I_p$
* ## Max Diode Reverse Tension
    $V_{\text{dMax}} = V_{\text{peakMax}}$


# Theorical Results X Simulation Results

Analyzing the results, it is evident that the theoretical values closely match the simulated ones, except for the peak current. This discrepancy arises because, in the simplified analysis, the input current is assumed to have a rectangular waveform, whereas in practice, this is not the case. By examining the input current waveform, it becomes clear that it follows a triangular shape, corresponding to a segment of a cosine wave. According to the reference book, the actual peak current can be approximated as twice the theoretical value. In this project, this approximation results in a peak current of 0.490 A, which is remarkably close to the value obtained through simulation. To check the simulation values obtained, go to the  [simulations](../Simulations/Retifier.md) section.
    
### Rectifier Parameters

| **Parameter**   | **Theoretical** | **Simulation** | **Unit** |
|---------------|---------------|--------------|---------|
| Pin          | 3.75          | 3.75         | W       |
| Capacitance (C) | 26.48         | 26.48        | µF      |
| Charging Time (tc) | 0.84          | 0.80         | ms      |
| Peak Current (Ip)  | 0.245         | 0.492        | A       |
| Effective Output Current (IoutEfc) | 0.025         | 0.026        | A       |
| Effective Capacitor Current (ICef) | 0.077         | 0.088        | A       |
| Average Diode Current (IDmed) | 0.0126        | 0.0107       | A       |
| Effective Diode Current (IDef) | 0.054         | 0.059        | A       |
| Peak Diode Current (IDp) | 0.245         | 0.493        | A       |
| Maximum Diode Voltage (Vdmáx) | 329.51        | 329.51       | V       |







