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

4. **Placement:** Place cells (gates) onto the chip’s floorplan.It is done in two steps i) Global ii) Detailed

5. **Clock Tree Synthesis (CTS):** It creates a clock distribution network. Ensure clock signals reach all parts of the chip with minimal skew,delay and power consumption. Insert buffers and inverters for balanced clock paths.

6. **Routing:** Connect the placed cells using metal layers. Route wires to connect inputs and outputs. Optimize for timing, congestion, and manufacturability.

7. **Sign Off:** Verification and validation of the design. Timing analysis, power analysis, and design rule checks. Once everything meets specifications, the design is ready for manufacturing.

<h3>Introduction to OpenLANE and Strive chipsets</h3>

OPENLANE is an automated RTL to GDSII flow which comprises of many open source EDA tools such as OpenROAD, Yosys, Magic, Netgen, Fault, CVC SPEF-Extractor, CU-GR, Klayout,etc. The was started as an Open-source tape-out experiment using an Open-source flow. Open PDK, Open EDA, and Open RTL are among the Open Everything SoCs in the striVe family. The main goal of Openlane is to cut-off human intervations between RTL to GDSII with no DRC, LVS and timing violatons.

<h3>Introduction to OpenLANE detailed ASIC design flow</h3>

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/61d59da4-9455-4955-9faa-864a36c5bfe3)

Modes of operation 
#### 
1. **Autonomous:** Complete execution (Push Button flow)

2. **Interactive:** Step by step execution

   
<h3>Get familiar to open-source EDA tools</h3>
<h3>OpenLANE Directory structure in detail</h3>

#### Few Linux Commands

**cd:** change directory.

**ls:** Used for listing different contents in the directory.

**ls -ltr:** Used for lisiting files in chronological order.

**command --help:** It gives information about all the switches what does they mean.

**clear:** Used to clear the screen.

In this workshop we are working in Sky130_fd_sc_hd PDK varient where, *sky130* is process name, *fd* is a foundary name, *sc* means standerd cell librery, *hd* means high density( type of varient).

![day1 part1](https://github.com/Chaithanya230/vsd_soc/assets/169294654/db9abe79-e65d-4024-9223-be1a9a7ae605)

<h3>Design Preparation Step</h3>

The terminal window is opened and we are currently in Openlane directory after this we choose flow.tcl and be in interactive mode.
flow.tcl tells how the flow has to go using the script and -interactive ensures that it undergoes step by step process. Later install the required packages.
Design preparation step the clock period is set to 12.

![Screenshot 2024-05-15 092407](https://github.com/Chaithanya230/vsd_soc/assets/169294654/07e3ec95-bfe6-4a19-b3b3-aa0058163c09)


![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/dc195871-0a7a-4e28-b47b-e3510d53ebfa)

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/b7b53c03-c844-454f-abe4-b901019076c2)

Now before synthesis we need to perpare a design set up stage which is shown below

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/a19c28c7-7cc3-4bef-8fdd-8f4a45670d3d)

<h3>Steps to characterize synthesis results</h3>

The result of the sysnthesis is given my a objective to find the flop ratio

Flop ratio =(no. of D_ff)/(total no of cells)
So, flop ratio= 1613/14876 = 0.108 = 10.8%

![no of d ff](https://github.com/Chaithanya230/vsd_soc/assets/169294654/9f6c27be-c8f8-4102-9fe8-589e50b25299)

![no of cells](https://github.com/Chaithanya230/vsd_soc/assets/169294654/4214a09e-c024-4981-a924-53151ad5cf11)


<h2>Good floorplan vs bad floorplan and introduction to library cells</h2>
<h3>Chip Floor planning considerations</h3>
<h3>Utilization and Aspect ratio</h3>
Chip dimensions mostly depends on the dimensions of standard cells

#### Dimensioning is first started by defining the width and length of core and die 

**Core:** It is a section of the chip where fundamental logic is placed.

**Die:** It is a small semiconductor material o which fundamental circuit is fabricated.

Now consider the given netlist 

![Day 2 1](https://github.com/Chaithanya230/vsd_soc/assets/169294654/9711cdae-138e-4059-8d5e-e1991eb6e652)

Now for core dimensions consider only standard cell components and ignore wirings initially.

![DAy 2 2](https://github.com/Chaithanya230/vsd_soc/assets/169294654/d1b19493-3703-4e82-9ce9-11418c26ec6c)

Now calculate the dimensions of each standard cells

![Day 2 3](https://github.com/Chaithanya230/vsd_soc/assets/169294654/0bd00ed0-7fda-47d8-badf-8db384aa4f9f)

The Utilization factor is defined as the ratio of area occupied by the netlist to total area of the core.

![Day 2 4](https://github.com/Chaithanya230/vsd_soc/assets/169294654/8e01491a-67d5-4a2d-9697-8466d5270335)

The Aspect ratio is defined as ratio of height to length of the core. It also tells about the shape of the chip (square or rectangle).

![Day 2 5](https://github.com/Chaithanya230/vsd_soc/assets/169294654/25277d89-b351-4820-a028-8c9950b36189)

<h3>Concept of Pre-placed cells</h3>
Pre-placed cells are cells which are placed only once on the chip after which it cannot be moved in a design cycle. The arrangement of these IP's in a chip is referred to as floor planning and the IP's have user defined location. These typically include IP blocks, memory arrays, and other large functional blocks that have predefined physical dimensions and connectivity requirements. They are implemented once and used multiple times on the chip.

![Day 2 6](https://github.com/Chaithanya230/vsd_soc/assets/169294654/f97c9aa3-649c-43c0-85d0-a1db616bb076)

<h3>Surrounding Pre-placed cells by De-coupling capacitors</h3>
<h3>De-coupling capacitors</h3>

Consider a logical circuit. Every logic gate has a capacitance which has to charge and discharge as its logic changes from 0 to 1 or 1 to 0. These charges comes from a single power supply. Every gate has a small capacitance which needs some amount of voltage (noise margin - voltage needed to get stable).
Practically there will be voltage drop as it reaches the capacitors due to the large distance between power supply and the capacitors.

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/afcf26f6-f5c3-4364-9391-4368cce45f5b)

![day 2 7](https://github.com/Chaithanya230/vsd_soc/assets/169294654/2f817137-f222-485a-859d-8b943a501033)

To solve this problem we use De-coupling capacitors. These are basically huge capacitors completlely fillled with charges. 
Now the de-coupling capacitors are used near to the circuit such that voltage across the dcap and the Vdd is same.
Whenever switching activity is found the decap looses it's charge to the circuit, when no swithing activity is there then they replenish their charges.

![day 2 8](https://github.com/Chaithanya230/vsd_soc/assets/169294654/e1064bdd-c364-451f-b280-134d84f1c9e2)

So after placing the Decaps between the blocks the chip looks something like this

![day 2 9](https://github.com/Chaithanya230/vsd_soc/assets/169294654/3942cde5-52a3-4058-9676-6a9c29ecd329)

<h3>Floor Planning</h3>

Power planning is to ensure that every component on the chip receives stable and clean power without any voltage drop.
The layout uses a grid of power (Vdd) and ground (Vss) lines(horizontal and vertical) that intersect across the chip to provide every component with access to power. This setup minimizes voltage drops and power losses. IP blocks and logic circuits are strategically located within this grid to optimize power delivery and minimize latency in power access.

![image](https://github.com/Chaithanya230/vsd_soc/assets/169294654/4cf16db6-3ce8-49ef-82aa-b09f29f52855)

<h3> Pin placement and logical cell placement blockage</h3>

The connectivity information between the gates is coded using vhdl or verilog of and is called as netlist
Consider the below designs to be implemented 

![Screenshot 2024-05-13 201528](https://github.com/Chaithanya230/vsd_soc/assets/169294654/6ad15ab0-5000-4ebb-9c31-bc3526db558c)

![Screenshot 2024-05-13 201637](https://github.com/Chaithanya230/vsd_soc/assets/169294654/07481bee-eee1-4932-bb2e-df1b4020ff79)

Complete design is given below

![Screenshot 2024-05-13 201741](https://github.com/Chaithanya230/vsd_soc/assets/169294654/59988a37-d238-42c9-bc96-c98b5dfeb24b)

The area between Core and the die is filled with pin information generally input ports are put on the left and output ports put on the right this need not be true in all the case. Now after placing the input and output ports that is after the pin placement is done we need to make sure that the automated PnR doesn't place any cells in the area between the core and die so the space between the space between Core and die should be blocked which is called logical self placement blockage.

![Screenshot 2024-05-13 202354](https://github.com/Chaithanya230/vsd_soc/assets/169294654/991a0629-f7f3-4120-a33d-b839e4265c53)

<h3>Steps to run floorplan using OpenLANE</h3>

Before runing the floorplanning, we required some switches for the floorplanning which we can get from the configuration from openlane. We can see some important things like utilization factor, aspect ratio,etc which can bw changed according to the requirements. 

![Screenshot 2024-05-13 212526](https://github.com/Chaithanya230/vsd_soc/assets/169294654/ed61d1de-eb41-4ded-b642-b5415523034d)

Now run the floorplan using `run_floorplan`

![Screenshot 2024-05-13 212719](https://github.com/Chaithanya230/vsd_soc/assets/169294654/7f518a54-01ee-4685-bf89-4f6fe1acfc39)

<h3>Review floorplan files and steps to view floorplan</h3>

Here in this step it shows the user how to floorplan actually looks.
For that we need to type the command shown in the terminal box shown below

![Screenshot 2024-05-15 100558](https://github.com/Chaithanya230/vsd_soc/assets/169294654/466a87bd-24ce-4f87-8528-2819947f101c)
After this press enter the floorplan will open in Magic file.

![Screenshot 2024-05-15 100616](https://github.com/Chaithanya230/vsd_soc/assets/169294654/f1bed0b5-93c0-4a46-973c-4a1220c04204)

<h3>Review floorplan layout in Magic</h3>

The image below shows the actual flooplan

![Screenshot 2024-05-15 100939](https://github.com/Chaithanya230/vsd_soc/assets/169294654/af6cc3fa-f0af-43c0-9a63-36196caae267)

The left most pins indicate the input pins and we can see that input output pins are placed equidistant. The Decap cells are arranged at the border of the side rows.

![Screenshot 2024-05-15 101209](https://github.com/Chaithanya230/vsd_soc/assets/169294654/6ae35a79-4cc5-436e-8c21-154510655a06)

The pre-placed cells can be seen at the bottom left corner.

![Screenshot 2024-05-15 101749](https://github.com/Chaithanya230/vsd_soc/assets/169294654/42371826-b3fa-4032-9b8b-21c3c8c488ca)


















































  











