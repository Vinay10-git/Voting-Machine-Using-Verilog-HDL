# 🗳️ Voting Machine Using Verilog HDL

> A digital voting machine designed and implemented using Verilog HDL to demonstrate RTL design, digital logic, vote counting, result generation, and simulation using a hardware description language.

![Verilog](https://img.shields.io/badge/HDL-Verilog-blue)
![Digital Design](https://img.shields.io/badge/Digital-Design-green)
![FPGA](https://img.shields.io/badge/FPGA-Ready-orange)
![Simulation](https://img.shields.io/badge/Simulation-Testbench-purple)
![License](https://img.shields.io/badge/License-MIT-success)

---

## 📖 Overview

The **Voting Machine Using Verilog HDL** is a digital system designed to simulate the basic operation of an electronic voting machine.

The system allows a voter to select a candidate using input switches or buttons. The corresponding candidate's vote count is incremented when a valid vote is cast.

The design is implemented using **Verilog HDL** and can be simulated using an HDL simulation tool. The project demonstrates important concepts of digital system design including:

* Combinational logic
* Sequential logic
* Registers
* Counters
* Clock-based operation
* Reset operation
* RTL design
* Testbench development
* Simulation and verification

---

# 🎯 Objectives

* Design a digital voting machine using Verilog HDL.
* Provide individual voting inputs for candidates.
* Count votes digitally.
* Store the vote count using registers/counters.
* Prevent invalid or unintended voting operations.
* Provide candidate-wise vote results.
* Verify the design using a Verilog testbench.
* Understand RTL-based digital system design.

---

# ✨ Features

* 🗳️ Candidate selection
* 🔢 Automatic vote counting
* 🔄 Reset functionality
* ⏱️ Clock-controlled operation
* 📊 Candidate-wise vote storage
* 🚫 Invalid input handling
* 🧪 Verilog testbench
* 📈 Simulation waveform verification
* 💻 RTL-based digital design

---

# 🏗️ System Architecture

```text
                 ┌─────────────────────┐
                 │    Voting Inputs    │
                 │                     │
                 │ Candidate 1         │
                 │ Candidate 2         │
                 │ Candidate 3         │
                 │ Candidate 4         │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Voting Controller │
                 │                     │
                 │ Input Validation    │
                 │ Vote Processing     │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Vote Counters    │
                 │                     │
                 │ Candidate 1 Count   │
                 │ Candidate 2 Count   │
                 │ Candidate 3 Count   │
                 │ Candidate 4 Count   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Result Display    │
                 │                     │
                 │ Candidate Results   │
                 └─────────────────────┘

                       ▲
                       │
                 ┌─────┴─────┐
                 │ Clock/Reset│
                 └───────────┘
```

---

# 🧠 Working Principle

The voting machine operates using sequential digital logic.

### 1. System Initialization

When the system is powered on or reset is activated, all candidate vote counters are initialized to zero.

```text
Candidate 1 = 0
Candidate 2 = 0
Candidate 3 = 0
Candidate 4 = 0
```

### 2. Candidate Selection

The voter selects a candidate through the corresponding input.

For example:

```text
Candidate 1 → vote input 1
Candidate 2 → vote input 2
Candidate 3 → vote input 3
Candidate 4 → vote input 4
```

### 3. Vote Processing

When a valid candidate input is detected, the corresponding vote counter is incremented.

```text
Candidate 1 selected
        ↓
Candidate 1 Counter
        ↓
Counter = Counter + 1
```

### 4. Vote Storage

The vote counts are stored in registers so that the values are retained until another vote or system reset occurs.

### 5. Result Generation

At the end of the voting process, the stored counts represent the total votes received by each candidate.

---

# 🔄 Voting Process

```text
                 START
                   │
                   ▼
             Initialize
             Vote Counters
                   │
                   ▼
             Wait for Vote
                   │
                   ▼
          Candidate Selected?
             /           \
           NO             YES
           │               │
           │               ▼
           │        Validate Input
           │               │
           │               ▼
           │        Increment
           │        Candidate Count
           │               │
           └───────┬───────┘
                   │
                   ▼
              Continue
              Voting
                   │
                   ▼
                RESET
                   │
                   ▼
             Clear Counters
```

---

# 🔢 Candidate Vote Counting

The basic counting operation is:

```text
New Vote Count = Previous Vote Count + 1
```

For example:

```text
Initial:
Candidate 1 = 0

After first vote:
Candidate 1 = 1

After second vote:
Candidate 1 = 2

After third vote:
Candidate 1 = 3
```

The same principle is applied to each candidate.

---

# 🔌 Inputs and Outputs

The exact signal names depend on the Verilog implementation.

A typical interface can be:

| Signal   | Direction | Description            |
| -------- | --------- | ---------------------- |
| `clk`    | Input     | System clock           |
| `reset`  | Input     | Resets vote counters   |
| `vote1`  | Input     | Candidate 1 vote       |
| `vote2`  | Input     | Candidate 2 vote       |
| `vote3`  | Input     | Candidate 3 vote       |
| `vote4`  | Input     | Candidate 4 vote       |
| `count1` | Output    | Candidate 1 vote count |
| `count2` | Output    | Candidate 2 vote count |
| `count3` | Output    | Candidate 3 vote count |
| `count4` | Output    | Candidate 4 vote count |

> Update the signal names above to exactly match your Verilog source code.

---

# 💻 Technologies Used

* **Verilog HDL**
* RTL Design
* Digital Logic Design
* Sequential Logic
* Counters and Registers
* HDL Simulation
* Testbench Verification

---

# 🛠️ Tools

The project can be developed and simulated using HDL tools such as:

* ModelSim
* QuestaSim
* Vivado
* Quartus Prime
* EDA Playground

Use the tool that matches your actual project implementation.

---

# 📂 Project Structure

```text
voting-machine-using-verilog-hdl
│
├── README.md
├── LICENSE
├── .gitignore
│
├── src/
│   ├── voting_machine.v
│   └── modules/
│
├── testbench/
│   └── voting_machine_tb.v
│
├── simulation/
│   ├── waveform.png
│   └── simulation_results.txt
│
├── docs/
│   ├── Project_Report.pdf
│   └── Presentation.pptx
│
├── images/
│   ├── block_diagram.png
│   ├── flowchart.png
│   ├── rtl_schematic.png
│   └── simulation_waveform.png
│
└── results/
    ├── output.png
    └── test_results.txt
```

---

# 📁 File Description

| File/Folder   | Description                     |
| ------------- | ------------------------------- |
| `src/`        | Main Verilog HDL source code    |
| `testbench/`  | Testbench used for verification |
| `simulation/` | Simulation outputs and waveform |
| `docs/`       | Project report and presentation |
| `images/`     | Diagrams and project images     |
| `results/`    | Test and simulation results     |
| `README.md`   | Project documentation           |

---

# 🧪 Testbench

A Verilog testbench is used to verify the functionality of the voting machine without requiring physical hardware.

The testbench applies different voting combinations and observes the candidate vote counters.

Example test sequence:

```text
Reset
  ↓
Candidate 1 votes
  ↓
Candidate 2 votes
  ↓
Candidate 1 votes
  ↓
Candidate 3 votes
  ↓
Candidate 1 votes
  ↓
Check Results
```

Expected result:

```text
Candidate 1 = 3
Candidate 2 = 1
Candidate 3 = 1
Candidate 4 = 0
```

> Replace this example with your actual testbench sequence and results if they differ.

---

# 📈 Simulation

The design should be verified using a waveform viewer.

Important signals to observe include:

```text
clk
reset
vote1
vote2
vote3
vote4
count1
count2
count3
count4
```

Example:

```text
Clock      ─┐_┌─┐_┌─┐_┌─┐_┌─

Vote 1     ____┌──────────────

Count 1    0────1─────────────
```

The waveform should demonstrate that a valid voting input increments only the corresponding candidate counter.

---

# 🖼️ Project Images

## Block Diagram

Add your actual block diagram:

```md
![Block Diagram](images/block_diagram.png)
```

---

## Flowchart

```md
![Flowchart](images/flowchart.png)
```

---

## RTL Schematic

```md
![RTL Schematic](images/rtl_schematic.png)
```

---

## Simulation Waveform

```md
![Simulation Waveform](images/simulation_waveform.png)
```

---

# 🚀 Simulation Instructions

## Using a Verilog Simulator

1. Clone the repository.

```bash
git clone https://github.com/YOUR_USERNAME/voting-machine-using-verilog-hdl.git
```

2. Open the project in your Verilog simulation environment.

3. Add the design file:

```text
src/voting_machine.v
```

4. Add the testbench:

```text
testbench/voting_machine_tb.v
```

5. Compile the Verilog files.

6. Run the simulation.

7. Open the waveform viewer.

8. Observe the voting inputs and candidate counters.

---

# 🧪 Verification

The design should be tested for:

* Reset operation
* Candidate 1 voting
* Candidate 2 voting
* Candidate 3 voting
* Candidate 4 voting
* Multiple votes for the same candidate
* Different candidate combinations
* Invalid/multiple candidate input conditions
* Counter reset

---

# 📊 Example Result

Example:

| Candidate   | Votes |
| ----------- | ----: |
| Candidate 1 |     3 |
| Candidate 2 |     1 |
| Candidate 3 |     2 |
| Candidate 4 |     0 |

The final values depend on the voting sequence applied during simulation.

---

# ⚙️ RTL Design Concepts Demonstrated

This project provides practical understanding of:

### Sequential Logic

Vote counts are updated synchronously with the clock.

### Counters

Each candidate's votes are maintained using digital counters.

### Registers

Registers store the current vote totals.

### Reset Logic

Reset initializes the voting machine to its starting state.

### Testbench

The testbench verifies the functionality of the RTL design.

### Waveform Analysis

Simulation waveforms are used to verify the relationship between inputs and outputs.

---

# 🌐 Applications

The design concept can be used for:

* Digital electronics education
* FPGA learning
* Verilog HDL projects
* RTL design practice
* Digital voting system prototypes
* Hardware description language training
* FPGA-based embedded systems

> This project is an educational RTL/FPGA prototype and is not intended to represent a certified real-world election system.

---

# ⚠️ Limitations

* This is a prototype digital design.
* It does not implement a complete real-world election security architecture.
* Authentication and voter verification are not included unless implemented separately.
* Secure vote storage is not included in the basic design.
* Physical deployment would require additional security, reliability, auditing, and certification measures.

---

# 🔮 Future Scope

Possible improvements include:

* 🔐 Voter authentication
* 🪪 RFID-based voter identification
* 👆 Fingerprint authentication
* 📺 Seven-segment/LCD result display
* 💾 Non-volatile vote storage
* 🔒 Secure vote storage
* 🏆 Automatic winner detection
* 📊 Real-time vote statistics
* 🖥 FPGA board implementation
* 🔄 Multiple election modes
* 🧪 More extensive verification using SystemVerilog/UVM

---

# 📄 Documentation

The repository contains supporting documentation such as:

* Project Report
* Presentation
* Verilog Source Code
* Testbench
* Block Diagram
* Flowchart
* RTL Schematic
* Simulation Waveform
* Test Results

---

# 📚 Learning Outcomes

Through this project, you can understand:

* Verilog HDL syntax
* RTL design methodology
* Digital counters
* Sequential circuits
* Clocked logic
* Reset design
* Testbench creation
* Simulation
* Waveform analysis
* FPGA-oriented digital design

---

# 👨‍💻 Project Information

**Project Title:** Voting Machine Using Verilog HDL

**Domain:** Digital Electronics / FPGA / VLSI

**HDL:** Verilog

**Design Type:** RTL

**Application:** Digital Voting System Prototype

---

# 📜 License

This project is released under the **MIT License**.

It is intended for educational and research purposes.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ Star.
