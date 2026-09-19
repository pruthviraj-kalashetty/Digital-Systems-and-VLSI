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

| Test Case | Scenario Description | Expected Behavior | Actual Behavior | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC_01** | Reset Assertion during active run | Immediate return to `S_RED` (`light=3'b100`) | Forced to `S_RED` within 1 cycle | ✅ PASS |
| **TC_02** | Red State Timing Hold | Light remains Red for exactly 6 clock cycles | Counter holds state for 6 cycles | ✅ PASS |
| **TC_03** | Sequential Transition Integrity | Sequenced through `RED -> GREEN -> YELLOW -> RED` | Deterministic cycle sequence verified | ✅ PASS |
| **TC_04** | Terminal Recovery Verification | Continuous execution across 50 full cycles | Zero state lockup or illegal states | ✅ PASS |

## Repository Structure

```text
└── 01-traffic-light-controller/
    │
    ├── README.md
    │
    ├── docs/
    │   ├── requirements-and-design.md
    │   ├── fsm-specification.md
    │   ├── verification-summary.md
    │   └── design-decisions.md
    │
    ├── architecture/
    │   ├── block-diagram.png
    │   ├── state-diagram.png
    │   └── timing-flow.png
    │
    └── rtl-tb/
        ├── README.md
        ├── traffic_light_controller.v
        ├── traffic_light_controller_tb.v
        ├── rtl-schematic.png
        └── waveform.png
```

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

---

# Requirements & Design Specification — Traffic Light Controller

| | |
|---|---|
| **Document Version** | 1.0 |
| **Status** | Approved for Implementation |
| **Project** | RTL Mini-Projects — 01 |
| **Target HDL** | Verilog (Synthesizable Subset) |

---

## 1. Problem Statement

Design a digital traffic-light controller that generates the correct sequence of Red, Yellow, and Green signals across deterministic intervals. The controller must operate synchronously within a single clock domain, maintain cycle-accurate phase holds, and return to a known safe state immediately upon reset assertion.

## 2. Objective

Design and verify a synchronous, parameterizable Moore FSM in synthesizable Verilog. The design integrates an internal cycle-accurate timer register with registered state logic, targeting latch-free structure and glitch-free output transitions.

## 3. Scope Boundaries

**In Scope**
* Single-intersection, fixed forward sequence: `S_RED` → `S_GREEN` → `S_YELLOW` → `S_RED`.
* Parameterized dwell-time counters for each operational state.
* Synchronous active-high reset recovery within 1 clock cycle.
* Decoupled Moore output decoding to prevent combinational path glitches.

**Out of Scope**
* Pedestrian walk requests and emergency vehicle preemption.
* Multi-axis cross-traffic arbitration.
* Runtime dynamic timing configuration via a software-accessible bus (e.g., APB/AXI).

## 4. Operational Assumptions

* Single clock domain driving all flip-flop clock pins.
* Synchronous active-high reset, sampled with `posedge clk`.
* Output bus `light[2:0]` drives downstream logic within the same design (no external electrical constraints assumed).

## 5. Functional Requirements

| ID | Requirement Description | Verification Method |
|---|---|---|
| **REQ-F01** | Cycle through `S_RED` → `S_GREEN` → `S_YELLOW` → `S_RED` in strict sequence without skipping states. | Testbench state sequence check |
| **REQ-F02** | Each state holds its active output for exactly N clock cycles defined by parameters (`RED_CYCLES`, `GREEN_CYCLES`, `YELLOW_CYCLES`). | Testbench cycle counting |
| **REQ-F03** | Assertion of synchronous `reset` forces the FSM to `S_RED` and clears the timer within 1 clock cycle. | Testbench reset check |
| **REQ-F04** | Output bus `light[2:0]` must be one-hot at all times; multiple active lights is an invalid condition. | Testbench output check (manual comparison, each cycle) |
| **REQ-F05** | The core runs continuously over extended run times without state lockup or illegal states. | 50+ cycle testbench stress run |

## 6. Non-Functional & Microarchitecture Constraints

| ID | Requirement Description | Verification Method |
|---|---|---|
| **REQ-NF01** | Fully synthesizable RTL using standard Verilog synthesizable constructs; no simulation-only delay logic. | Manual code review against synthesizable coding guidelines |
| **REQ-NF02** | Latch-free design: complete branch assignments in all combinational blocks. | Manual code review; Verilator lint check planned |
| **REQ-NF03** | Synchronous reset architecture, sampled on the clock edge. | Design review (formal STA not yet performed) |
| **REQ-NF04** | All state durations parameterized via `parameter` declarations, avoiding hardcoded magic numbers. | Manual code review |

## 7. Interface Specification

```text
              ┌───────────────────────────┐
   clk   ───▶ │                           │
   reset ───▶ │  traffic_light_controller │ ───▶ light[2:0]
              │                           │
              └───────────────────────────┘
```

| Signal | Direction | Width | Reset Value | Description |
|---|---|---|---|---|
| `clk` | Input | 1 | — | Primary system clock (positive-edge triggered). |
| `reset` | Input | 1 | — | Synchronous active-high system reset. |
| `light[2]` | Output | 1 | `1'b1` | Active-high **Red Light** indicator. |
| `light[1]` | Output | 1 | `1'b0` | Active-high **Yellow Light** indicator. |
| `light[0]` | Output | 1 | `1'b0` | Active-high **Green Light** indicator. |

## 8. Design Architecture

The controller partitions timing from control logic across two functional processes:

```text
   clk, reset          Sequential Process           Combinational Process
        │            (State + Timer Register)         (Next-State + Output)
        ▼                      │                              │
   ┌─────────┐                 ▼                              ▼
   │  Timer  │ ──────▶  ┌─────────────┐   current   ┌───────────────────┐   light[2:0]
   │ Counter │          │ State Reg   │ ──state───▶  │  Output Decode    │ ────────────▶
   └─────────┘          └─────────────┘              └───────────────────┘
```

1. **Sequential State & Timer Process:** A clocked `always @(posedge clk)` block registers current state and increments an internal cycle counter until terminal count is reached, triggering the next state.
2. **Combinational Moore Output Process:** An `always @(*)` block decodes the registered state into the one-hot `light[2:0]` bus. Because outputs depend solely on state registers, combinational glitches from input transitions cannot propagate to downstream logic.

## 9. Requirements Traceability Matrix (RTM)

| Requirement ID | Verification Test Case | Expected Result | Status |
|---|---|---|---|
| **REQ-F01** | `TC_03` (Sequential Transition Integrity) | Order verified: `RED` → `GREEN` → `YELLOW` | *(fill in after simulation)* |
| **REQ-F02** | `TC_02` (State Timing Hold Verification) | Cycle counts match parameter values | *(fill in after simulation)* |
| **REQ-F03** | `TC_01` (Reset Latency Check) | Immediate return to `S_RED` on clock edge | *(fill in after simulation)* |
| **REQ-F04** | `TC_03` (Output Mutual Exclusion) | Exactly one light active every cycle | *(fill in after simulation)* |
| **REQ-F05** | `TC_04` (Extended Run Stress) | Zero deadlock or undefined states over 50 cycles | *(fill in after simulation)* |

## 10. Related Documents

- [FSM Specification](./fsm-specification.md)
- [Verification Summary](./verification-summary.md)
- [Design Decisions & Trade-offs](./design-decisions.md)

- ---

# Requirements & Design Specification — Traffic Light Controller

| Field | Value |
|---|---|
| **Document Version** | 1.1 |
| **Status** | Approved for Implementation |
| **Project** | RTL Mini-Projects — 01 |
| **Target HDL** | Verilog-2001, synthesizable RTL |
| **Design Style** | Parameterized Moore finite-state machine |

---

## 1. Problem Statement

A two-road intersection requires controlled right-of-way assignment between north/south (NS) and east/west (EW) traffic. The controller shall sequence red, yellow, and green lamp indications using a single synchronous clock domain.

The design shall ensure that both roads never receive green simultaneously and shall include an all-red clearance interval before right-of-way changes from one direction to the other.

## 2. Objective

Design and verify a synthesizable, parameterized Moore finite-state machine in Verilog. The controller shall use a registered state machine and cycle counter to generate exact green, yellow, and all-red durations.

The design shall be safe, deterministic, latch-free, and configurable through timing parameters.

## 3. Scope Boundaries

### In Scope

- One fixed-time intersection with NS and EW traffic directions.
- Six FSM states representing green, yellow, and all-red phases.
- Parameterized green, yellow, and all-red durations.
- Active-high synchronous reset.
- Cycle-accurate state-duration control.
- One-hot lamp indication for each direction.
- Automatic recovery from an illegal FSM state.

### Out of Scope

- Vehicle sensors and adaptive timing.
- Pedestrian walk signals.
- Emergency-vehicle preemption.
- Flashing-lamp operation.
- Multi-intersection coordination.
- Software-controlled runtime configuration through APB, AXI, or another bus.
- Physical electrical lamp-driver circuitry.

## 4. Operational Assumptions

- The design operates in one clock domain.
- `rst` is an active-high synchronous reset sampled on `posedge clk`.
- A timing parameter represents clock cycles, not real-time seconds.
- The integrating system chooses timing parameters based on its clock frequency.
- `GREEN_CYCLES`, `YELLOW_CYCLES`, and `ALL_RED_CYCLES` shall each be greater than or equal to one.
- All outputs are active high.
- Each traffic direction shall have exactly one active lamp during every legal FSM state.

## 5. Configuration Parameters

| Parameter | Default Value | Valid Range | Description |
|---|---:|---:|---|
| `GREEN_CYCLES` | 5 | ≥ 1 | Duration of each green phase in clock cycles |
| `YELLOW_CYCLES` | 2 | ≥ 1 | Duration of each yellow phase in clock cycles |
| `ALL_RED_CYCLES` | 1 | ≥ 1 | Clearance duration when both roads are red |

## 6. FSM State Definition

| State | Encoding | NS Lamps | EW Lamps | Duration |
|---|---|---|---|---|
| `NS_GREEN` | `3'b000` | Green | Red | `GREEN_CYCLES` |
| `NS_YELLOW` | `3'b001` | Yellow | Red | `YELLOW_CYCLES` |
| `ALL_RED_TO_EW` | `3'b010` | Red | Red | `ALL_RED_CYCLES` |
| `EW_GREEN` | `3'b011` | Red | Green | `GREEN_CYCLES` |
| `EW_YELLOW` | `3'b100` | Red | Yellow | `YELLOW_CYCLES` |
| `ALL_RED_TO_NS` | `3'b101` | Red | Red | `ALL_RED_CYCLES` |

The normal phase sequence is:

```text
NS_GREEN → NS_YELLOW → ALL_RED_TO_EW →
EW_GREEN → EW_YELLOW → ALL_RED_TO_NS → NS_GREEN
```

## 7. Timing Convention

A state with a duration of `N` shall remain active for exactly `N` rising clock intervals.

The timer counter shall increment while the FSM remains in its current state. A state transition shall occur when:

```text
count == duration - 1
```

When a transition occurs, the counter shall clear to zero and begin timing the next state.

## 8. Safety Invariants

The following conditions shall be true throughout normal operation:

1. `ns_green` and `ew_green` shall never be asserted simultaneously.
2. NS traffic shall have exactly one active lamp in every legal state.
3. EW traffic shall have exactly one active lamp in every legal state.
4. Every direction change shall pass through an all-red clearance state.
5. Reset shall return the controller to a known legal state.
6. An illegal state encoding shall recover to the safe `NS_GREEN` state.
7. Default output decoding for an illegal state shall drive both directions red.

## 9. Functional Requirements

| ID | Requirement Description | Verification Method |
|---|---|---|
| **REQ-F01** | The FSM shall follow the defined six-state phase sequence without skipping a legal state. | Testbench state-sequence check |
| **REQ-F02** | `NS_GREEN` and `EW_GREEN` shall each remain active for exactly `GREEN_CYCLES`. | Testbench cycle-count check |
| **REQ-F03** | `NS_YELLOW` and `EW_YELLOW` shall each remain active for exactly `YELLOW_CYCLES`. | Testbench cycle-count check |
| **REQ-F04** | Each all-red state shall remain active for exactly `ALL_RED_CYCLES`. | Testbench cycle-count check |
| **REQ-F05** | When `rst=1` at a rising clock edge, the FSM shall enter `NS_GREEN` and clear the timer counter to zero. | Testbench reset-recovery check |
| **REQ-F06** | NS and EW green outputs shall never be high at the same time. | Assertion or testbench safety check on every clock |
| **REQ-F07** | Each direction shall have exactly one asserted lamp in every legal state. | One-hot output check on every clock |
| **REQ-F08** | The controller shall repeat the complete traffic cycle continuously. | Full-cycle repeat check |
| **REQ-F09** | An illegal FSM state shall select safe recovery behavior. | Directed illegal-state recovery test |

## 10. Non-Functional and Microarchitecture Requirements

| ID | Requirement Description | Verification Method |
|---|---|---|
| **REQ-NF01** | The RTL shall use only synthesizable Verilog constructs. | RTL review and synthesis-tool check |
| **REQ-NF02** | Sequential storage shall be implemented only in clocked blocks using `posedge clk`. | RTL review |
| **REQ-NF03** | Combinational blocks shall assign defaults or cover all branches to prevent latch inference. | RTL review and lint check |
| **REQ-NF04** | Timing values shall be parameterized; the RTL shall not contain hardcoded phase durations. | RTL review |
| **REQ-NF05** | Outputs shall depend only on the registered FSM state. | RTL review of Moore output decoder |
| **REQ-NF06** | The design shall use a single clock domain and shall not require clock-domain-crossing logic. | Architecture review |

## 11. Interface Specification

```text
                   ┌────────────────────────────────┐
      clk    ─────▶ │                                │
      rst    ─────▶ │   traffic_light_controller     │
                   │                                │
  ns_red           │ ──────────────────────────────▶ │ NS red
  ns_yellow        │ ──────────────────────────────▶ │ NS yellow
  ns_green         │ ──────────────────────────────▶ │ NS green
  ew_red           │ ──────────────────────────────▶ │ EW red
  ew_yellow        │ ──────────────────────────────▶ │ EW yellow
  ew_green         │ ──────────────────────────────▶ │ EW green
                   └────────────────────────────────┘
```

| Signal | Direction | Width | Reset-State Value | Description |
|---|---|---:|---|---|
| `clk` | Input | 1 | — | Primary positive-edge-triggered system clock |
| `rst` | Input | 1 | — | Active-high synchronous reset |
| `ns_red` | Output | 1 | `1'b0` | North/south red-lamp command |
| `ns_yellow` | Output | 1 | `1'b0` | North/south yellow-lamp command |
| `ns_green` | Output | 1 | `1'b1` | North/south green-lamp command |
| `ew_red` | Output | 1 | `1'b1` | East/west red-lamp command |
| `ew_yellow` | Output | 1 | `1'b0` | East/west yellow-lamp command |
| `ew_green` | Output | 1 | `1'b0` | East/west green-lamp command |

## 12. Design Architecture

The controller uses registered state and timing storage, with combinational next-state, duration-selection, and output-decode logic.

```text
                            ┌─────────────────────┐
                            │  Duration Selection │
                            │  state → duration   │
                            └─────────┬───────────┘
                                      │
                                      ▼
┌──────────┐     ┌──────────────┐   terminal    ┌─────────────────┐
│ clk, rst │ ──▶ │ State Register│ ────────────▶ │ Next-State Logic│
└──────────┘     │   3-bit FSM   │ ◀──────────── │                 │
                 └──────┬───────┘   next_state  └─────────────────┘
                        │
                        │ current state
              ┌─────────┴──────────┐
              ▼                    ▼
┌─────────────────────┐    ┌─────────────────────┐
│ Timer / Counter Reg │    │ Moore Output Decode │
│ clear or increment  │    │ state → lamp outputs│
└─────────────────────┘    └─────────────────────┘
```

### Architecture Rules

1. The state register and counter are updated only on `posedge clk`.
2. Reset has priority over normal state progression.
3. The counter clears when the FSM enters a new state.
4. The output decoder depends only on the registered state.
5. The output decoder defaults to both directions red for an illegal state.

## 13. Requirements Traceability Matrix

| Requirement ID | Test Case | Expected Result | Status |
|---|---|---|---|
| **REQ-F01** | `TC-01`: State sequence | Six states occur in the specified order | Pending simulation |
| **REQ-F02** | `TC-02`: Green duration | Each green state lasts `GREEN_CYCLES` | Pending simulation |
| **REQ-F03** | `TC-03`: Yellow duration | Each yellow state lasts `YELLOW_CYCLES` | Pending simulation |
| **REQ-F04** | `TC-04`: All-red duration | Each clearance state lasts `ALL_RED_CYCLES` | Pending simulation |
| **REQ-F05** | `TC-05`: Reset recovery | State becomes `NS_GREEN`; count becomes zero | Pending simulation |
| **REQ-F06** | `TC-06`: Green mutual exclusion | NS and EW green are never both high | Pending simulation |
| **REQ-F07** | `TC-07`: Lamp one-hot check | Exactly one lamp per direction is active | Pending simulation |
| **REQ-F08** | `TC-08`: Cycle repeat | FSM returns to `NS_GREEN` after one full sequence | Pending simulation |
| **REQ-F09** | `TC-09`: Illegal-state recovery | Controller returns to safe state | Pending simulation |

## 14. Related Documents

- [FSM Specification](./fsm-specification.md)
- [Design Decisions](./design-decisions.md)
- [Verification Summary](./verification-summary.md)
- [State Diagram](../architecture/state-diagram.png)
- [Block Diagram](../architecture/block-diagram.png)
- [Timing Flow](../architecture/timing-flow.png)
---

# Requirements and Design

| Field | Value |
|---|---|
| Document version | 1.1 |
| Status | Approved for implementation |
| Target HDL | Verilog-2001 synthesizable subset |
| Design style | Parameterized Moore FSM |

## 1. Project purpose

Design and verify a synthesizable Verilog controller for a standard four-way road intersection. The controller operates two opposing traffic flows:

- **North/South (NS)**
- **East/West (EW)**

Each flow receives a red, yellow, or green indication. Opposing directions in the same flow share an indication; for example, northbound and southbound traffic are both represented by the NS output.

## 2. Scope

### Included in version 1

- A synchronous finite-state-machine (FSM) controller.
- A single clock input and synchronous active-high reset.
- Fixed, parameterized durations for green, yellow, and all-red intervals.
- Individual 3-bit outputs for NS and EW lights.
- A Verilog testbench that checks the normal sequence and reset behavior.

### Not included in version 1

- Pedestrian crossing requests.
- Vehicle sensors, adaptive timing, or traffic-priority rules.
- Flashing operation, fault detection, or emergency-vehicle pre-emption.
- Separate left-turn phases.
- Physical signal-driver circuitry or clock-divider hardware.

These features can be added as later versions without changing the basic safety model.

## 3. Functional requirements

| ID | Requirement |
|---|---|
| FR-01 | After reset, NS must be green and EW must be red. |
| FR-02 | The controller must follow this repeating order: NS green → NS yellow → all red → EW green → EW yellow → all red → NS green. |
| FR-03 | A green interval must last `GREEN_TIME` clock cycles. |
| FR-04 | A yellow interval must last `YELLOW_TIME` clock cycles. |
| FR-05 | Each all-red clearance interval must last `ALL_RED_TIME` clock cycles. |
| FR-06 | During either green or yellow interval, the other traffic flow must remain red. |
| FR-07 | During an all-red interval, both traffic flows must be red. |
| FR-08 | The timing parameters must be compile-time Verilog parameters, allowing different timing plans without changing the FSM logic. |

## 4. Safety requirements

| ID | Requirement |
|---|---|
| SR-01 | NS and EW must never both be green. |
| SR-02 | NS and EW must never both be yellow. |
| SR-03 | Every change of right-of-way must include an all-red clearance state. |
| SR-04 | Reset and invalid FSM states must produce a safe state: NS green and EW red after reset; both red while an invalid state is being recovered. |

## 5. Interface definition

| Signal | Direction | Width | Description |
|---|---:|---:|---|
| `clk` | Input | 1 | System clock; state and timer update on its rising edge. |
| `reset` | Input | 1 | Active-high synchronous reset, sampled on the rising edge of `clk`. |
| `north_south` | Output | 3 | NS traffic-light indication. |
| `east_west` | Output | 3 | EW traffic-light indication. |

### Light encoding

The output is one-hot encoded to simplify connection to three separate lamps.

| Name | Value | Meaning |
|---|---:|---|
| `RED` | `3'b100` | Stop |
| `YELLOW` | `3'b010` | Prepare to stop |
| `GREEN` | `3'b001` | Proceed |

## 6. FSM State Definition

The design is implemented as a 6-state Moore finite-state machine. Light outputs depend strictly on the active state, and state transitions occur once the elapsed clock count matches the configured parameter duration.

| State | Encoding | NS Output (`north_south`) | EW Output (`east_west`) | Duration (Cycles) | Next State |
|---|:---:|:---:|:---:|:---:|---|
| `NS_GREEN` | `3'b000` | `GREEN` (`3'b001`) | `RED` (`3'b100`) | `GREEN_CYCLES` | `NS_YELLOW` |
| `NS_YELLOW` | `3'b001` | `YELLOW` (`3'b010`) | `RED` (`3'b100`) | `YELLOW_CYCLES` | `ALL_RED_TO_EW` |
| `ALL_RED_TO_EW` | `3'b010` | `RED` (`3'b100`) | `RED` (`3'b100`) | `ALL_RED_CYCLES` | `EW_GREEN` |
| `EW_GREEN` | `3'b011` | `RED` (`3'b100`) | `GREEN` (`3'b001`) | `GREEN_CYCLES` | `EW_YELLOW` |
| `EW_YELLOW` | `3'b100` | `RED` (`3'b100`) | `YELLOW` (`3'b010`) | `YELLOW_CYCLES` | `ALL_RED_TO_NS` |
| `ALL_RED_TO_NS` | `3'b101` | `RED` (`3'b100`) | `RED` (`3'b100`) | `ALL_RED_CYCLES` | `NS_GREEN` |

* **Invalid States (`3'b110`, `3'b111`):** Default recovery transitions immediately to `ALL_RED_TO_NS` with both outputs forced to `RED` (`3'b100`).
  
## 7. Design approach

The design uses a Moore FSM with six states. Outputs depend only on the current state, avoiding output glitches caused by changes to the counter. A synchronous counter records elapsed cycles in the active state. When that counter reaches the duration for the current phase, the FSM moves to the next state and clears the counter. Reset is evaluated only at a rising clock edge, consistent with the single-clock synchronous architecture.

| State | NS output | EW output | Exit condition |
|---|---|---|---|
| `NS_GREEN` | Green | Red | `GREEN_TIME` cycles elapsed |
| `NS_YELLOW` | Yellow | Red | `YELLOW_TIME` cycles elapsed |
| `ALL_RED_1` | Red | Red | `ALL_RED_TIME` cycles elapsed |
| `EW_GREEN` | Red | Green | `GREEN_TIME` cycles elapsed |
| `EW_YELLOW` | Red | Yellow | `YELLOW_TIME` cycles elapsed |
| `ALL_RED_2` | Red | Red | `ALL_RED_TIME` cycles elapsed |

The next-state path is strictly circular, which makes normal operation deterministic and straightforward to verify.

## 8. Timing assumptions

- All time values are expressed in **clock cycles**, not seconds.
- The external system is responsible for selecting a clock frequency and converting real-world seconds to parameter values. For example, with a 1 Hz clock, `GREEN_TIME = 30` means a 30-second green phase.
- `GREEN_TIME`, `YELLOW_TIME`, and `ALL_RED_TIME` must be positive integers.
- Version 1 gives NS and EW equal green durations. Independent `NS_GREEN_TIME` and `EW_GREEN_TIME` parameters may be introduced later if the junction needs unequal timings.

## 9. Verification acceptance criteria

The testbench must demonstrate all of the following:

1. Reset initializes NS to green and EW to red.
2. Each state appears in the required order.
3. Each state remains active for its configured number of clock cycles.
4. Both outputs are red during both clearance states.
5. No sampled clock cycle has green on both NS and EW.
6. The FSM repeats from `ALL_RED_2` back to `NS_GREEN`.

## 10. Future enhancement path

Future revisions can add request inputs and additional states while preserving the safety rule that conflicting flows are never permitted together. Suitable next additions are pedestrian phases, sensor-triggered green extensions, independent NS/EW green durations, and an emergency all-red override.


<details>
<summary><b>📁 [01]-Verilog-Basics</b></summary>

<br>

| Topic / Note | File Path |
| :--- | :--- |
| **What is HDL?** | [`What-is-HDL.md`](./[01]-Verilog-Basics/What-is-HDL.md) |
| **HDL vs Software** | [`HDL-vs-Software.md`](./[01]-Verilog-Basics/HDL-vs-Software.md) |
| **Introduction to Verilog** | [`Introduction-to-Verilog.md`](./[01]-Verilog-Basics/Introduction-to-Verilog.md) |
| **Module Structure** | [`Module-Structure.md`](./[01]-Verilog-Basics/Module-Structure.md) |
| **Port Declaration** | [`Port-Declaration.md`](./[01]-Verilog-Basics/Port-Declaration.md) |
| **Data Types (`wire` vs `reg`)** | [`Data-Types-wire-vs-reg.md`](./[01]-Verilog-Basics/Data-Types-wire-vs-reg.md) |
| **Integer, Real & Time** | [`Integer-Real-Time.md`](./[01]-Verilog-Basics/Integer-Real-Time.md) |
| **Number Representation** | [`Number-Representation.md`](./[01]-Verilog-Basics/Number-Representation.md) |
| **Operators in Verilog** | [`Operators-in-Verilog.md`](./[01]-Verilog-Basics/Operators-in-Verilog.md) |
| **Operator Precedence** | [`Operator-Precedence.md`](./[01]-Verilog-Basics/Operator-Precedence.md) |
| **Parameters** | [`Parameters.md`](./[01]-Verilog-Basics/Parameters.md) |
| **`localparam`** | [`localparam.md`](./[01]-Verilog-Basics/localparam.md) |

</details>
## 11. Related Engineering Documentation


- [FSM Specification](./fsm-specification.md)
- [Verification Summary](./verification-summary.md)
- [Design Decisions & Trade-offs](./design-decisions.md)
