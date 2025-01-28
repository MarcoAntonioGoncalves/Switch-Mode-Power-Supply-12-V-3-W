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

    








