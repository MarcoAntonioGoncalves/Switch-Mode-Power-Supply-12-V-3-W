# Full Wave Retifier

The rectifier used will be the full-wave rectifier with a capacitive filter. The equations used for the design were taken from the book Projeto de Fontes Chaveadas by Ivo Barbi. The simplified analysis method was used, which, although it generates some inconsistencies between the simulated and calculated values, is reliable for the design, mainly because the ripple in the capacitor is less than 20%.

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

    








