# Buck Conveter

The non-isolated Buck Forward converter is a step-down voltage converter. It uses an electronic switch controlled by a PWM signal, and a combination of a diode and an inductor to decrease the output voltage in relation to the input. As the name suggests, there is no galvanic isolation between the power supply and the output of the circuit.

When it comes to DC-DC converters, there are three possible conduction modes: Continuous Conduction Mode (CCM), Discontinuous Conduction Mode (DCM), and Critical Conduction Mode (CRM), which refer to the current in the inductor. In CCM, the current never reaches zero; in CRM, the current reaches zero at the end of the cycle but quickly rises again; in DCM, the current in the inductor reaches zero and stays there for part of the cycle. Each mode leads to a different analysis of the circuit, causing the design equations to vary depending on the conduction mode used. For this project, Continuous Conduction Mode (CCM) will be considered.

# Equations

* ## Load Ro
  
$$R_o = \frac{V_o^2}{P_o}$$

$$i_{\text{Ro}} = \frac{V_o}{R_o}$$

* ## Dutty Cycle
  
    $$D_{\text{min}} = \frac{V_o}{V_{\text{xMin}}-\Delta V_{\text{Cin}}}$$

* ## Inductor 
    $$\Delta i_{\text{Lo}} = \Delta i_{\text{LoPercentage}} \cdot i_{\text{Ro}}$$

    $$L_o = D_{\text{min}}\left(\frac{V_{\text{peakMin}} - \Delta V_{\text{Cin}} - V_O}{F_s \Delta i_{\text{Lo}}}\right)$$

    $$i_{\text{LoMax}} = i_{\text{Ro}} \cdot \Delta i_{\text{Lo}}^2$$

    $$i_{\text{LoMed}} = i_{\text{Ro}}$$

    $$i_{\text{LoRms}} = \sqrt{\frac{\Delta i_{\text{Lo}}^2 + 12 i_{\text{Ro}}^2}{12}}$$
* ## Capacitor Co
    $$\Delta V_o = \Delta V_{\text{VoPercentage}}\cdot V_o$$

    $$C_o = \frac{2 \Delta i_{\text{Lo}} D_{\text{min}}}{\Delta V_o F_s}$$

    $$i_{\text{CoRms}} = \sqrt{\frac{\Delta i_{\text{Lo}}^2}{12}}$$
* ## Eletronic Switch
    $$i_{\text{sMax}} = i_{\text{Ro}} + \frac{\Delta i_{\text{Lo}}}{2}$$

    $$i_{\text{sMed}} = i_{\text{Ro}} \cdot D_{\text{min}}$$

    $$i_{\text{sRms}} = \sqrt{D_{\text{min}} \left( \frac{\Delta i_{\text{Lo}}^2 + 12 i_{\text{Ro}}^2}{12} \right)}$$

    $$V_{\text{sMax}} = V_{\text{peakMax}}$$
* ## Diode Do
    $$i_{\text{DoMax}} = i_{\text{Ro}} + \frac{\Delta i_{\text{Lo}}}{2}$$

    $$i_{\text{DoMed}} = i_{\text{Ro}} \cdot (1 - D_{\text{min}})$$

    $$i_{\text{DoRms}} = \sqrt{(1-D_{\text{min}}) \left( \frac{\Delta i_{\text{Lo}}^2 + 12 i_{\text{Ro}}^2}{12} \right)}$$

    $$V_{\text{DoMax}} = -V_{\text{peakMax}}$$

# Theorical Results X Simulation Results

The theoretical results were very close to those obtained through simulation, proving the quality of the methodology used in this project. To check the simulation values obtained, go to the [simulations](../Simulations/BuckConverter.md) section.

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
      <td>Load Voltage Ro</td>
      <td>12</td>
      <td>11.97</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Load Average Current Io</td>
      <td>0.25</td>
      <td>0.249</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Minimum Duty Cycle</td>
      <td>0.081</td>
      <td>0.081</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Inductor Current Ripple</td>
      <td>0.062</td>
      <td>0.060</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Inductor Inductance Lo</td>
      <td>2.670</td>
      <td>2.670</td>
      <td>mH</td>
    </tr>
    <tr>
      <td>Inductor RMS Current</td>
      <td>0.250</td>
      <td>0.249</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Inductor Maximum Current</td>
      <td>0.281</td>
      <td>0.280</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Inductor Average Current</td>
      <td>0.250</td>
      <td>0.249</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Output Voltage Ripple</td>
      <td>0.120</td>
      <td>0.09</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Output Capacitance Co</td>
      <td>1.280</td>
      <td>1.280</td>
      <td>µF</td>
    </tr>
    <tr>
      <td>Capacitor RMS Current</td>
      <td>0.018</td>
      <td>0.018</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Switch Maximum Current S</td>
      <td>0.281</td>
      <td>0.280</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Switch Average Current S</td>
      <td>0.020</td>
      <td>0.020</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Switch RMS Current S</td>
      <td>0.071</td>
      <td>0.071</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Switch Maximum Voltage</td>
      <td>329.511</td>
      <td>329.51</td>
      <td>V</td>
    </tr>
    <tr>
      <td>Diode Maximum Current Do</td>
      <td>0.281</td>
      <td>0.280</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Diode Average Current Do</td>
      <td>0.229</td>
      <td>0.229</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Diode RMS Current Do</td>
      <td>0.240</td>
      <td>0.239</td>
      <td>A</td>
    </tr>
    <tr>
      <td>Diode Maximum Voltage</td>
      <td>-329.511</td>
      <td>-329.51</td>
      <td>V</td>
    </tr>
  </tbody>
</table>
