# DIGTIAL VLSI SoC DESGIN AND PLANNING

Digital VLSI SoC Design and Planning refers to the process of designing and preparing a System-on-Chip (SoC) using Very Large Scale Integration (VLSI) techniques, specifically focused on digital logic circuits.

>- This is a 2 week course of Digital VLSI SoC Design and Planning with complete RTL2GDSII flow organised by VSD in collaboration with NASSCOM

## TABLE OF CONTENTS
DAY - 1
  1. INCEPTION OF OPEN-SOURCE EDA ,OPENLANE AND SKY130 PDK
       * [HOW TO TALK TO COMPUTERS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/blob/main/README.md#how-to-talk-to-computers)
       * [SoC DESIGN AND OPEN LANE](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md#soc-design-and-open-lane)
       * [GET FAMILIAR TO OPEN SOURCE EDA TOOLS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md#-get-familiar-to-open-source-eda-tools-)

DAY - 2
  
  2. GOOD FLOORPLAN VS BAD FLOORPLAN AND INTRODUCTION TO LIBRARY CELLS
       * [CHIP FLOOR PLANNING CONSIDERATIONS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/blob/main/README.md#-chip-floor-planning-considera)
       * [LIBRARY BINDING AND PLACEMENT](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
       * [CELL DESIGN AND CHARACTERIZATION FLOWS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
       * [GENERAL TIMING CHARACTERIZATION PARAMETERS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)

DAY - 3

  3. DESIGN LIBRARY CELL USING MAGIC LAYOUT AND NGSPICE CHARACTERIZATION
       * [LABS FOR CMOS INVERTER NGSPICE SIMULATIONS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
       * [INCEPTION OF LAYOUT A^ CMOS FABRICATION PROCESS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
       * [SKY130 TECH FILE LABS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)

DAY - 4

  4. PRE-LAYOUT TIMING ANALYSIS AND IMPORTANCE OF GOOD CLOCK TREE
      * [TIMING MODELLING USING DELAY TABLES](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
      * [TIMING ANALYSIS WITH IDEAL CLOCKS USING OPENSTA](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
      * [CLOCK TREE SYNTHESIS TRITON CTS AND SIGNAL INTERGRITY](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)

DAY - 5

  5. FINAL STEPS FOR RTL2GDS USING TRITONROUTE AND OPENSTA
     * [ROUTING AND DESIGN RULE CHECK(DRC)](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
     * [POWER DISTRIBUTION NETWORK AND ROUTING](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
     * [TRITION ROUTE FEATURES](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)

# DAY - 1

## INCEPTION OF OPEN-SOURCE EDA ,OPENLANE AND SKY130 PDK
### <ins> HOW TO TALK TO COMPUTERS <ins/>

ARDUINO : Arduino is an open-source electronics platform based on easy-to-use hardware and software. It's designed to make digital electronics more accessible to hobbyists, students, engineers, and artists. Arduino boards are equipped with a microcontroller, which is a small computer that can read inputs (like sensors, buttons, or data from the internet) and turn them into outputs (like activating motors, lights, or displays).


![Screenshot (120)](https://github.com/user-attachments/assets/9d6f5b58-99e8-4cb6-adf6-04a5357b68b8)

The board shown in the image is the Arduino Leonardo, a microcontroller development board based on the ATmega32u4 chip, which is highlighted in the yellow circle. What sets the Leonardo apart from other Arduino boards is its built-in USB communication capability, thanks to the ATmega32u4’s native USB support. This allows the board to emulate USB devices like a keyboard, mouse, or joystick without requiring an additional USB-to-serial converter. It features 20 digital I/O pins (7 of which can be used for PWM), 12 analog inputs, and operates at 5V with a 16 MHz clock speed. 

**chip components**

chip consists of three main parts
1) Die
2) Pads
3) Core

![Screenshot (128)](https://github.com/user-attachments/assets/cd06aae4-2652-4013-8828-e815a0505fca)

**Pads** --> Pads are the physical contact points on the die used to connect the internal circuitry to the outside world

**Core** --> The core is the central part of the die that contains the actual digital/analog logic circuitry — the functional heart of the chip.

**Die** --> The die is the entire silicon piece cut from the wafer that contains the integrated circuit (IC).

**The example**: RISC-V SoC 

![Screenshot (119)](https://github.com/user-attachments/assets/2609c087-5f06-47e8-bdb1-11f58a0a1241)

### <ins>Intro to RISC-V</ins>

RISC-V is an open-source, modular instruction set architecture (ISA) based on the principles of Reduced Instruction Set Computing (RISC). Unlike proprietary ISAs such as ARM or x86, RISC-V is freely available for anyone to use, design, and modify, making it ideal for academic research, startups, and custom hardware development. It offers a simple and clean base ISA (like RV32I or RV64I) that can be extended with optional modules such as multiplication/division (M), atomic operations (A), and floating-point (F). Due to its flexibility and scalability, RISC-V is used in a wide range of applications—from low-power microcontrollers to full-featured Linux-capable processors and even AI accelerators. Its open nature encourages innovation and collaboration across the semiconductor industry.

![Screenshot (122)](https://github.com/user-attachments/assets/2a5b09ab-8509-4f47-a092-eb3ae1320b18)

**MACROS**--> Macros are pre-designed, reusable blocks or components that are placed inside a chip to perform specific functions.

**FOUNDRY IP'S**-->Foundry IPs are ready-made blocks provided by the chip manufacturing company (called a foundry, like TSMC or GlobalFoundries). 
These blocks are used to make sure your chip can connect safely to the outside world and work properly when built.

![Screenshot (131)](https://github.com/user-attachments/assets/f97d7fa1-e937-4f26-bbd1-2bbf84b481bf)

### FROM SOFTWARE APPLICATION TO HARDWARE

![Screenshot (137)](https://github.com/user-attachments/assets/fa8fc487-f8b0-4cff-b8f0-e9181a1f81e8)

The above picture contains the representation of the flow , from the software application to the system software and goes to the hardware 

From the software app to the system software that is of containing an OS (Operating system --> n Operating System (OS) is system software that acts as an interface between computer hardware and the user. It manages both hardware resources and software services). It has a compiler and assembler(A compiler translates high-level code into assembly or machine code, while an assembler converts assembly code into machine code.)

Last the code goes to the hardware section for process and gives the response.


### <ins>SoC DESIGN AND OPEN LANE<ins/>

![Screenshot (160)](https://github.com/user-attachments/assets/5bbec3b4-45b5-4f67-a7bf-c71e56b16ca7)

ASIC stands for Application-Specific Integrated Circuit. It is a custom-designed chip created for a specific task or application, unlike general-purpose chips like CPUs or GPUs.

The ASIC containing three parts 
> EDA TOOLS

> RTL Designs

> PDK Data

### <ins> SIMPLIFIED RTL TO GDSII FLOW <ins/>

![Screenshot (162)](https://github.com/user-attachments/assets/d0aacb89-0642-43d6-96d9-146120fc920a)

1) Synthesis: Converts RTL to gate-level netlist using standard cell libraries with timing and area optimization.

2) Floorplanning: Defines chip layout including macro placement, I/O pins, and power grid.

3) Placement: Legally places standard cells to optimize timing, area, and congestion.

4) Clock Tree Synthesis (CTS): Builds balanced clock trees to minimize skew and meet timing.

5) Routing: Connects all cells with metal layers while meeting DRC, timing, and signal integrity.

<ins> **OPENLANE ASIC FLOW** <ins/>
 
 ![Screenshot (174)](https://github.com/user-attachments/assets/741def72-51f3-49f1-adb7-a428dd62091c)

1) Preparation: Set up design configuration and technology files (sky130 or other PDKs).

2) Synthesis: Convert RTL to gate-level netlist using Yosys.

3) Floorplanning: Define chip size, aspect ratio, I/O pins, and core/utilization using Floorplan.tcl.

4) Placement: Place standard cells using RePlAce for global and OpenDP for detailed placement.

5) CTS (Clock Tree Synthesis): Generate and balance clock tree using TritonCTS.

6) Routing: Route signal and clock nets using FastRoute (global) and TritonRoute (detailed).

7) GDSII Generation: Export final layout to GDSII using Magic.

8) DRC/LVS Checks: Run design rule (DRC) and layout-vs-schematic (LVS) checks with Magic and Netgen.

9) Power Analysis: Use OpenSTA to check timing and optionally estimate power.

### <ins> GET FAMILIAR TO OPEN SOURCE EDA TOOLS <ins/>

* **Basic Linux commands**
  
> cd : Change directory

> ls -ltr : List files with detailed info, sorted by modification time, from oldest to newest.

> clear :Clears the terminal screen.

> pwd : Print Working Directory

> ls : List directory contents


** Design Preparation Step **

In the oracle vritual box , there is a zip file given from the workshop that contains the open source tools and for using of the tools we use the terminal window in there.

![VirtualBox_vsdworkshop_18_05_2025_17_42_31](https://github.com/user-attachments/assets/dbf4b48a-f76d-49a8-be28-5520c03b14dd)

Here the linux basic commands are used like cd for the changing the directory and ls -ltr etc are used and explored more of the commands 

![2](https://github.com/user-attachments/assets/b2ba2fda-2f9b-49e9-90b8-73f5ff780d45)

![3](https://github.com/user-attachments/assets/083142ac-51fa-4c42-9f4b-48f72771055e)

![4](https://github.com/user-attachments/assets/0b529153-d042-42f2-a44f-58cf7058b336)

this are the commands which are present in the alphabetical order .

* then the directory is changed to openlane_working_dir and exploring the inside files and there the directory goes to the pdks and continue the exploring of the files present and listing them.

![6](https://github.com/user-attachments/assets/d7555bee-ab05-4cdf-93b1-f3f2e93eae63)

![7](https://github.com/user-attachments/assets/ac141cde-ea29-4a0f-a79c-e3b82e1ba0b4)

![8](https://github.com/user-attachments/assets/89559490-5a07-472e-b5e9-e5106dc97afe)

![9](https://github.com/user-attachments/assets/a9539a18-561d-4224-bbdf-3602a2462141)

![10](https://github.com/user-attachments/assets/79ed6ec4-a4f6-4ce2-ad2a-2ac7a904b331)

![11](https://github.com/user-attachments/assets/c430afe2-132b-4e6f-b778-29678e1d84bb)

* we are working in the openlane directory that has the skywater files.


  
 ![1](https://github.com/user-attachments/assets/64ab3a7b-1473-4617-a6a7-a21554eb0cd5)

here we used the docker then flow.tcl interactive after the we use the package require command to access the openlane 

 ![2 (1)](https://github.com/user-attachments/assets/e7c549ad-6277-49ea-b3f1-211fed30ae8b)

![2 (2)](https://github.com/user-attachments/assets/f8e5561a-a4f9-4c96-8a0b-9f9a7349a3df)

![2(3)](https://github.com/user-attachments/assets/bbfdf443-f75c-441d-b26d-ad2ab59d9847)

![2(4)](https://github.com/user-attachments/assets/d3baa3dc-b8e3-40a1-90d9-cd767ba9aa06)

We are doing the picorv32 so for that , we changed the directory to picorv32a and explored the conf.tcl 

![3](https://github.com/user-attachments/assets/7b6c43d4-f47f-4f21-a2cb-277e7f3c8ba6)


![4](https://github.com/user-attachments/assets/7d725ee0-0915-4c59-a6f9-6cc212e588bc)

![5](https://github.com/user-attachments/assets/1a1401bb-9b01-45c2-93ef-a6330cdfb8c9)

![6](https://github.com/user-attachments/assets/e0734ee0-6db0-4258-b89f-3dd303ba026b)

![7](https://github.com/user-attachments/assets/65a7df34-a0e2-42cd-ba0a-fc7d9301a695)

then goes to the sky130A directory and explored the sky130 conf tcl file

then we used prep -design command for the picorv32a and finished the design preparation and explored few more files

![4](https://github.com/user-attachments/assets/0250e564-0446-4af9-beea-b38228053a0b)

![6](https://github.com/user-attachments/assets/1894b315-39dd-4011-8004-cec8d1266798)

![6 -1](https://github.com/user-attachments/assets/0a85f2db-ccdc-440c-8523-3c220d96c393)

![7](https://github.com/user-attachments/assets/069d6473-fa2b-42e0-a2ac-487945bba1f8)

![7-1](https://github.com/user-attachments/assets/645e2199-8a8c-4b04-ad7b-f67968204ea8)

here in the prep design we did the synthesis of the picorv32a by using the run command

![8](https://github.com/user-attachments/assets/722374a8-1fea-482f-a265-b7655146cd1d)

![8 final](https://github.com/user-attachments/assets/6954eb3d-7d4a-4d0f-a97b-ba602445190d)

![1](https://github.com/user-attachments/assets/634b91b1-5df2-44d6-971d-a9e0746c7697)

![2](https://github.com/user-attachments/assets/b1f331b2-041c-4510-b297-540cd5da1508)

![2-1](https://github.com/user-attachments/assets/793ca795-7e39-4f7c-9a7f-3608078c98f5)

![3](https://github.com/user-attachments/assets/11117acb-2880-4f34-b26d-53f6eb1aa335)

![4](https://github.com/user-attachments/assets/7961dfec-d3a4-498b-8291-75e0af176809)

![4-1](https://github.com/user-attachments/assets/7c245376-74a2-4840-a44d-2a1a6ea41b65)

![5](https://github.com/user-attachments/assets/7846773f-3481-4f76-84ed-69e1311f77f7)

![5-1](https://github.com/user-attachments/assets/de21dcdf-40e9-42b0-8f38-6cc61a9b9e1b)

![6](https://github.com/user-attachments/assets/3930d8f2-3255-46ee-9f4b-ff0e835a9b4f)

![6-1](https://github.com/user-attachments/assets/4a8e42e4-6493-4ad3-8c90-45810018974d)

# DAY - 2 

## GOOD FLOORPLAN VS BAD FLOORPLAN AND INTRODUCTION TO LIBRARY CELLS

### <ins> CHIP FLOOR PLANNING CONSIDERATIONS <ins/>

In section , we have explored the floorplanning

1) Define width and height of core and die --> Determine die size based on total cell area and routing/pad overhead, then define a slightly smaller core area inside it.
2) Define locations of preplaced cells --> Place fixed macros (e.g., memory, analog IP) early to guide placement and minimize congestion.
3) surround pre-placed cells with decoupling capacitors --> Add decaps around macros to reduce local IR drop and stabilize power.
4) power planning --> Create power grid and stripes to distribute VDD/VSS efficiently across the chip with minimal voltage drop.
5) pin placement -->  Position I/O pins along die boundaries based on logical groups and shortest routing paths.

![Screenshot (190)](https://github.com/user-attachments/assets/974e8d82-3615-4a54-8e6a-a4952fc1053d)

![Screenshot (200)](https://github.com/user-attachments/assets/ff2d3242-d6b3-4038-9609-6894af3814dd)

![Screenshot (201)](https://github.com/user-attachments/assets/399561da-924e-40d8-bad4-ca1da971c5c2)

![Screenshot (203)](https://github.com/user-attachments/assets/f1be7e7a-9c59-46b8-867a-9f6162566e8c)

![Screenshot (205)](https://github.com/user-attachments/assets/d0abbb20-67a8-4e3b-aa3b-37d49eebc0c7)

![Screenshot (206)](https://github.com/user-attachments/assets/76851653-a66b-466a-bbf2-9d0a1b58c04e)

![Screenshot (209)](https://github.com/user-attachments/assets/e82bed10-3b5a-4a9d-a40d-b9a7bccbcadf)

![Screenshot (213)](https://github.com/user-attachments/assets/fdd51b32-1171-4b66-8e3a-92986950ae97)

![Screenshot (215)](https://github.com/user-attachments/assets/19fdd337-b8c3-4d63-b0eb-37e9161c59e7)

![Screenshot (216)](https://github.com/user-attachments/assets/52c176d1-758d-4592-9a2f-be99dfa63a9d)

![Screenshot (222)](https://github.com/user-attachments/assets/7b45a59b-1ba8-4885-8778-e951c713fb8f)

![Screenshot (229)](https://github.com/user-attachments/assets/8917a5c8-0046-4cb6-99ea-22cbd0f735a1)

![Screenshot (231)](https://github.com/user-attachments/assets/1fcc5a56-633e-454f-a75e-a84ecfd9bc0d)

![Screenshot (233)](https://github.com/user-attachments/assets/784eb414-045d-4e25-862c-8ef1f3fc6c1c)

![Screenshot (238)](https://github.com/user-attachments/assets/a58f5b0f-dc46-4860-ac7c-fe6c3762f180)

![Screenshot (246)](https://github.com/user-attachments/assets/e056a4bb-abe1-49b7-b0bf-9de3255a80c0) 

![Screenshot (247)](https://github.com/user-attachments/assets/925f422d-e429-4a48-8fca-7d173d9c087e)

![Screenshot (250)](https://github.com/user-attachments/assets/37992c9a-e14b-4f07-afa7-77207be40fc0)


### steps for run the floor planning

![1](https://github.com/user-attachments/assets/024a079b-b820-424e-bc3c-59dc62d3644f)

![1-2](https://github.com/user-attachments/assets/29eee72f-f6d3-4409-86e8-b18c43bbe52b)

![2](https://github.com/user-attachments/assets/08e42853-a4bc-46c2-ba79-104ec17c2bc7)

![2-1](https://github.com/user-attachments/assets/8ef1b6ce-a13e-4eab-854f-35e5b70576a2)

![3](https://github.com/user-attachments/assets/bb773278-6622-4c63-b557-2a9fa14c742f)

![3-1](https://github.com/user-attachments/assets/a0b4143f-d893-4313-9835-9ee22cd1c4b3)

* after the synthesis then we go for the floor planning , there we go the confirugation directory there we explored the readme file and contains present then checked the conf.tcl file soon we go for run_floorplan for running the floorplan for our design picorv32a.


![1](https://github.com/user-attachments/assets/2a9e33f7-dda8-4dac-a17c-2b8f09281b65)

![2](https://github.com/user-attachments/assets/c36c70c5-2bf0-4000-81b6-cf4c15096bd1)

![2-1](https://github.com/user-attachments/assets/66917782-32a3-4ea5-8d43-6935c8e0875f)

![3](https://github.com/user-attachments/assets/ad71ced6-7b53-426f-8a7d-11d02e4a2782)

![3-1](https://github.com/user-attachments/assets/22a1aca8-591d-44dc-aa18-f5f20a4a84e9)

![4](https://github.com/user-attachments/assets/cd190255-01a7-403f-8841-c9a60d0de683)

![4-1](https://github.com/user-attachments/assets/75725421-6dbd-4a92-be15-de334c680a7e)

![5](https://github.com/user-attachments/assets/7ff3b432-5785-4a4f-9226-5a4687354772)

![5-1](https://github.com/user-attachments/assets/9867fa6b-4e15-4c30-b381-08dde5a37a31)

![6-1](https://github.com/user-attachments/assets/730d8544-cf36-44fe-b2bd-96f4521132f7)
 
![6](https://github.com/user-attachments/assets/2c002713-763c-4ca8-b45c-3e1e603f7894)

![5-2](https://github.com/user-attachments/assets/86c4c530-a682-48e2-838a-d608fd835033)

checked the floorplanning results and used magic , a opensource layout tool and used to see the layout.

* merged.lef: This version includes cell padding, controlled by the CELL_PAD parameter. Padding is added to ensure proper spacing between cells during placement and routing
* merged_unpadded.lef: This version excludes cell padding and is used in stages where unpadded cell dimensions are required .

**LIBRARY BINDING AND PLACEMENT**

1) bind netlist with physical cells
2) placement
3) optimize placement

![Screenshot (400)](https://github.com/user-attachments/assets/e1d64abf-efb3-4659-80f9-ee3f764e04da)

![Screenshot (402)](https://github.com/user-attachments/assets/4680d404-6572-4c99-94ad-5f742d7016af)

![Screenshot (408)](https://github.com/user-attachments/assets/92a7b3b2-78ba-4409-97f4-809a8573d501)

![Screenshot (414)](https://github.com/user-attachments/assets/1f08329f-91fa-48e6-b082-8aa7714d431e)

the flow goes from synthesis to routing , this are the steps to create the chip

1) synthesis
2) floor planning
3) placement
4) cts
5) routing

![Screenshot (419)](https://github.com/user-attachments/assets/9e856001-b145-4b92-93ee-feb84a696100)




### <ins> LIBRARY BINDING AND PLACEMENT <ins/>

Standard cells are pre-designed and pre-characterized logic gates and functional units (like AND, OR, NAND, flip-flops, muxes).

![Screenshot (423)](https://github.com/user-attachments/assets/145955ac-6935-4969-a661-98ada60012ab)

for connecting from one cell to the another cell, sometimes according to the distance we use buffer block in middle to connect.

![Screenshot (427)](https://github.com/user-attachments/assets/f223b23f-9910-4b17-ae9d-623293fe4fac)

![Screenshot (428)](https://github.com/user-attachments/assets/a0a179b3-fb14-4b43-a782-f0aadbb3c51d)

![Screenshot (430)](https://github.com/user-attachments/assets/fac065fc-9962-47e2-bec1-66e343e4e32a)

![Screenshot (437)](https://github.com/user-attachments/assets/486adb65-90e1-4d22-ae91-420e96adeb35)

![Screenshot (440)](https://github.com/user-attachments/assets/4a494733-ff62-46c6-be69-aaa2d3687caf)

![Screenshot (442)](https://github.com/user-attachments/assets/063aa989-85ea-4399-a2ab-05a653bb96b4)

![Screenshot (443)](https://github.com/user-attachments/assets/1678ecfa-8fce-40ad-af40-50fd492d9d1e)

![Screenshot (450)](https://github.com/user-attachments/assets/c5d14cfc-e555-4827-9356-f0cdef3f5fc6)


The above pics contains the cell design flow from inputs to the outputs 

GUNA --> GUNA is an open-source standard cell library from IIT Madras designed to support VLSI education, research, and open-source digital IC design

### <ins> GENERAL TIMING CHARACTERIZATION PARAMETERS <ins/>

![Screenshot (452)](https://github.com/user-attachments/assets/122f7918-f18c-4175-9db7-4a29035b7555)

 In the above pic the timing characterization contains of high , low of rise and fall of time

![Screenshot (454)](https://github.com/user-attachments/assets/84f7a2a5-26b8-4cf0-af56-4ea1ce5db60b)

 - low rise threshold

   
![Screenshot (455)](https://github.com/user-attachments/assets/5670cfec-773f-41df-adce-819060fdc46f)

- high rise threshold


![Screenshot (456)](https://github.com/user-attachments/assets/e7174b3b-8ddf-4850-bcb6-c6ed83f6be57)

- low fall threshold

![Screenshot (457)](https://github.com/user-attachments/assets/944334e3-83e1-4cea-bc69-8f48dbdbebd2)

-in rise threshold

![Screenshot (459)](https://github.com/user-attachments/assets/81d6477b-9816-4db0-92a3-158af21a41f8)

-out rise threshold

![Screenshot (460)](https://github.com/user-attachments/assets/6918b28e-531b-4bd1-bffa-20842ed3402d)

-in fall threshold

![Screenshot (461)](https://github.com/user-attachments/assets/83221a11-dbe2-4499-b8bf-7aec6dd562ab)

![Screenshot (467)](https://github.com/user-attachments/assets/713b7589-d309-45f2-b9f4-cbd2aeb420a1)

 propagation delay is the above pic

![Screenshot (471)](https://github.com/user-attachments/assets/94ad75da-5857-439c-98a1-42454e8e8f34)

 Propagation Delay -- Time taken for a signal to propagate from the input to the output of a gate, measured from the 50% voltage point of the input to the 50% voltage point of the output.

 Transition Delay -- Time taken for the output signal to transition from 10% to 90% (rise) or 90% to 10% (fall) of its final value.

 # DAY-3

 ## DESIGN LIBRARY CELL USING MAGIC LAYOUT AND NGSPICE CHARACTERIZATION

 ### <ins> LABS FOR CMOS INVERTER NGSPICE SIMULATIONS <ins/>

![Screenshot (373)](https://github.com/user-attachments/assets/660f89ee-b63f-4726-90b6-ee98b05eb0f2)

spice deck --> A SPICE deck is a text-based file used to simulate electronic circuits using SPICE (Simulation Program with Integrated Circuit Emphasis). It describes the circuit's components, their connections (netlist), simulation commands, and models.

1) component connectivity
2) component values
3) identify nodes
4) name nodes

![Screenshot (376)](https://github.com/user-attachments/assets/df49007f-9e6d-4e7c-a5a9-2ebfe3b7a8f3)

![Screenshot (384)](https://github.com/user-attachments/assets/a1e1d377-1eae-4a36-8da4-9e1202a09b4e)


** Lab steps to git clone vsdstdcelldesign **

we have git clone the file and used the tool magic to see the layout

![1](https://github.com/user-attachments/assets/1db45cfa-f1e6-4396-bb78-92bf7da5ce38)

![3](https://github.com/user-attachments/assets/1c35e4eb-26ff-44cd-863f-0a292b14e572)

![4](https://github.com/user-attachments/assets/ffa3f0ae-8642-49cd-b140-9b9af9b264be)

![4-1](https://github.com/user-attachments/assets/c9e5385a-2000-4dff-8b43-1c29948d491e)

![5](https://github.com/user-attachments/assets/dfdc6b73-6f92-42a0-b8cb-50060558ce23)

![5-1](https://github.com/user-attachments/assets/db155fa7-b276-4708-8bb0-cc776d96c824)

![5-2](https://github.com/user-attachments/assets/2a30ced5-b401-4c7b-9675-72c59cfaffd1)


### <ins> INCEPTION OF LAYOUT A^ CMOS FABRICATION PROCESS <ins/>

Here we learned about 16 steps of mask CMOS

first starting with the selecting the substrate

![Screenshot (257)](https://github.com/user-attachments/assets/f90b0914-d378-4bb0-8f10-44b7f94b9ac5)

then creating active regions 

![Screenshot (258)](https://github.com/user-attachments/assets/e3ea668a-0d03-4688-842b-a22ba816212d)

step-3 adding the mask 1 to create the active region

![Screenshot (261)](https://github.com/user-attachments/assets/cf944c9e-e226-4e3f-aa34-e6b410b3e377)

![Screenshot (262)](https://github.com/user-attachments/assets/88e58f5d-fdb1-4a8d-ac98-dd9f49a86ddc)

![Screenshot (263)](https://github.com/user-attachments/assets/4ed82466-4c45-40bf-8580-12f1d028ab54)

![Screenshot (265)](https://github.com/user-attachments/assets/aba5b456-e7aa-4131-83ef-374ec680ae5a)

![Screenshot (266)](https://github.com/user-attachments/assets/f1ef22b7-3095-4deb-94bc-1da6f6d27be7)

![Screenshot (267)](https://github.com/user-attachments/assets/485cd783-5037-405d-a248-a471dea37641)

step-4 N WELL  and P WELL formation

![Screenshot (274)](https://github.com/user-attachments/assets/dfeee17a-69a4-4cdb-af38-2b555deb961f)

![Screenshot (269)](https://github.com/user-attachments/assets/96d24f83-6990-40c2-866d-d8fa03716516)

![Screenshot (272)](https://github.com/user-attachments/assets/8f7ea3de-2a52-4aec-8a69-4280fa6cff69)

![Screenshot (274)](https://github.com/user-attachments/assets/cbd1b5eb-ddb3-48f5-bd2c-bba77fb13a03)

![Screenshot (276)](https://github.com/user-attachments/assets/37cb98e1-cc81-4323-8682-1bdf2c734247)

![Screenshot (277)](https://github.com/user-attachments/assets/36e370b8-7a49-40e6-8863-527e85d97b44)

![Screenshot (278)](https://github.com/user-attachments/assets/1915b4c7-3b47-4a2c-b341-1a9d585a2729)

used boron and phosphorus for ion implantation  to create the n well and p well and is kept in high temp furnace

![Screenshot (280)](https://github.com/user-attachments/assets/7735bfbf-4232-464b-8556-b2676c3563c1)


step-5 formation of gate

![Screenshot (282)](https://github.com/user-attachments/assets/e8c53dbf-136b-4bf9-b834-7eaa92870726)

![Screenshot (286)](https://github.com/user-attachments/assets/2bd1d48a-33b0-4aef-a3e9-4b9c76bddb31)

![Screenshot (287)](https://github.com/user-attachments/assets/b7deb3ec-9a53-401b-807b-1e4431263276)

![Screenshot (290)](https://github.com/user-attachments/assets/c2a29571-3329-4941-9072-1997c438a3ad)

![Screenshot (291)](https://github.com/user-attachments/assets/dd17ee2d-68a6-4309-ac9d-a65a9bf24b6a)

![Screenshot (292)](https://github.com/user-attachments/assets/0a44e812-d36a-4584-a9b3-9a1f647d5c0f)

![Screenshot (293)](https://github.com/user-attachments/assets/4b9010e5-a821-4c83-a163-607b821e073e)

![Screenshot (294)](https://github.com/user-attachments/assets/072be424-95c6-4baa-bc16-b68e87d2ace1)

![Screenshot (295)](https://github.com/user-attachments/assets/effa1d5a-7744-48f5-b7e6-1fa35d5a9888)

![Screenshot (297)](https://github.com/user-attachments/assets/aa3602d1-3d4e-4d08-9023-09dc56bdead8)

used a  layer of polysilicon and etched it and added the mask 6 
 
step -6 lightly doped drain formation

![Screenshot (300)](https://github.com/user-attachments/assets/b11a199f-a3df-4002-9f10-17a3c674d2b6)

![Screenshot (306)](https://github.com/user-attachments/assets/0d5c39d4-f1c4-4dfe-a417-b786f1c034fa)

![Screenshot (309)](https://github.com/user-attachments/assets/75707d46-3297-44af-8516-fce668c36172)

![Screenshot (310)](https://github.com/user-attachments/assets/7ff27f04-49a2-41d3-baf2-ac478ed570ec)

![Screenshot (311)](https://github.com/user-attachments/assets/653d1903-777e-4922-a2a5-9bb364d938f8)

![Screenshot (312)](https://github.com/user-attachments/assets/03460ace-96f9-4590-a93f-1bbcf4c9b1ee)

![Screenshot (313)](https://github.com/user-attachments/assets/d88c8098-2506-4937-9176-72a3b9e290e1)

![Screenshot (314)](https://github.com/user-attachments/assets/a5a7d562-126c-47ec-bf41-d6d3b1d14939)

we used the boron and phosphorus for the ion implant in the wells 

step - 7 source and drain formation

![Screenshot (316)](https://github.com/user-attachments/assets/fba08289-b903-4ef2-8535-f1d0768741c6)

![Screenshot (317)](https://github.com/user-attachments/assets/5f9bdc87-189b-4150-a4f6-6668dcb3c974)

![Screenshot (318)](https://github.com/user-attachments/assets/f71e217d-eb36-49c1-8149-6a876016492f)

![Screenshot (320)](https://github.com/user-attachments/assets/4b900919-29a1-4c2b-b361-8460f148dc90)

![Screenshot (321)](https://github.com/user-attachments/assets/85ac565b-d190-4234-93c6-cd248b8be114)

![Screenshot (323)](https://github.com/user-attachments/assets/621ba674-2576-454b-b01a-d251567404b1)

step -8 formation of contacts

![Screenshot (327)](https://github.com/user-attachments/assets/0bb6eb45-6e31-4c2c-9829-dcea695170db)

![Screenshot (329)](https://github.com/user-attachments/assets/d4ec801c-ec8c-4e1c-8dba-ce60f6db9e59)

![Screenshot (330)](https://github.com/user-attachments/assets/60ceacdc-f07d-4f28-91b3-1aa2d571dd20)

![Screenshot (331)](https://github.com/user-attachments/assets/24121a35-41cc-4756-887a-cce3b7087188)

![Screenshot (333)](https://github.com/user-attachments/assets/2db57311-6c47-4344-81ad-bc36f6086b5b)

![Screenshot (338)](https://github.com/user-attachments/assets/25ff053c-d2d2-4c9c-9508-35f73eca73d6)

![Screenshot (339)](https://github.com/user-attachments/assets/68bf76e7-43fe-4f12-9d73-bb40bae9ee35)

step - 9 higher level formation

![Screenshot (343)](https://github.com/user-attachments/assets/8879b025-7327-4471-b66d-bf269797ad7a)

![Screenshot (344)](https://github.com/user-attachments/assets/e3a8bd07-b9c0-480a-a4d1-30c87562691a)

![Screenshot (345)](https://github.com/user-attachments/assets/8e286eb8-13de-4c3d-9a87-910c22d59289)

![Screenshot (347)](https://github.com/user-attachments/assets/0cf042c3-2cd6-474d-8a3e-8016a3421a55)

![Screenshot (348)](https://github.com/user-attachments/assets/447d4464-80d1-4648-84af-9a2a46ba8d20)

![Screenshot (349)](https://github.com/user-attachments/assets/9cb663a8-9583-4bcc-869e-8c7b8a2fa288)

![Screenshot (350)](https://github.com/user-attachments/assets/6b2e3051-28cc-4241-b754-ec9390dca0e4)

![Screenshot (351)](https://github.com/user-attachments/assets/3cd0d7d6-3fbc-4964-8f71-21dec475ca5b)

![Screenshot (353)](https://github.com/user-attachments/assets/75dbe8f9-4c8d-462a-a2cc-150d3384a97e)

![Screenshot (354)](https://github.com/user-attachments/assets/63e34e5c-caed-41e7-992a-290fde62e5bf)

similarly we added another layer on top that is tin despoited in the holes and finally mask layer 15  is added 

![Screenshot (362)](https://github.com/user-attachments/assets/79e1d577-f4f1-4a52-b81e-9b229299b582)

![Screenshot (364)](https://github.com/user-attachments/assets/34a2697c-9d3b-4441-b54b-f33cba8474ea)

![Screenshot (365)](https://github.com/user-attachments/assets/e078f0c7-e2e1-467e-93f5-c81dd9144ecf)



** floorplan ** 

![2-1](https://github.com/user-attachments/assets/4d8ce9ad-99a8-472f-93ca-c79e7c6db7cc)

![2-1-1](https://github.com/user-attachments/assets/d0edbb18-f473-421d-90dc-814dc8c69025)

after floorplan the magic tool is used to show the die 

![2-2](https://github.com/user-attachments/assets/b3cae46a-5055-4062-8976-47232d2779fa)

![3-1](https://github.com/user-attachments/assets/f9ef321f-1e2d-4ecc-9729-3259cbb9cfd8)

![1-3](https://github.com/user-attachments/assets/34879653-4610-4e40-a2af-a115ba298f56)

this is layout of the inverter and from the window which popped up has few command that are explored 

like selecting the area and giving the cmd what means it gives the detail about the selected area


![1](https://github.com/user-attachments/assets/ab924c5e-6ce7-4fe4-9b28-d0421f6e838f)


![5](https://github.com/user-attachments/assets/95fecdc6-606f-4e34-91cc-3f5cc1e8e8fa)

# DAY-4

## PRE-LAYOUT TIMING ANALYSIS AND IMPORTANCE OF GOOD CLOCK TREE

### IMING MODELLING USING DELAY TABLES

![1](https://github.com/user-attachments/assets/699f8265-cc91-4642-b256-73bde3dcbd06)

![2](https://github.com/user-attachments/assets/d52517d5-9f2f-41f3-bc2c-1062888adbd0)

![3](https://github.com/user-attachments/assets/224f3532-5876-40c0-bca4-5b56094201e1)

![5-1](https://github.com/user-attachments/assets/e8d3d7f7-b921-464f-9188-006260700048)

![7](https://github.com/user-attachments/assets/aa3faa41-2bd3-47c3-896c-5325f4130701)

![7-1](https://github.com/user-attachments/assets/cc01d608-f301-4692-adc2-98b281f5441d)

--> less is a powerful command-line file pager that lets you view the contents of a file one screen at a time

![3](https://github.com/user-attachments/assets/9dbfbc47-2cf3-45ce-979a-1dbd23e0fdf9)


![7-1](https://github.com/user-attachments/assets/6480998b-8fa7-406a-99c3-d6b99ab202dd)

![7-2](https://github.com/user-attachments/assets/4e37327a-c185-4bb5-a3c6-6159c0a4c168)

![7-3](https://github.com/user-attachments/assets/7b723550-e193-476d-84a1-aa76c4973fda)

![7-4](https://github.com/user-attachments/assets/17246326-5191-43c4-a89d-f6093a4bffe5)

![floorplan 5](https://github.com/user-attachments/assets/c3191868-1595-4466-9fd2-280f059dc438)

the synthesis and floorplan are completed and in magic tool we have viewed the die 

![2](https://github.com/user-attachments/assets/be3d5b3a-fb77-4c94-b6df-b7f7e9135a48)

![3](https://github.com/user-attachments/assets/c3bdcab7-fbc9-44be-be4a-922d6273fd62)

![5](https://github.com/user-attachments/assets/63e0528c-401f-4092-bc9b-14dd112c9361)

![5-1](https://github.com/user-attachments/assets/2edde62b-c4ff-4cfd-9499-a74c7a5d78cb)

![6-2](https://github.com/user-attachments/assets/77b22aa0-7689-4eaf-b401-5dcddacf5142)


![2](https://github.com/user-attachments/assets/3cdba806-4837-4e06-b76d-e881b9f7dcd2)

then we did the cts that is clock tree synthesis and it is criucal step for the design

# DAY -5 

## FINAL STEPS FOR RTL2GDS USING TRITONROUTE AND OPENSTA

After cts , the final step is routing 

![routning final](https://github.com/user-attachments/assets/0f16546d-3a80-4924-a368-8e886da05a76)

routing is divided into two 

1) global route --> Global routing finds approximate paths between source and destination pins within a grid-based layout, helping plan congestion and wire distribution before detailed routing begins.
2) detailed route --> Detailed routing finalizes the precise paths of wires, specifying exact routes, metal layers, and vias to connect all pins without violating design rules

![image](https://github.com/user-attachments/assets/36d114e2-cd29-43fd-8844-fca19dd39216)

here we see the DRC that is Design Rule Check (DRC) is a verification process used in chip design to ensure that the physical layout complies with a set of predefined manufacturing rules provided by the semiconductor foundry.

there few rules that is 1) width 2) spacing 3) pitch between the wires

![image](https://github.com/user-attachments/assets/2d19547d-944e-4933-93ea-c978c7251f2e)
