# DIGTIAL VLSI SoC DESGIN AND PLANNING

Digital VLSI SoC Design and Planning refers to the process of designing and preparing a System-on-Chip (SoC) using Very Large Scale Integration (VLSI) techniques, specifically focused on digital logic circuits.

>- This is a 2 week course of Digital VLSI SoC Design and Planning with complete RTL2GDSII flow organised by VSD in collaboration with NASSCOM

## TABLE OF CONTENTS
DAY - 1
  1. INCEPTION OF OPEN-SOURCE EDA ,OPENLANE AND SKY130 PDK
       * [HOW TO TALK TO COMPUTERS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/blob/main/README.md#how-to-talk-to-computers)
       * [SoC DESIGN AND OPEN LANE](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md#soc-design-and-open-lane)
       * [GET FAMILIAR TO OPEN SOURCE EDA TOOLS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)

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
### HOW TO TALK TO COMPUTERS

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












