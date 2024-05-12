# Digial_VLSI_SoC
<h2>Day1-Inception of open-source EDA, OpenLANE and Sky130 PDK</h2>
<h3>How to talk to computers?</h3>
<h3>Introduction to QFN-48 Package, chip, pads, core, die and IPs</h3>
<h4>Arduino Microcontroller Board</h4>
The Arduino microcontroller (MC) board is a popular open-source electronics platform based on easy-to-use hardware and software.It contains of input/output pins for connecting different sensors, actuators, and other parts, and a programmable microcontroller, usually an AVR or ARM-based chip. Arduino boards are popular because they provide an easy-to-use development environment, a big community for assistance and resources, and are useful for prototyping and interactive electronic creations.


![515b4656ce395f8a38000000](https://github.com/Chaithanya230/vsd_soc/assets/169294654/1187983f-1ab5-4411-92f3-9a96c944ee6b)


#### Different Chip Components 
1. **Pads:** Signals can be sent inside and outside the chips through pads.

2. **Core:** A place where all digial logic gates are placed.

3. **Die:** Present at the corner. it is the size of the entire chip.

 **Foundry IPs (Intellectual Properties):** Foundry IPs are pre-designed, pre-verified, and pre-characterized functional blocks provided by semiconductor foundries.

**Macros:** Macros are reusable blocks of custom-designed logic created by chip designers or third-party IP providers.


   ![Screenshot 2024-05-12 111511](https://github.com/Chaithanya230/vsd_soc/assets/169294654/fac1c72f-fd4b-42d4-917f-226f077345df)


<h3> Introduction to RISC-V</h3>

#### RISC-V Instruction Set Architecture (ISA)
RISC-V is an open-source instruction set architecture (ISA) based on reduced instruction set computing (RISC) principles. It offers flexibility, scalability, and customization for various applications, from embedded systems to high-performance computing.Basically it is a language of the computer and the way we talk to it.

<h3>From Software Applications to Hardware</h3>

The flow from Apps to Hardware is given as:

Software Applications -> System Software -> Hardware


![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/1956a952-2aae-4601-9517-abb876b11c93)


The basic operation here is that application software moves into system software where the C progarms are converted into binary language and then fed into the hardware.
#### Operating System, Complier, Assembler
1. **Operating system (OS):** Operating system handles input output operation memory allocation etc. The major operation is to take the application software and converted to its assembly level program and finally into binary language so that it is understood by the hardware

2. **Complier:** It takes output of the OS and converts the programs into its respective instruction set.

3. **Assembler:** It takes the output of the complier that is the instruction (.exe) file and converts it to binary language. This binary language is sent to hardware and hardware performs ouput based on the function it recieve and gives the output.


<h3>SoC design and OpenLANE</h3>
<h3>Introduction to all components of open-source digital asic design</h3>

#### Tools required to design Digital ASIC

1. **EDA TOOLS:** EDA (Electronic Design Automation) tools are software applications used by semiconductor and electronic designers to design, simulate, and verify electronic systems and integrated circuits (ICs). It help designers create complex digital and analog circuits, optimize performance, ensure reliability, and meet design constraints.

2. **PDK DATA:** Process Design Kit (PDK) is a collection of files, models, and documentation provided by semiconductor foundries to facilitate the design of integrated circuits using their manufacturing process technology. PDKs contain information about the semiconductor process, including design rules, device models, layout guidelines, and technology files. Designers use PDKs in conjunction with EDA tools to develop IC designs optimized for a specific manufacturing process.

3. **RTLIP's:** (Register Transfer Level Intellectual Properties are pre-designed, pre-verified, and pre-characterized digital hardware blocks or modules that are described at the register-transfer level (RTL). These IP blocks are used in the design of integrated circuits (ICs) and systems-on-chip (SoCs)

<h3>Simplified RTL to GDSII flow</h3>

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/95eecb72-8a7a-449a-83b1-f2180b88b193)

#### 

1. **RTL Design (Register Transfer Level):** Engineers create a high-level description of the digital circuit using a hardware description language (HDL) like Verilog or VHDL.
   
2. **Synthesis:** The RTL code is synthesized into a gate-level netlist. Logic gates, flip-flops, and other components are generated based on the RTL.
   
3. **FloorPlanning + Power Planning:** Chip floor planning (Partition of the chip die betwwen different system bulding blocks
    Macros floor planning (Dimensions, pin location and row definition) and power planning ( involves strategic distribution of power and gnd connections to all functional blocks).

4  **Placement:** Place cells (gates) onto the chip’s floorplan.It is done in two steps i) Global ii) Detailed

5. **Clock Tree Synthesis (CTS):** It creates a clock distribution network. Ensure clock signals reach all parts of the chip with minimal skew,delay and power consumption. Insert buffers and inverters for balanced clock paths.

6. **Routing:** Connect the placed cells using metal layers. Route wires to connect inputs and outputs. Optimize for timing, congestion, and manufacturability.

7. **Sign Off:** Verification and validation of the design. Timing analysis, power analysis, and design rule checks. Once everything meets specifications, the design is ready for manufacturing.






  











