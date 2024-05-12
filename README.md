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

4. **Foundry IPs (Intellectual Properties):** Foundry IPs are pre-designed, pre-verified, and pre-characterized functional blocks provided by semiconductor foundries.

5. **Macros:** Macros are reusable blocks of custom-designed logic created by chip designers or third-party IP providers.


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


  











