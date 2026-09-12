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

## 🔌 Interface Specifications

Quick interface overview. Full details are available in
[Requirements & Design](./docs/requirements-and-design.md).

| Port | Direction | Width | Description |
| :--- | :--- | :--- | :--- |
| `clk` | Input | 1 | Master system clock |
| `reset` | Input | 1 | Synchronous active-high reset |
| `light` | Output | 3 | One-hot encoded traffic lights `{Red, Yellow, Green}` |


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


## 💻 RTL Implementation

The RTL implementation follows strict synthesizable coding standards:

- Separated 2-process FSM modeling (Sequential state/timer registers + Combinational next-state/output logic)
- One-hot state encoding (`S_RED=3'b001`, `S_GREEN=3'b010`, `S_YELLOW=3'b100`) for minimal combinational decode logic and maximum $F_{max}$
- Full case coverage with defensive `default` branches to guarantee zero inferred latches
- Fully synchronous active-high reset aligned with the system clock tree
- Parameterized state dwell times (`RED_CYCLES`, `GREEN_CYCLES`, `YELLOW_CYCLES`)

The Verilog RTL and testbench are available in
[rtl-tb/](./rtl-tb).

## 🧪 Verification Strategy

The dedicated testbench is used to verify:

- Synchronous reset assertion and de-assertion latency
- Cycle-accurate timing verification across all state intervals
- State transition sequence ordering without intermediate invalid states
- Output vector integrity (`light` bus exclusivity: never multiple lights ON simultaneously)
- Extended endurance testing (50+ continuous cycles) verifying terminal recovery and zero deadlock
- Self-checking assertion checks with automated `$error` tracking and summary reporting

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

## 📚 Documentation

- [Requirements & Design](./docs/requirements-and-design.md)
- [FSM Specification](./docs/fsm-specification.md)
- [Verification Summary](./docs/verification-summary.md)
- [Design Decisions & Trade-offs](./docs/design-decisions.md)

## 🧪 Verification & Simulation Results

Verification is executed through a self-checking testbench (`tb/tb_traffic_light_controller.v`) with automated cycle checks and assertion monitoring.

| Test Case | Scenario Description | Expected Behavior | Actual Behavior | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC_01** | Reset Assertion during active run | Immediate return to `S_RED` (`light=3'b100`) | Forced to `S_RED` within 1 cycle | ✅ PASS |
| **TC_02** | Red State Timing Hold | Light remains Red for exactly 6 clock cycles | Counter holds state for 6 cycles | ✅ PASS |
| **TC_03** | Sequential Transition Integrity | Sequenced through `RED -> GREEN -> YELLOW -> RED` | Deterministic cycle sequence verified | ✅ PASS |
| **TC_04** | Terminal Recovery Verification | Continuous execution across 50 full cycles | Zero state lockup or illegal states | ✅ PASS |


## 🛠️ Tools & Technologies

- **HDL:** Verilog HDL 
- **Simulation Engine:** Icarus Verilog 
- **Waveform Debugger:** GTKWave 
- **Synthesis & Linting:** Xilinx Vivado / Verilator
- **Version Control:** Git & GitHub

## 📚 Key RTL Concepts Applied

- **Moore FSM Topology:** Decoupled input-to-output combinational paths for hazard-free outputs.
- **One-Hot State Encoding:** Minimized next-state decode logic depth to reduce critical path delay.
- **Deterministic Reset Recovery:** Synchronous reset architecture eliminating removal/recovery metastability issues.
- **Latch Prevention Disciplines:** Full default assignments and comprehensive case item branching.
- **Self-Checking Verification:** Automated testbenches using tasks, loop assertions, and status counters.
- **Static Timing Awareness:** Registering boundaries to maintain clean setup and hold slack margins.

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

- Fully parameterized cycle registers accessible via an AMBA APB slave bus interface.
- Dual-axis intersection support (North-South / East-West) with conflicting-green hardware interlocks.
- Pedestrian crossing request synchronizer with debounce filtering.
- Emergency vehicle preemption logic with priority interrupt override.

## 🔗 Related

Part of the [RTL Mini-Projects](../README.md) collection.

This project strengthens practical FSM and RTL design skills and provides a
foundation for larger control-oriented digital hardware projects.

