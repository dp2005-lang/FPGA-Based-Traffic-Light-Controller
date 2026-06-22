# FPGA-Based-Traffic-Light-Controller
Here is a copy-paste-ready GitHub README for **FPGA-Based Traffic Light Controller**:

# 🚦 FPGA-Based Traffic Light Controller

![Verilog](https://img.shields.io/badge/Verilog-HDL-blue)
![FPGA](https://img.shields.io/badge/FPGA-Digital%20Design-orange)
![FSM](https://img.shields.io/badge/FSM-Traffic%20Control-success)
![Simulation](https://img.shields.io/badge/Simulation-Matplotlib-purple)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview

This project implements an **FPGA-Based Traffic Light Controller** using Verilog HDL and Finite State Machine (FSM) design concepts.

The system controls traffic signals at a road intersection using Red, Yellow, and Green lights. It follows a predefined timing sequence to ensure safe and organized movement of vehicles from two directions.

The project can be implemented on an FPGA board using LEDs as traffic lights or verified virtually using Verilog simulation, Python, and Matplotlib waveform visualization.

---

## 🎯 Problem Statement

Traffic intersections require proper signal coordination to avoid accidents, reduce congestion, and maintain safe vehicle movement.

The objective of this project is to design a digital traffic light controller that can:

* Control traffic lights for two road directions
* Generate Red, Yellow, and Green signal sequences
* Use timing delays for each traffic signal
* Ensure only one road receives a Green signal at a time
* Use an FSM for safe state transitions
* Support FPGA LED implementation
* Verify operation using simulation waveforms

---

## 🏗️ Project Architecture

```text
                   +-------------------+
                   | FPGA Board Clock  |
                   +---------+---------+
                             |
                             v
                   +-------------------+
                   | Clock Divider /   |
                   | Clock Enable      |
                   +---------+---------+
                             |
                             v
                   +-------------------+
                   | Finite State      |
                   | Machine Controller|
                   +---------+---------+
                             |
          +------------------+------------------+
          |                                     |
          v                                     v
+----------------------+              +----------------------+
| Road A Signal Output |              | Road B Signal Output |
| Red / Yellow / Green |              | Red / Yellow / Green |
+----------------------+              +----------------------+
```

---

## ⚙️ Features

* 🚦 Two-road traffic signal control
* 🔴 Red light control
* 🟡 Yellow light control
* 🟢 Green light control
* ⏱️ Parameterizable timing delays
* 🔁 Automatic traffic signal sequencing
* 🧠 FSM-based design
* ⚡ Clock-enable based timing logic
* 💡 FPGA LED output support
* 🧪 Verilog testbench verification
* 📊 Virtual waveform visualization using Matplotlib
* ⚙️ Yosys and Vivado synthesis support

---

## 🧠 VLSI Concepts Used

| Concept              | Purpose                                       |
| -------------------- | --------------------------------------------- |
| Verilog HDL          | Describes the hardware behavior               |
| FPGA                 | Implements the traffic controller in hardware |
| Clock Divider        | Generates slow timing ticks from FPGA clock   |
| Clock Enable         | Controls timing without gated clocks          |
| Finite State Machine | Controls traffic light sequence               |
| Sequential Logic     | Stores the current traffic state              |
| Combinational Logic  | Generates Red, Yellow, and Green outputs      |
| Counters             | Maintains timing for each traffic state       |
| Reset Logic          | Initializes the system to a safe state        |
| Testbench            | Verifies traffic signal transitions           |
| Waveform Simulation  | Displays timing and signal behavior           |

---

## 🔄 Traffic Light Sequence

The traffic controller follows this sequence:

```text
Road A Green  → Road A Yellow → Road B Green → Road B Yellow → Repeat
```

During Road A Green, Road B remains Red.

During Road B Green, Road A remains Red.

### State Transition Diagram

```text
                +-------------------+
                | ROAD_A_GREEN      |
                | A = Green         |
                | B = Red           |
                +---------+---------+
                          |
                          v
                +-------------------+
                | ROAD_A_YELLOW     |
                | A = Yellow        |
                | B = Red           |
                +---------+---------+
                          |
                          v
                +-------------------+
                | ROAD_B_GREEN      |
                | A = Red           |
                | B = Green         |
                +---------+---------+
                          |
                          v
                +-------------------+
                | ROAD_B_YELLOW     |
                | A = Red           |
                | B = Yellow        |
                +---------+---------+
                          |
                          +----------------------+
                                                 |
                                                 v
                                         ROAD_A_GREEN
```

---

## 🚦 Traffic Signal Output Table

| State         | Road A | Road B |
| ------------- | ------ | ------ |
| ROAD_A_GREEN  | Green  | Red    |
| ROAD_A_YELLOW | Yellow | Red    |
| ROAD_B_GREEN  | Red    | Green  |
| ROAD_B_YELLOW | Red    | Yellow |

---

## ⏱️ Example Timing Table

| Signal State  | Example Duration |
| ------------- | ---------------: |
| Road A Green  |       10 seconds |
| Road A Yellow |        3 seconds |
| Road B Green  |       10 seconds |
| Road B Yellow |        3 seconds |

> Timing values can be changed using Verilog parameters.

---

## 📁 Folder Structure

```text
FPGA-Traffic-Light-Controller/
│
├── rtl/
│   ├── clock_enable.v
│   ├── traffic_light_fsm.v
│   └── top.v
│
├── tb/
│   └── traffic_light_tb.v
│
├── constraints/
│   └── traffic_light_constraints.xdc
│
├── simulation/
│   └── traffic_light_simulation.ipynb
│
├── waveforms/
│   ├── traffic_sequence_waveform.png
│   ├── state_transition_waveform.png
│   └── reset_waveform.png
│
├── reports/
│   ├── synthesis_report.txt
│   └── utilization_report.txt
│
├── images/
│   ├── architecture.png
│   ├── fsm_diagram.png
│   └── simulation_output.png
│
├── docs/
│   └── project_report.pdf
│
├── README.md
└── .gitignore
```

---

## 🛠️ Tools and Technologies

| Tool                    | Purpose                                   |
| ----------------------- | ----------------------------------------- |
| Verilog / SystemVerilog | RTL hardware design                       |
| Xilinx Vivado           | FPGA synthesis and implementation         |
| Yosys                   | Open-source Verilog synthesis             |
| ModelSim                | RTL simulation                            |
| EDA Playground          | Browser-based Verilog simulation          |
| Google Colab            | Virtual simulation platform               |
| Python                  | Virtual signal simulation                 |
| Matplotlib              | Waveform and traffic signal visualization |
| GitHub                  | Documentation and portfolio hosting       |

---

## 🚀 How to Run Virtual Simulation in Google Colab

### Step 1: Open Google Colab

```text
https://colab.research.google.com/
```

### Step 2: Create a New Notebook

Name the notebook:

```text
FPGA_Traffic_Light_Controller_Simulation.ipynb
```

### Step 3: Install Required Libraries

```python
!pip install matplotlib numpy
```

### Step 4: Run Simulation Cells

Run the cells for:

* Clock generation
* FSM state transitions
* Traffic light output generation
* Timing counter simulation
* Matplotlib waveform plotting

### Step 5: View the Output

The simulation will display:

* Road A traffic signal sequence
* Road B traffic signal sequence
* FSM state transition waveform
* Red, Yellow, and Green light timing
* Reset behavior

---

## 🧪 Testbench Verification

The Verilog testbench verifies the following conditions:

| Test Case                | Expected Result                             |
| ------------------------ | ------------------------------------------- |
| Reset condition          | Road A starts Green and Road B starts Red   |
| Road A Green duration    | Road A stays Green for configured time      |
| Road A Yellow transition | Road A changes from Green to Yellow         |
| Road B Green transition  | Road B changes to Green after Road A Yellow |
| Road B Yellow transition | Road B changes from Green to Yellow         |
| Continuous operation     | Sequence repeats correctly                  |
| Safety check             | Both roads never become Green together      |

---

## 📊 Expected Waveform Behavior

```text
Time →
Road A Green   ██████████____________________
Road A Yellow  __________████________________
Road A Red     ________________██████████████

Road B Red     ██████████████________________
Road B Green   ________________██████████____
Road B Yellow  __________________________████
```

The waveform confirms that only one road receives a Green signal at a time.

---

## ⚙️ FPGA Implementation Steps

1. Create a new Vivado project.
2. Select your FPGA board or target device.
3. Add Verilog files from the `rtl/` folder.
4. Add the testbench file from the `tb/` folder.
5. Add the XDC constraints file from the `constraints/` folder.
6. Assign FPGA LEDs to Road A and Road B Red, Yellow, and Green outputs.
7. Run behavioral simulation.
8. Run synthesis and check resource utilization.
9. Run implementation.
10. Generate the bitstream.
11. Program the FPGA board.
12. Observe LEDs changing according to traffic signal sequence.

---

## 📸 Screenshots Checklist

Upload these screenshots to your GitHub repository:

* [ ] Verilog RTL code screenshot
* [ ] Clock enable module screenshot
* [ ] FSM code screenshot
* [ ] State transition diagram
* [ ] Testbench code screenshot
* [ ] Reset waveform
* [ ] Road A signal waveform
* [ ] Road B signal waveform
* [ ] Full traffic sequence waveform
* [ ] Matplotlib virtual simulation output
* [ ] Yosys synthesis report
* [ ] Vivado utilization report
* [ ] FPGA board LED output photo or video, if available
* [ ] GitHub repository preview

---

## 🌍 Real-World Applications

This project represents traffic control systems used in:

* 🚦 Road intersections
* 🏙️ Smart city traffic management
* 🅿️ Parking systems
* 🚧 Railway crossing controllers
* 🏭 Industrial safety systems
* 🚘 Toll booth systems
* 🏢 Building access control systems
* 🤖 Automated vehicle coordination systems

---

## 📈 Future Improvements

* Pedestrian crossing button support
* Emergency vehicle priority mode
* Vehicle density sensor input
* Countdown timer display
* Four-way intersection support
* Smart traffic control using AI
* IoT-based remote monitoring
* Camera-based vehicle detection
* Adaptive traffic timing
* LCD display integration

---

## 🎓 Learning Outcomes

After completing this project, you will understand:

* FPGA-based digital system design
* Verilog HDL coding
* Finite State Machine design
* Clock enable generation
* Counter-based timing control
* Traffic signal sequencing
* Reset and safety logic
* Testbench development
* Waveform simulation
* FPGA synthesis workflow
* GitHub documentation practices

---

## 👨‍💻 Author

**Name:** Debankita Panja
**Project Type:** VLSI / FPGA / Digital Design
**Level:** Beginner-Friendly and Industry-Oriented
**Platform:** Verilog, Google Colab, Yosys, Vivado, ModelSim

---

## ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

Feel free to fork this repository and improve it with advanced traffic control features.
