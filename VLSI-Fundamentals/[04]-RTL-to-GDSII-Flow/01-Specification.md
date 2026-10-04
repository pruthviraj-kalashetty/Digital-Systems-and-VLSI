# **Specification**

* **Overview**

Specification is the first major step in the VLSI design process. It defines **what the chip or hardware block must do**, including its functionality, interfaces, performance requirements, operating conditions, and constraints. A clear specification provides the foundation for architecture, RTL design, verification, synthesis, and physical implementation.

---

* **Definition**

A specification is a detailed description of the **required functionality, behavior, interfaces, performance targets, and design constraints** of a hardware system or IP block.

It defines **what the design must achieve**, but generally does not describe the detailed RTL implementation.

---

* **Why is it needed?**

A specification is needed to create a common and unambiguous understanding of the design requirements.

It helps to:

- Define the required functionality.
- Identify inputs and outputs.
- Define interface behavior.
- Establish timing requirements.
- Define performance targets.
- Define reset behavior.
- Define operating conditions.
- Establish power and area requirements.
- Provide requirements for verification.
- Guide architecture and RTL development.
- Reduce ambiguity and design errors.

Without a clear specification, different engineers may interpret the same requirement differently.

---

* **Specification in the VLSI Design Flow**

A simplified design flow is:

```text id="specflow01"
System Requirement
       │
       ▼
 Specification
       │
       ▼
 Architecture
       │
       ▼
 Microarchitecture
       │
       ▼
 RTL Design
       │
       ▼
 Functional Verification
       │
       ▼
 Logic Synthesis
       │
       ▼
 Physical Design
       │
       ▼
 Signoff
       │
       ▼
 Tapeout
```

Specification is therefore the starting point for the detailed hardware design process.

---

* **What does a Specification contain?**

A hardware specification can contain several categories of requirements.

### **1. Functional Requirements**

Functional requirements define **what the hardware must do**.

For example, for a counter:

```text id="specflow02"
- Counter shall increment on every active clock edge.
- Counter shall reset to zero when reset is asserted.
- Counter shall wrap around after reaching its maximum value.
```

These requirements describe behavior rather than implementation.

---

### **2. Interface Requirements**

Interface requirements define how the block communicates with the outside world.

Example:

```text id="specflow03"
Inputs:
    clk
    reset
    enable

Output:
    count
```

The specification should define:

- Signal names
- Direction
- Width
- Meaning
- Active level
- Timing relationship
- Valid conditions

---

### **3. Timing Requirements**

Timing requirements describe when signals must change and what timing performance is required.

Examples:

```text id="specflow04"
Clock Frequency : 100 MHz
Clock Period    : 10 ns
Reset Type      : Synchronous
```

Other timing requirements may include:

- Setup requirements
- Hold requirements
- Latency
- Throughput
- Clock relationships

---

### **4. Performance Requirements**

Performance requirements describe how efficiently the hardware should operate.

Examples:

- Maximum operating frequency
- Required throughput
- Maximum latency
- Processing rate
- Response time

For example:

```text id="specflow05"
Required Frequency : ≥ 500 MHz
Maximum Latency    : 4 Clock Cycles
```

---

### **5. Reset Requirements**

The specification should clearly define reset behavior.

Important details include:

- Synchronous or asynchronous reset
- Active-high or active-low
- Initial state
- Which registers are reset
- Required behavior after reset release

Example:

```text id="specflow06"
Reset Type   : Synchronous
Reset Level  : Active High
Reset State  : IDLE
```

---

### **6. Power Requirements**

Power requirements define limits or targets related to power consumption.

Examples:

- Maximum dynamic power
- Leakage power target
- Clock power requirements
- Low-power operating modes

Power requirements become increasingly important in battery-powered and high-performance systems.

---

### **7. Area Requirements**

Area requirements define constraints on the amount of silicon that the design should occupy.

For example:

```text id="specflow07"
Maximum Area : 0.50 mm²
```

The actual area depends on the technology and implementation.

---

### **8. Operating Conditions**

The specification may define the expected operating environment.

Examples:

- Supply voltage
- Operating frequency
- Temperature range
- Process conditions
- Required operating modes

These requirements can later be used by synthesis, timing analysis, and physical design.

---

* **Inputs and Outputs**

A specification should clearly identify the external interface.

Example for a simple register block:

```text id="specflow08"
                +----------------------+
                |      Register        |
                |       Block          |
                |                      |
      clk ----->|                      |
    reset ----->|                      |
     write ---->|                      |
      data ---->|                      |
                |                      |-----> q
                +----------------------+
```

Example interface table:

| Signal | Direction | Width | Description |
|---|---|---:|---|
| `clk` | Input | 1 | System clock |
| `reset` | Input | 1 | Reset signal |
| `write` | Input | 1 | Write control |
| `data` | Input | 8 | Input data |
| `q` | Output | 8 | Stored data |

---

* **Functional Specification vs Implementation**

A specification should describe **what the hardware must do**, not unnecessarily dictate how it must be implemented.

For example:

**Specification:**

```text
The counter shall increment by one on each enabled clock cycle.
```

**Implementation:**

```verilog
always @(posedge clk)
begin
    if (enable)
        count <= count + 1'b1;
end
```

The first describes the required behavior.

The second describes one RTL implementation.

Therefore:

> **Specification defines WHAT. RTL defines HOW.**

---

* **Specification Example**

Consider a simple 4-bit counter.

### **Functional Requirements**

```text id="specflow09"
1. The counter shall be 4 bits wide.
2. The counter shall increment when enable is high.
3. The counter shall retain its value when enable is low.
4. Reset shall clear the counter to zero.
5. The counter shall operate synchronously with the clock.
6. The counter shall wrap from 15 to 0.
```

### **Interface**

| Signal | Direction | Width | Description |
|---|---|---:|---|
| `clk` | Input | 1 | Clock |
| `reset` | Input | 1 | Active-high synchronous reset |
| `enable` | Input | 1 | Enables counting |
| `count` | Output | 4 | Current counter value |

### **Behavior**

```text id="specflow10"
reset = 1
    │
    ▼
count = 0

reset = 0, enable = 1
    │
    ▼
count increments every clock

reset = 0, enable = 0
    │
    ▼
count holds its current value
```

### **Boundary Condition**

```text id="specflow11"
1111
  │
  │ + 1
  ▼
0000
```

This boundary behavior should be explicitly defined in the specification.

---

* **Specification and Verification**

The specification is also the foundation for functional verification.

The relationship is:

```text id="specflow12"
Specification
      │
      ├──────────────► RTL Design
      │
      └──────────────► Verification Plan
                              │
                              ▼
                           Testbench
                              │
                              ▼
                         Test Results
```

Every important requirement should ideally have a corresponding verification scenario.

For example:

| Requirement | Verification |
|---|---|
| Reset clears counter | Apply reset and check `count = 0` |
| Enable increments counter | Enable counting and check sequence |
| Disable holds value | Disable and check value remains unchanged |
| Counter wraps | Test transition from `1111` to `0000` |

This creates traceability between requirements and verification.

---

* **Specification and RTL Design**

The specification provides the requirements from which the RTL is developed.

```text id="specflow13"
Specification
      │
      ▼
Architecture
      │
      ▼
Microarchitecture
      │
      ▼
RTL
```

For an RTL Design Engineer, understanding the specification correctly is critical because an RTL implementation can be syntactically correct and synthesizable while still violating the actual specification.

---

* **Specification and PPA**

Specification can also contain high-level **Power, Performance, and Area (PPA)** targets.

```text id="specflow14"
              Specification
                    │
             ┌──────┼──────┐
             ▼      ▼      ▼
          Power  Performance Area
```

For example:

```text id="specflow15"
Frequency : ≥ 500 MHz
Power     : ≤ Target Value
Area      : ≤ Target Value
```

These requirements influence later architecture, RTL, synthesis, and physical design decisions.

---

* **Requirements Traceability**

Requirements traceability ensures that each requirement is addressed during design and verification.

Example:

```text id="specflow16"
Requirement
     │
     ├──► Architecture
     │
     ├──► RTL
     │
     └──► Verification Test
```

A requirement should not simply be written and forgotten.

It should be traceable through the design process.

---

* **Common Specification Mistakes**

### **1. Ambiguous Requirements**

Bad:

```text
The block should operate quickly.
```

Better:

```text
The block shall support a minimum operating frequency of 500 MHz.
```

---

### **2. Missing Reset Behavior**

If reset behavior is not defined, RTL designers and verification engineers may make different assumptions.

---

### **3. Missing Boundary Conditions**

For counters, FIFOs, buffers, and state machines, boundary behavior must be clearly specified.

---

### **4. Undefined Interface Behavior**

The specification should define what happens when:

- Inputs are invalid.
- Requests arrive while busy.
- Multiple control signals are asserted.
- Data is unavailable.
- A transaction is incomplete.

---

### **5. Conflicting Requirements**

Requirements should not contradict one another.

For example:

```text
Frequency ≥ 1 GHz
Area ≤ Very Small
Power ≤ Very Low
```

Such requirements may require architectural trade-offs and feasibility analysis.

---

### **6. Over-Specifying the Implementation**

A specification should generally define required behavior and constraints without unnecessarily forcing a particular RTL coding style.

---

* **Specification Document Structure**

A practical hardware specification can follow a structure such as:

```text id="specflow17"
01. Purpose
02. Scope
03. Functional Requirements
04. Interface Definition
05. Operating Modes
06. Timing Requirements
07. Reset Requirements
08. Performance Requirements
09. Power Requirements
10. Area Requirements
11. Error Handling
12. Boundary Conditions
13. Operating Conditions
14. Verification Requirements
15. Constraints and Assumptions
```

The exact structure depends on the project.

---

* **Specification for an RTL Project**

For an RTL mini-project, a simplified specification can be:

```text id="specflow18"
Project Name
     │
     ├── Purpose
     ├── Functional Requirements
     ├── Inputs
     ├── Outputs
     ├── Timing
     ├── Reset
     ├── Operating Conditions
     ├── Boundary Conditions
     └── Verification Requirements
```

This is especially useful before starting RTL coding.

---

* **Applications**

Specification is used for:

- ASIC design
- FPGA design
- RTL IP development
- CPU design
- GPU design
- SoC design
- Memory controllers
- UART/SPI/I2C controllers
- FIFOs
- DMA controllers
- Interrupt controllers
- Timers
- Communication interfaces
- AI accelerators
- Digital signal-processing hardware

---

* **Advantages**

- Provides a clear design target.
- Reduces ambiguity.
- Guides architecture development.
- Guides RTL implementation.
- Helps create verification plans.
- Improves communication between teams.
- Enables requirements traceability.
- Helps identify design constraints early.
- Reduces the risk of implementing incorrect functionality.

---

* **Limitations**

- A specification may change during development.
- Complex systems can have very large specifications.
- Ambiguous requirements can still exist if not reviewed carefully.
- Some performance and PPA requirements may require detailed feasibility analysis.
- A specification alone does not guarantee correct implementation.

---

* **Real-World Example**

Consider a UART controller.

A high-level specification may define:

```text id="specflow19"
Data Width       : 8 bits
Parity            : Optional / Defined by configuration
Stop Bits         : Defined by configuration
Clock             : System clock
Baud Rate         : Configurable
Reset             : Synchronous active-high
```

It can also define:

- Transmit behavior
- Receive behavior
- Busy indication
- Error conditions
- Start-bit detection
- Stop-bit handling
- Interface timing

The RTL designer then uses these requirements to develop the UART architecture and RTL.

The verification engineer uses the same requirements to create tests.

---

* **Key Points**

1. Specification is the starting point of detailed hardware design.
2. It defines **what the hardware must do**.
3. It should define functionality, interfaces, timing, reset, performance, and constraints.
4. Specification should clearly define boundary conditions.
5. Specification guides architecture and RTL development.
6. Specification is also the foundation for verification planning.
7. Requirements should be traceable to RTL and verification.
8. A synthesizable RTL design can still be wrong if it does not satisfy the specification.
9. High-level PPA targets may be included in the specification.
10. A good specification should be clear, measurable, consistent, and testable.
11. **Specification → Architecture → RTL → Verification → Synthesis → Physical Design** is a simplified design relationship.
12. For an RTL Design Engineer, reading and understanding specifications is a fundamental skill.

---

* **Interview Questions**

**1. What is a specification in VLSI design?**

A specification defines the required functionality, interfaces, timing, performance, operating conditions, and constraints of a hardware system or block.

**2. What is the difference between specification and RTL?**

Specification defines **what the hardware must do**, while RTL describes **how the required behavior is implemented as hardware**.

**3. Why is specification important?**

It provides a clear design target and guides architecture, RTL development, verification, synthesis, and later implementation stages.

**4. What are functional requirements?**

Functional requirements describe the required behavior and operations of the hardware.

**5. Why should boundary conditions be specified?**

Boundary conditions define behavior at limits or exceptional cases and prevent different teams from making different assumptions.

**6. What is requirements traceability?**

Requirements traceability is the process of connecting each requirement to the corresponding architecture, RTL implementation, and verification activity.

**7. Can RTL be correct but still fail the specification?**

Yes. RTL can compile, simulate in limited tests, and synthesize successfully while still implementing behavior that differs from the specification.

**8. What timing information can be included in a specification?**

Clock frequency, clock period, latency, throughput, timing relationships, and other required timing constraints.

**9. What is the role of specification in verification?**

Verification uses the specification to determine what scenarios must be tested and what results are expected.

**10. What makes a good hardware specification?**

It should be clear, unambiguous, measurable, consistent, complete enough for implementation, and testable.

**11. Who uses the specification?**

Different teams can use it, including architecture, RTL design, verification, synthesis, physical design, and system teams.

**12. Why should an RTL engineer understand specifications?**

Because RTL must implement the required behavior exactly. Misunderstanding the specification can result in functionally incorrect hardware even when the RTL code itself is syntactically valid.

---

* **Quick Revision**

```text id="specflow20"
Specification
     │
     ├── What should the hardware do?
     ├── What are the inputs and outputs?
     ├── What are the timing requirements?
     ├── What is the reset behavior?
     ├── What are the performance targets?
     ├── What are the power/area constraints?
     └── What conditions must be verified?
              │
              ▼
         Architecture
              │
              ▼
             RTL
              │
              ▼
         Verification
```

**Remember:**

> **Specification = WHAT**

> **Architecture = HOW the system is organized**

> **RTL = HOW the hardware behavior is described**

> **Verification = Does the implementation satisfy the specification?**

---

* **Summary**

Specification is the foundation of the VLSI design process. It defines the required **functionality, interfaces, timing, reset behavior, performance, operating conditions, and design constraints** before detailed implementation begins.

For an RTL Design Engineer, specification is especially important because RTL should be written from clearly understood requirements rather than assumptions. A strong RTL engineer should be able to read a specification, identify all required behaviors and boundary conditions, convert them into an architecture, and later verify that the RTL satisfies every requirement.

---

* **References**

- Neso Academy — VLSI Design and Digital Electronics concepts
- All About Electronics — Digital Design and VLSI concepts
- Neil H. E. Weste & David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- IEEE — Hardware and system design standards and practices
