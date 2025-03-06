# Inductor Project

Inductors are crucial components for the operation of a DC-DC converter. When operating at high frequencies, these components can exhibit a range of non-idealities, potentially leading to undesirable results such as voltage spikes, high losses, and noise emission.

Unlike other components, the inductor will not be purchased as a finished product but rather constructed from an EE-type ferrite core and enameled copper wire. The design equations were taken from a paper guided by Professor Ivo Barbi called:[Projeto Físico de Indutores e Transformadores](https://professorpetry.com.br/Bases_Dados/Apostilas_Tutoriais/Apostila_Projeto_Fisico_De_Magneticos.pdf), which shows how to build magnetic elements for high-frequency operation.

This section will discuss the selection of the magnetic core, the choice of the enameled copper wire type, and the necessary parameters for the construction of the inductor. It is important to note that the inductance of the inductor was previously calculated and should be 2.670 mH.

## Product of the Areas Ae and Aw

The product of the areas Ae and Aw is of utmost importance in the selection of the magnetic core used, as it determines the energy storage capacity, magnetic efficiency, and thermal performance.

<p align="center">
  <img src="/images/components/Indutor/AexAw.png" alt="Ae x Aw">
</p>

A component present in the inductor that has not been mentioned yet is the spool, where the core will be inserted and the wire will be wound.

The minimum product of the areas that the core must have is calculated according to the equation below:

$$ A_e \cdot A_w = \frac{L_o \cdot i_{LoRms} \cdot i_{LoMax}}{\Delta B \cdot J_{max} \cdot K_w} $$


The parameters not yet mentioned in this equation are those in the denominator. $J_{\text{max}}$ represents the maximum current density in the inductor, $K_w$ represents the area utilization factor that will actually be used by the copper winding, and $\Delta B$ represents the magnetic flux density of the EE-type ferrite core. For $K_w$ and $J_{\text{max}}$, there are typical values that are widely used by designers. For the first, the value is 0.7, and for the second, it is 450 A/cm². As for $\Delta B$, it is necessary to consult manufacturers' datasheets to obtain it. Below is an image from a catalog by Thorton, a company that manufactures magnetic cores.

<p align="center">
  <img src="/images/components/Indutor/NucleosCatalog.png" alt="Magnetic Cores">
</p>

Through the catalog, it is possible to notice that the flux density of the IP12R material (the material of the core that will be acquired) is 0.510 T. This value could be used as $\Delta B$, but to allow for a safety margin, the value used will be 0.35.

With all the acquired values, it is possible to find the product between the areas $A_e$ and $A_w$.

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
      <td>ΔB (Magnetic Flux Density)</td>
      <td>0.35</td>
      <td>T (Tesla)</td>
    </tr>
    <tr>
      <td>Kw (Area Utilization Factor)</td>
      <td>0.7</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Jmax (Maximum Current Density)</td>
      <td>450</td>
      <td>A/cm²</td>
    </tr>
    <tr>
      <td>Ae × Aw (Product of Areas)</td>
      <td>0.0171</td>
      <td>cm⁴</td>
    </tr>
  </tbody>
</table>



The product of the areas of the selected core must be at least the value calculated above, taking care to avoid over-dimensioning, which would increase the project costs unnecessarily.

Thornton offers a catalog with various options for magnetic cores. From this document, several options were analyzed, and the NEE-20/10/5 was selected. It has an area product of 0.07905 cm⁴, which is slightly larger than the calculated value but not as large as other options found. Additionally, it is a relatively inexpensive component, making it ideal for use in the project.

<p align="center">
  <img src="/images/components/Indutor/Core-NEE20-10-5.png" alt="Core NEE-20/10/5">
</p>

## Number of Turns

The inductor is constructed by winding an enameled copper wire around a spool, and then introducing the magnetic core with a certain gap to result in the desired inductance. The expression below calculates the number of turns the inductor should have, i.e., how many loops are required around the spool to achieve the calculated value.

$$ N_e = \frac{L_o \cdot i_{\text{LoMax}}}{\Delta B \cdot A_e} $$

The equation results in 69.29 turns. Since the number of turns must be an integer, the nearest whole number will be chosen, so 69 turns will be wound around the spool.

## Air gap

The air gap refers to the distance between the legs of the magnetic core. Below is an image to better illustrate it:

<p align="center">
  <img src="/images/components/Indutor/AirGap.png" alt="Air Gap">
</p>

The air gap is added mainly for two reasons. Without it, the inductance is only proportional to the magnetic permeability of the core, which can easily change due to temperature and operating point. Adding an air gap introduces a reluctance, which is the opposition to the passage of magnetic flux, much higher, making the inductance value less influenced by variations in the core's permeability. The other reason is that it allows the inductor to operate with higher currents in the winding without the core reaching saturation.

The distance of the air gap can be calculated using the expression below:

$$ \text{AirGap} = \frac{N^2 \cdot A_e \cdot \mu_o}{L_o} $$

The new parameter that appears in the equation is the magnetic permeability of air, which has the known value of $4\pi \times 10^{-7}$. By calculating the air gap distance, the obtained value is 0.07 millimeters.

Obviously, it will be extremely difficult to achieve such a small distance manually. What will be done in practice is placing a thin material between the legs of the core pair, such as a small piece of paper, and pressing the assembly until the desired inductance is achieved. Once it is obtained, tape will be applied to the inductor to secure the assembly.

## Enamelled Copper Wire

For high-frequency projects, the skin effect must be taken into account when choosing a conductor. This effect, causes electrons inside a conductor to tend to distribute along the periphery, resulting in a higher current density at the edges of the conductor than in the central region. This effect reduces the effective area of the conductor. Thus, it is possible to use an equation to calculate the maximum diameter the conductor can have.

$$ D_{\text{max}} = \frac{15}{\sqrt{F_s}} $$

This equation provides the result in centimeters and uses only the switching frequency as a parameter. The maximum diameter resulted in 0.058 centimeters. Thus, the wire gauge chosen cannot exceed this value.

The book *Projeto de Fontes Chaveadas* by Professor Ivo Barbi provides a table with relevant information about enamel-coated wires.

<p align="center">
  <img src="/images/components/Indutor/Wires.png" alt="enamel-coated wires">
</p>

It is possible to observe the copper diameter in the second column of the table. For this project, the chosen enamel-coated wire is AWG 26.
To determine whether a single wire or a combination will be necessary, it is required to calculate the minimum area needed for the effective current dimensioned in the project to flow through the inductor. After this calculation, simply divide the calculated required area by the copper area of the conductor, which is present in the table. The equations to obtain the answers are shown below:

$$ A_{\text{necessary}} = \frac{i_{\text{LoRms}}}{J_{\text{max}}} $$

$$ N_{\text{wires}} = \frac{A_{\text{necessary}}}{A_{\text{table}}} $$

The minimum area required calculated was 5.57E-04 cm², and the conductor area from the AWG 26 table is 0.001287 cm². Solving for the number of wires, we obtain a value of 0.43. Therefore, it will not be necessary to use a parallel wire configuration; a single wire will be sufficient to comfortably conduct the effective current circulating through the inductor.

## Inductor Losses  
As was done for the other components, it is necessary to calculate the losses that occur in the inductor. These losses are composed of copper losses due to Joule's effect, and magnetic losses, which occur in the core.

### Copper Losses
To calculate the copper losses, it is necessary to first calculate the 
resistance presented by the winding:

$$ R_{\text{cooper}} = \frac{R_{\text{wire}} \cdot L_{\text{turn}} \cdot N}{N_{\text{fios}}} $$

The new parameters that appear in this equation are the resistance of the wire and the average length of a turn. The first is obtained from figure from the book, and the worst-case scenario will be used, with a conductor temperature of 100°C. The resistance value in this case is 0.001419 Ω. The second is taken from the Thornton datasheet, and its value is 4.3 centimeters. Solving this gives a resistance of approximately 0.422 Ω.
With the resistance value, we can use the well-known power equation that relates resistance and current:

$$ P = R_{\text{cooper}} \times I_{\text{LoRms}}^2 $$

By performing the calculation, it is possible to observe that the loss is 0.026 W.

### Magnetic Losses
According to Ivo Barbi, the magnetic losses are related to hysteresis and can be calculated through an empirical expression:

$$ P = \Delta B^{2.4} \cdot (K_h \cdot f_s + K_f \cdot F_s^2) \cdot Volume_{\text{core}} $$

In this equation, there are some parameters that have not yet been presented in this document, which are $K_h$, $K_f$, and the volume of the core. The values of $K_h$ and $K_f$ are respectively $4 \times 10^{-5}$ and $4 \times 10^{-10}$. These values were taken from Ivo Barbi's material, and according to him, they are standard values for Thornton cores. The core volume is taken from the datasheet, with a value of $1.34 \, \text{cm}^3$. The expression results in $0.472 \ \text{W}$.

### Total losses

The total losses are calculated with the equation bellow. For this inductor it results in 0,498W.

$$ P_{\text{total}} = P_{\text{magnetic}} + P_{\text{cooper}}$$





