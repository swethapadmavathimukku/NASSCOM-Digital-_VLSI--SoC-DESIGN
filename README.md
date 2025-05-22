# DIGTIAL VLSI SoC DESGIN AND PLANNING

Digital VLSI SoC Design and Planning refers to the process of designing and preparing a System-on-Chip (SoC) using Very Large Scale Integration (VLSI) techniques, specifically focused on digital logic circuits.

>- This is a 2 week course of Digital VLSI SoC Design and Planning with complete RTL2GDSII flow organised by VSD in collaboration with NASSCOM

## TABLE OF CONTENTS
DAY - 1
  1. INCEPTION OF OPEN-SOURCE EDA ,OPENLANE AND SKY130 PDK
       * [HOW TO TALK TO COMPUTERS](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
       * [SoC DESIGN AND OPEN LANE](https://github.com/swethapadmavathimukku/NASSCOM-Digital-_VLSI--SoC-DESIGN/edit/main/README.md)
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




