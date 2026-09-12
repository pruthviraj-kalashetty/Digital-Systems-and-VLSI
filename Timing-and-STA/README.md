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

## 🎯 Problem Statement

Define the traffic-control problem and the required behavior of the controller.

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

## 🛠️ Tools & Technologies
- Verilog HDL
- Icarus Verilog
- GTKWave
- Vivado
- Git & GitHub

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

# ⚡ TRAFFIC LIGHT CONTROLLER

### Moore FSM • Timed State Transitions • Synthesizable RTL

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TYPE-MOORE%20FSM-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STATES-3-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20RTL-VERILOG-0F172A?style=for-the-badge&labelColor=020617&color=8B5CF6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20VERIFICATION-IN%20PROGRESS-0F172A?style=for-the-badge&labelColor=020617&color=F59E0B"/>
</p>

---

## 📌 One-Line Summary

A synthesizable Verilog RTL traffic-light controller implemented using a
3-state Moore FSM with synchronous reset and clock-driven state transitions.

## 📌 Overview

The Traffic Light Controller is a synthesizable Verilog RTL project that
implements a predefined traffic-light sequence using a Moore Finite State
Machine (FSM). The project demonstrates FSM-based control, synchronous reset,
timed state transitions, RTL coding, testbench development, simulation, and
waveform analysis.

## 🎯 Problem Statement

Design a digital traffic-light controller that generates the appropriate
Red, Yellow, and Green signals according to a predefined sequence. The
controller must operate synchronously with the system clock and return to a
known initial state when reset is asserted.

## 🎯 Objective

Design and verify a synchronous traffic-light controller using a Moore FSM,
where each FSM state represents a traffic-light condition and determines the
corresponding output.

## 🔌 Inputs and Outputs

Quick interface overview. Full details are available in
[Requirements & Design](./docs/requirements-and-design.md).

| Signal | Direction | Width | Purpose |
|--------|-----------|-------|---------|
| `clk` | Input | 1 | System clock |
| `reset` | Input | 1 | Synchronous reset |
| `light` | Output | 3 | Traffic-light output `{Red, Yellow, Green}` |

## 🏗️ Architecture

The controller consists of a state register, next-state logic, and output
logic. The FSM changes state on the active clock edge and generates the
corresponding traffic-light output based on the current state.

![Block Diagram](./architecture/block-diagram.png)

### FSM State Diagram

![State Diagram](./architecture/state-diagram.png)

### Timing Flow

![Timing Flow](./architecture/timing-flow.png)

Detailed FSM behavior is documented in
[FSM Specification](./docs/fsm-specification.md).

## 🔄 Design Flow

Requirements → FSM Specification → State Encoding → RTL Design →
Testbench → Simulation → Waveform Analysis → RTL Schematic → Verification

## 💻 RTL Implementation

The RTL implementation follows a structured FSM design consisting of:

- State register
- Next-state combinational logic
- Output logic
- Synchronous reset
- Clock-driven state transitions

The Verilog RTL and testbench are available in
[rtl-tb/](./rtl-tb).

## 🧪 Verification Strategy

The dedicated testbench is used to verify:

- Reset behavior
- FSM state transitions
- Traffic-light output sequence
- Clock-driven operation
- Complete state cycle
- Expected versus actual behavior

Detailed verification planning and results are documented in
[Verification Summary](./docs/verification-summary.md).

## 📈 Simulation Evidence

### Waveform

![Waveform](./rtl-tb/waveform.png)

The waveform is analyzed to compare the expected FSM behavior with the actual
simulation output.

### RTL Schematic

![RTL Schematic](./rtl-tb/rtl-schematic.png)

The RTL schematic provides a hardware-oriented view of the structures inferred
from the Verilog RTL.

## 📊 Results & Verification

| Test Case | Expected Behavior | Actual Behavior | Result |
|-----------|-------------------|------------------|--------|
| Reset | Controller enters initial state | — | ⬜ |
| State Transition 1 | Correct light output | — | ⬜ |
| State Transition 2 | Correct light output | — | ⬜ |
| State Transition 3 | Correct light output | — | ⬜ |
| Complete Cycle | Expected sequence repeats correctly | — | ⬜ |

**Legend:** ⬜ Not Tested • 🟡 In Progress • ✅ PASS • ❌ FAIL

> Verification status will be updated after RTL compilation, simulation,
> waveform analysis, and comparison of expected versus actual behavior.

See [Verification Summary](./docs/verification-summary.md) for detailed
PASS/FAIL results.


## 🛠️ Tools & Technologies

- Verilog HDL
- Icarus Verilog
- GTKWave
- Vivado
- Git & GitHub

## 📚 Key RTL Concepts Applied

- Moore FSM
- State encoding
- State register
- Next-state logic
- Synchronous reset
- Combinational output logic
- Latch-free RTL design
- Synthesizable Verilog
- Testbench-based verification
- Waveform debugging

## 💬 Interview Questions

**Q: Why is a Moore FSM used for this design?**  
A: The traffic-light output depends only on the current FSM state, providing
predictable and state-based output behavior.

**Q: Why use synchronous reset?**  
A: The reset is sampled with the clock, allowing the FSM to return to its
initial state synchronously.

**Q: Why are default assignments important in combinational logic?**  
A: Default assignments ensure signals receive defined values and help prevent
unintended latch inference.

**Q: What happens during a state transition?**  
A: The next-state logic determines the upcoming state, and the state register
updates on the active clock edge.

**Q: How can this controller be extended?**  
A: Additional inputs and states can be introduced for features such as
pedestrian crossing, emergency priority, or multi-intersection control.

## ⚖️ Design Decisions & Trade-offs

- **Moore FSM:** Provides predictable state-dependent outputs.
- **Synchronous reset:** Keeps reset behavior aligned with the system clock.
- **Separated FSM logic:** Improves readability, simulation, and debugging.
- **Fixed state sequence:** Keeps the initial design focused on fundamental
  FSM-based RTL implementation.

See [Design Decisions & Trade-offs](./docs/design-decisions.md) for details.

## 🚀 Future Improvements

- Parameterized traffic-light timing
- Pedestrian crossing support
- Emergency priority mode
- Multi-intersection control
- Configurable traffic sequences

## 📚 Documentation

- [Requirements & Design](./docs/requirements-and-design.md)
- [FSM Specification](./docs/fsm-specification.md)
- [Verification Summary](./docs/verification-summary.md)
- [Design Decisions & Trade-offs](./docs/design-decisions.md)

## 🔗 Related

Part of the [RTL Mini-Projects](../README.md) collection.

This project strengthens practical FSM and RTL design skills and provides a
foundation for larger control-oriented digital hardware projects.


