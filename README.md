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
       * [CHIP FLOOR PLANNING CONSIDERATIONS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
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












