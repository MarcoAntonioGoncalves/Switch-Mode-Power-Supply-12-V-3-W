# Switch-Mode-Power-Supply-12-V-3-W

## Introduction

My name is Marco Antonio Machado Gonçalves, and I am a Mechatronics Engineering student at the Universidade Federal do Paraná (UTFPR). I created this repository to help anyone interested in designing a switched-mode power supply. It provides a comprehensive step-by-step guide, including the underlying theory, key equations, and criteria for selecting components. The repository also includes the circuits implemented on the PCB, along with the schematic and board files, as well as simulations and the results obtained

I think it’s important to highlight that the theoretical part does not provide an in-depth analysis of the mesh and operational stages of the circuits. As a consequence, the deduction of the design equations is also not presented. What is expected to be found in the theory is an explanation of how the circuit works and the necessary equations for designing it.

I would like to give credit to the book [Projeto de Fontes Chaveadas](https://ivobarbi.com.br/livro-projetos-de-fontes-chaveadas/) written by Ivo Barbi, and the YouTube playlist [Fontes Chaveadas](https://www.youtube.com/watch?v=BYBMHBqT8EI&list=PLSjlUAuQORNNm-O2ilwZME7qL0d8M-_xs). The book was a great help in the rectifier project and Dc-Dc converter project, while the YouTube channel provided detailed explanations and information about the design of switched-mode power supplies and high-frequency inductors. If anyone wants to dive deeper into the theory, I recommend these two sources.

## Recomendend order to read the repository

1. **Theory**
   - Start with the theoretical section to understand the main concepts.

2. **Simulations**
   - Review the simulations, which provide a comparison between theoretical and simulated results.

3. **Component Selection**
   - After the simulations, analyze the component selection.

4. **Results**
   - Explore the obtained results to understand the actual performance.

5. **Hardware Folder**
   - The hardware folder contains the following files:
     - Schematics
     - PCB files
     - 3D image of the PCB
   - These files are especially useful for those interested in building their own power supply.


## Specifications

| **Specification**                   | **Description**             |
|------------------------------------|-----------------------------|
| **Minimum Input Voltage (V)**      | 110 V                       |
| **Maximum Input Voltage (V)**      | 233 V                       |
| **Minimum Peak Voltage (V)**       | 155.56 V                    |
| **Maximum Peak Voltage (V)**       | 329.51 V                    |
| **Grid Frequency (Hz)**            | 60 Hz                       |
| **Output Power (W)**               | 3 W                         |
| **Output Voltage (V)**             | 12 V                        |
| **Efficiency**                     | 80%                         |
| **Rectifier Ripple (%)**           | 5%                          |
| **Switching Frequency (Hz)**       | 66 kHz                      |
| **Inductor Ripple (%)**            | 0.25%                       |
| **Output Voltage Variation (V)**   | 0.01 V                      |
| **Safety Coefficient**             | 1.25                        |
| **Ambient Temperature (ºC)**       | 50 ºC                       |