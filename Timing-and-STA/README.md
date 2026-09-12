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

# ◈ Traffic Light Controller

> **Verilog RTL • Moore FSM • Synchronous Reset • Simulation & Verification**

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
