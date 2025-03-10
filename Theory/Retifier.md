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
    

<table align="center">
  <thead>
    <tr>
      <th><strong>Parameter</strong></th>
      <th><strong>Theoretical</strong></th>
      <th><strong>Simulation</strong></th>
      <th><strong>Unit</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Pin</td>
      <td>3.75</td>
      <td>3.75</td>
      <td>W</td>
    </tr>
    <tr>
      <td>Capacitance (C)</td>
      <td>26.48</td>
      <td>26.48</td>
      <td>µF</td>
    </tr>
    <tr>
      <td>Charging Time (tc)</td>
      <td>0.84</td>
      <td>0.80</td>
      <td>ms</td>
    </tr>
    <tr>
      <td>Peak Current (Ip)</td>
      <td>0.245</td>
      <td>0.492</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Effective Output Current (IoutEfc)</td>
      <td>0.025</td>
      <td>0.026</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Effective Capacitor Current (ICef)</td>
      <td>0.077</td>
      <td>0.088</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Average Diode Current (IDmed)</td>
      <td>0.0126</td>
      <td>0.0107</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Effective Diode Current (IDef)</td>
      <td>0.054</td>
      <td>0.059</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Peak Diode Current (IDp)</td>
      <td>0.245</td>
      <td>0.493</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Maximum Diode Voltage (Vdmáx)</td>
      <td>329.51</td>
      <td>329.51</td>
      <td>V</td>
    </tr>
  </tbody>
</table>







