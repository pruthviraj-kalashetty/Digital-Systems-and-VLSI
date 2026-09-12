# ⚡ MINI RTL PROJECTS — INTEGRATED FSM & DATAPATH DESIGNS

### FSM Design • Datapath Integration • Verification • Waveform Analysis

<p>
  <img src="https://img.shields.io/badge/%E2%9A%A1%20DOMAIN-RTL%20DESIGN-0F172A?style=for-the-badge&labelColor=020617&color=2563EB"/>
  <img src="https://img.shields.io/badge/%E2%9C%A6%20FOCUS-FSM%20%26%20DATAPATH-0F172A?style=for-the-badge&labelColor=020617&color=06B6D4"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20PROJECTS-5%20INTEGRATED%20DESIGNS-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFICATION-SELF--CHECKING%20TB-0F172A?style=for-the-badge&labelColor=020617&color=8B5CF6"/>
</p>

---

## 🛠️ Tools Used
<p><img src="https://skillicons.dev/icons?i=github,git,vscode,linux"/></p>

---

## 📌 About This Section

This section contains integrated RTL mini-projects that combine fundamentals from earlier repository sections (combinational logic, sequential circuits, FSM design) into complete, functional systems. Each project follows a full design-to-verification lifecycle: requirements → architecture → RTL → testbench → simulation → documentation.

### 🎯 What Each Project Demonstrates
* **Design Thinking:** Translating a requirement into a block/state diagram before coding.
* **RTL Implementation:** Synthesizable, latch-free Verilog following established coding guidelines.
* **Verification Discipline:** Self-checking testbenches with structured PASS/FAIL validation.
* **Professional Documentation:** Design decisions, trade-offs, and interview-relevant analysis.

---

## 📚 Projects

| # | Project | Focus Area | Status |
|---|---|---|---|
| 01 | [Traffic Light Controller](./01-Traffic-Light-Controller) | Moore FSM, timed transitions | ✅ |
| 02 | [Digital Stopwatch/Clock](./02-Digital-Stopwatch) | Counter + FSM integration | ✅ |
| 03 | [Vending Machine Controller](./03-Vending-Machine-Controller) | Multi-input FSM, conditional logic | ✅ |
| 04 | [4-bit ALU](./04-Four-Bit-ALU) | Datapath, opcode-based control | ✅ |
| 05 | [Elevator Controller](./05-Elevator-Controller) | Priority/arbitration, complex FSM | ✅ |

---

## 🎯 Skills Developed

- FSM Architecture & State Encoding
- Datapath and Control Logic Integration
- Self-Checking Testbench Design
- Waveform-Based Functional Verification
- RTL Schematic Interpretation
- Design Trade-off Analysis

---

## 🔗 Builds Toward

➡ Computer Architecture (Datapath/Control Unit Design)
➡ RTL IP Design (Repository 04)
➡ System-Level Integration (Repository 05)

---
this is 01
# ⚡ TRAFFIC LIGHT CONTROLLER

### Moore FSM • Timed State Transitions • Synthesizable RTL

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TYPE-MOORE%20FSM-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STATES-3-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFIED-4%2F4%20TEST%20CASES-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
</p>

---

## 📌 Project Overview
## 🎯 Objective
## 📋 Functional Requirements
## 🔌 Inputs and Outputs
## 🏗️ Block Diagram / State Diagram
## 💻 RTL Design
## 🧪 Testbench
## 📊 Simulation Results (Waveform)
## 🔍 RTL Schematic
## ✅ Verification Summary
## ⚙️ Design Decisions & Trade-offs
## 🐛 Debugging Notes
## 📚 Key RTL Concepts Learned
## 💬 Interview Questions
## 🚀 Future Improvements
## 📝 Conclusion

this is 02
# ⚡ Traffic Light Controller

### Moore FSM • Timed State Transitions • Synthesizable RTL

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TYPE-MOORE%20FSM-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STATES-3-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFIED-PASS-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
</p>

---

## 📌 Overview
One-paragraph summary: what this project is, what it does, why it was built (mini-project, portfolio piece).

## 🎯 Objective
1-2 sentences — what the design accomplishes.

## 🏗️ Architecture at a Glance
Brief description + embedded diagram:
![State Diagram](./architecture/state-diagram.png)

## 📚 Documentation
- [Requirements & Design](./docs/requirements-and-design.md)
- [FSM Specification](./docs/fsm-specification.md)
- [Verification Summary](./docs/verification-summary.md)
- [Design Decisions](./docs/design-decisions.md)

## 💻 RTL & Testbench
See [`rtl-tb/`](./rtl-tb) for source code, testbench, schematic, and waveform.

## ✅ Verification Status
Short summary line, e.g., "All test cases passed — see [verification summary](./docs/verification-summary.md) for details."

## 🔗 Related
Link back to the parent Mini-Projects index, or note what repo/skill this builds toward.

---

# ⚡ TRAFFIC LIGHT CONTROLLER

### Moore FSM • Timed State Transitions • Synthesizable RTL

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TYPE-MOORE%20FSM-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STATES-3-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFIED-4%2F4%20TEST%20CASES-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
</p>

---

## 📌 Overview
One-paragraph summary: what this project is, what it does, why it was built.

## 🎯 Objective
1-2 sentences — what the design accomplishes.

## 🔌 Inputs and Outputs
Quick table — signal name, direction, width, purpose. (Full detail in [Requirements & Design](./docs/requirements-and-design.md).)

| Signal | Direction | Width | Purpose |
|---|---|---|---|
| clk | input | 1 | System clock |
| reset | input | 1 | Synchronous reset |
| light | output | 3 | {Red, Yellow, Green} |

## 🏗️ Architecture at a Glance
Brief description + embedded diagram:
![State Diagram](./architecture/state-diagram.png)

## 📚 Documentation
- [Requirements & Design](./docs/requirements-and-design.md)
- [FSM Specification](./docs/fsm-specification.md)
- [Verification Summary](./docs/verification-summary.md)
- [Design Decisions & Trade-offs](./docs/design-decisions.md)

## 💻 RTL & Testbench
See [`rtl-tb/`](./rtl-tb) for source code, testbench, schematic, and waveform.

## ✅ Verification Status
All test cases passed — see [verification summary](./docs/verification-summary.md) for the full PASS/FAIL table.

## 📚 Key RTL Concepts Applied
- Moore FSM design (output depends only on current state)
- Synchronous reset handling
- Latch-free combinational next-state logic

## 💬 Interview Questions
**Q: Why Moore FSM instead of Mealy here?**
A: Output (light color) only needs to depend on the current state, not immediate input — Moore avoids glitches on output transitions.

**Q: How would you extend this to a pedestrian crossing signal?**
A: Add a new state and input condition, extend the state transition table accordingly — no core FSM logic change.

## 🚀 Future Improvements
- Add configurable timing (parameterized instead of fixed cycle counts)
- Add pedestrian crossing state extension

## 🔗 Related
Part of the [Mini-Projects](../README.md) collection — builds toward Computer Architecture (control unit design) and future system-level integration.

---

# ⚡ TRAFFIC LIGHT CONTROLLER

### Moore FSM • Timed State Transitions • Synthesizable RTL

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TYPE-MOORE%20FSM-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STATES-3-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFIED-4%2F4%20TEST%20CASES-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
</p>


---

## 📌 Overview

The Traffic Light Controller is a synthesizable Verilog RTL project that
implements a predefined traffic-light sequence using a Moore Finite State
Machine (FSM). The project demonstrates FSM-based control, synchronous reset,
RTL coding, testbench development, simulation, and waveform analysis.

## 🎯 Objective

Design a synchronous traffic-light controller that generates the appropriate
Red, Yellow, and Green signals according to the defined FSM sequence.

## 🔌 Inputs and Outputs

Quick interface overview. Full details are available in
[Requirements & Design](./docs/requirements-and-design.md).

| Signal | Direction | Width | Purpose |
|--------|-----------|-------|---------|
| `clk` | Input | 1 | System clock |
| `reset` | Input | 1 | Synchronous reset |
| `light` | Output | 3 | Traffic-light output `{Red, Yellow, Green}` |

## 🏗️ Architecture

The design consists of a state register, next-state logic, and output logic.
The FSM changes state on the active clock edge and generates traffic-light
outputs based on the current state.

![Block Diagram](./architecture/block-diagram.png)

### FSM State Diagram

![State Diagram](./architecture/state-diagram.png)

## 🔄 Design Flow

Requirements → FSM Design → RTL → Testbench → Simulation → Waveform → RTL Schematic

## 🧪 Verification

The testbench checks:

- Reset behavior
- FSM state transitions
- Traffic-light output sequence
- Clock-driven operation
- Expected versus actual behavior

Detailed results are documented in
[Verification Summary](./docs/verification-summary.md).

## 📊 Simulation Evidence

### Waveform

![Waveform](./rtl-tb/waveform.png)

The waveform is used to compare the expected FSM behavior with the actual
simulation behavior.

### RTL Schematic

![RTL Schematic](./rtl-tb/rtl-schematic.png)

The RTL schematic shows the hardware structures inferred from the Verilog RTL.

## 📚 Documentation

- [Requirements & Design](./docs/requirements-and-design.md)
- [FSM Specification](./docs/fsm-specification.md)
- [Verification Summary](./docs/verification-summary.md)
- [Design Decisions & Trade-offs](./docs/design-decisions.md)

## 💻 RTL & Testbench

See [rtl-tb/](./rtl-tb) for the Verilog RTL, testbench, waveform, and RTL
schematic.

## 📋 Test Cases

| Test Case | Expected Behavior | Result |
|-----------|-------------------|--------|
| Reset | Controller enters initial state | ⬜ |
| State Transition 1 | Correct light output | ⬜ |
| State Transition 2 | Correct light output | ⬜ |
| State Transition 3 | Correct light output | ⬜ |
| Complete Cycle | Expected sequence repeats correctly | ⬜ |

**Legend:** ⬜ Not Tested • 🟡 In Progress • ✅ PASS • ❌ FAIL

## 📚 Key RTL Concepts Applied

- Moore FSM
- State register and next-state logic
- Synchronous reset
- Combinational output logic
- Latch-free RTL design
- Synthesizable Verilog
- Testbench-based simulation
- Waveform debugging

## 💬 Interview Questions

**Q: Why is a Moore FSM used?**  
A: The traffic-light output depends only on the current state, providing
predictable state-based outputs.

**Q: Why use synchronous reset?**  
A: The reset is applied with respect to the clock, allowing the FSM to return
to its initial state synchronously.

**Q: Why are default assignments important in combinational logic?**  
A: They ensure all signals receive defined values and help prevent unintended
latch inference.

**Q: How can this design be extended?**  
A: Additional states and inputs can be introduced for features such as
pedestrian crossing or emergency priority control.

## ⚖️ Design Decisions

- **Moore FSM:** Provides state-dependent and predictable outputs.
- **Synchronous reset:** Keeps reset behavior aligned with the clock.
- **Separated FSM logic:** Makes the RTL easier to understand, simulate, and debug.

See [Design Decisions & Trade-offs](./docs/design-decisions.md) for details.

## 🚀 Future Improvements

- Parameterized traffic-light timing
- Pedestrian crossing support
- Emergency priority mode
- Multi-intersection control

## 🔗 Related

Part of the [RTL Mini-Projects](../README.md) collection.

This project strengthens practical FSM and RTL design skills and provides a
foundation for larger control-oriented digital hardware projects.

---


# 🚦 Traffic Light Controller

[![Language](https://img.shields.io/badge/HDL-SystemVerilog-blue.svg)](https://www.systemverilog.io/)
[![Simulation](https://img.shields.io/badge/Simulation-Icarus%20Verilog-orange.svg)](https://steveicarus.github.io/iverilog/)
[![Waveform](https://img.shields.io/badge/Waveform-GTKWave-green.svg)](https://gtkwave.sourceforge.net/)
[![Lint](https://img.shields.io/badge/Lint-Verilator-purple.svg)](https://www.veripool.org/verilator/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A synthesizable SystemVerilog traffic light controller for a two-road intersection, designed using a finite-state machine and verified with a self-checking testbench.

<p align="center">
  <img src="docs/waveform.png" alt="Traffic light controller waveform" width="850">
</p>

## Overview

This project implements a digital traffic light controller for north-south and east-west traffic. The controller manages the light sequence using a finite-state machine and a programmable cycle counter.

The design includes a safe ALL_RED transition state to prevent both traffic directions from receiving permission to move during a direction change.

## Project Highlights

- Synthesizable SystemVerilog RTL.
- Finite-state-machine-based control.
- Parameterized light timing.
- Separate state, timing, and output logic.
- Self-checking simulation testbench.
- Safety checks for conflicting traffic signals.
- Verilator lint checking.
- Simulation waveform analysis using GTKWave.

## Architecture

text
                 +----------------------+
                 |                      |
                 |      FSM Controller  |
                 |                      |
                 +----------+-----------+
                            |
                            v
                 +----------------------+
                 |                      |
                 |    Timing Counter    |
                 |                      |
                 +----------+-----------+
                            |
                            v
                 +----------------------+
                 |                      |
                 |   Output Decoder     |
                 |                      |
                 +----------+-----------+
                            |
              +-------------+-------------+
              |                           |
              v                           v
       North-South Signals          East-West Signals


## State Sequence

text
NS_GREEN → NS_YELLOW → ALL_RED
                              ↓
EW_GREEN → EW_YELLOW → ALL_RED
      ↑                         ↓
      └─────────────────────────┘


![Traffic light controller state diagram](docs/state_diagram.png)

| State | North-South Road | East-West Road |
|---|---|---|
| NS_GREEN | Green | Red |
| NS_YELLOW | Yellow | Red |
| ALL_RED | Red | Red |
| EW_GREEN | Red | Green |
| EW_YELLOW | Red | Yellow |

## Interface

| Signal | Direction | Width | Description |
|---|---|---:|---|
| clk | Input | 1 | System clock |
| reset | Input | 1 | Controller reset |
| enable | Input | 1 | Enables state progression |
| ns_red | Output | 1 | North-south red light |
| ns_yellow | Output | 1 | North-south yellow light |
| ns_green | Output | 1 | North-south green light |
| ew_red | Output | 1 | East-west red light |
| ew_yellow | Output | 1 | East-west yellow light |
| ew_green | Output | 1 | East-west green light |

## Timing Parameters

The light durations are configurable using SystemVerilog parameters.

| Parameter | Default | Description |
|---|---:|---|
| GREEN_TIME | 10 | Duration of the green state |
| YELLOW_TIME | 3 | Duration of the yellow state |
| ALL_RED_TIME | 1 | Safety transition duration |

Example:

systemverilog
traffic_light_controller #(
    .GREEN_TIME  (10),
    .YELLOW_TIME (3),
    .ALL_RED_TIME(1)
) dut (
    .clk   (clk),
    .reset (reset),
    .enable(enable),
    .ns_red(ns_red),
    .ns_yellow(ns_yellow),
    .ns_green(ns_green),
    .ew_red(ew_red),
    .ew_yellow(ew_yellow),
    .ew_green(ew_green)
);


## Repository Structure

text
traffic-light-controller/
├── README.md
├── LICENSE
├── Makefile
├── .gitignore
│
├── rtl/
│   └── traffic_light_controller.sv
│
├── tb/
│   └── traffic_light_controller_tb.sv
│
├── docs/
│   ├── block_diagram.png
│   ├── state_diagram.png
│   └── waveform.png
│
├── results/
│   ├── simulation_report.md
│   └── lint_report.txt
│
└── .github/
    └── workflows/
        └── simulation.yml


## Tools Used

- SystemVerilog
- Icarus Verilog
- GTKWave
- Verilator
- GNU Make
- GitHub Actions

## Getting Started

### Prerequisites

Install the following tools:

- Icarus Verilog
- GTKWave
- Verilator
- GNU Make

### Clone the Repository

bash
git clone [https://github.com/YOUR_USERNAME/traffic-light-controller.git](https://github.com/YOUR_USERNAME/traffic-light-controller.git)
cd traffic-light-controller


### Run Simulation

bash
make sim


### Run Lint

bash
make lint


### Run All Checks

bash
make all


### View the Waveform

bash
gtkwave waves/traffic_light_controller.vcd


## Verification

The testbench checks:

- Reset behavior.
- Correct initial state.
- North-south traffic sequence.
- East-west traffic sequence.
- Timer expiration.
- State transition order.
- Safe ALL_RED transition.
- Prevention of conflicting green signals.

### Verification Results

| Test | Result |
|---|---|
| Reset behavior | ✅ PASS |
| Initial state | ✅ PASS |
| North-south green timing | ✅ PASS |
| North-south yellow timing | ✅ PASS |
| East-west green timing | ✅ PASS |
| East-west yellow timing | ✅ PASS |
| Safe all-red transition | ✅ PASS |
| Conflicting green signal check | ✅ PASS |

## Safety Properties

The following conditions must always remain true:

text
NS_GREEN and EW_GREEN must never be active together.
NS_GREEN and EW_YELLOW must never be active together.
NS_YELLOW and EW_GREEN must never be active together.
Reset must place the controller in a known state.
Every FSM state must have a valid next state.


## Design Decisions

### Finite State Machine

An FSM was selected because the traffic light controller operates through a defined sequence of operating modes.

### Separate Output Decoder

The output logic is separated from the state-transition logic. This makes the design easier to read, verify, and modify.

### All-Red Safety State

An ALL_RED state is included between direction changes to avoid unsafe simultaneous traffic permissions.

### Parameterized Timing

The timing values are configurable so that the design can be adapted to different clock frequencies and traffic requirements.

## Example Waveform

The expected sequence is:

text
North-South: GREEN → YELLOW → RED
East-West:   RED   → RED    → GREEN → YELLOW


![Simulation waveform](docs/waveform.png)

## Future Improvements

- Add pedestrian crossing control.
- Add emergency vehicle priority.
- Add vehicle sensor inputs.
- Add night flashing mode.
- Add countdown timer display.
- Implement the design on an FPGA development board.
- Add SystemVerilog assertions and functional coverage.

## Learning Outcomes

Through this project, I practiced:

- RTL design using SystemVerilog.
- Finite state machine implementation.
- Sequential and combinational logic.
- Counter-based timing control.
- Self-checking testbench development.
- Simulation and waveform debugging.
- Basic RTL linting and code organization.

## Author

*Your Name*

- GitHub: [@your-username](https://github.com/your-username)
- LinkedIn: [Your LinkedIn Profile](https://www.linkedin.com/in/your-profile/)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
