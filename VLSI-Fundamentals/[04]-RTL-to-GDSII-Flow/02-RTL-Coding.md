# **RTL Coding**

* **Overview**

RTL Coding is the process of describing the required digital hardware behavior at the **Register Transfer Level (RTL)** using a Hardware Description Language (HDL) such as Verilog or SystemVerilog. RTL code describes registers, combinational logic, control logic, data paths, and the transfer of data between registers.

---

* **Definition**

RTL Coding is the process of converting a hardware architecture or microarchitecture into **synthesizable HDL code** that represents how data is stored, processed, and transferred between registers under clock and control signals.

For an RTL Design Engineer, RTL coding is one of the most important skills because the RTL becomes the primary input to functional verification and logic synthesis.

---

* **Why is it needed?**

RTL Coding is needed to translate the hardware requirements and architecture into a precise digital hardware description.

It helps to:

- Describe sequential and combinational hardware.
- Define data movement between registers.
- Implement control logic and FSMs.
- Implement datapaths.
- Create synthesizable hardware.
- Enable functional simulation.
- Provide input to logic synthesis.
- Support ASIC and FPGA implementation.
- Make hardware behavior easier to verify and maintain.

The goal is not simply to write code that compiles. The goal is to describe **correct and synthesizable hardware**.

---

* **RTL in the VLSI Design Flow**

```text
Specification
      │
      ▼
Architecture
      │
      ▼
Microarchitecture
      │
      ▼
RTL Coding
      │
      ▼
Functional Verification
      │
      ▼
Logic Synthesis
      │
      ▼
Gate-Level Netlist
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

RTL Coding connects the architectural description of the hardware to the implementation and verification stages.

---

* **Basic RTL Concept**

The fundamental RTL concept is:

```text
Register → Combinational Logic → Register
                │
                ▼
          Data Processing
```

Example:

```text
        +-------------+
        | Register A  |
        +------+------+
               |
               ▼
       +---------------+
       | Combinational |
       |     Logic     |
       +-------+-------+
               |
               ▼
        +-------------+
        | Register B  |
        +-------------+
```

At a clock edge, Register B captures the result produced by the combinational logic.

---

* **Main Components of RTL**

RTL generally consists of:

### **1. Sequential Logic**

Sequential logic stores information and normally changes state according to a clock.

Common elements:

- Flip-flops
- Registers
- Counters
- Shift registers
- State registers

Example:

```verilog
always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

This describes a register that captures `d` on the active clock edge.

---

### **2. Combinational Logic**

Combinational logic produces outputs based on current inputs.

Common examples:

- AND
- OR
- XOR
- Multiplexer
- Decoder
- Comparator
- Adder
- Subtractor

Example:

```verilog
always @(*)
begin
    if (sel)
        y = b;
    else
        y = a;
end
```

This describes a 2-to-1 multiplexer.

---

### **3. Control Logic**

Control logic determines how the datapath operates.

Examples:

- Enable signals
- Valid signals
- Ready signals
- FSMs
- Control flags
- Write/read controls

---

### **4. Datapath**

The datapath performs data processing operations.

Typical components include:

```text
Registers
   │
   ├──► Adder
   ├──► Subtractor
   ├──► Comparator
   ├──► Shifter
   ├──► Multiplier
   └──► Multiplexer
```

---

* **RTL Coding Styles**

A common Verilog RTL organization uses separate sequential and combinational blocks.

### **Sequential Block**

```verilog
always @(posedge clk)
begin
    if (reset)
        state <= IDLE;
    else
        state <= next_state;
end
```

### **Combinational Block**

```verilog
always @(*)
begin
    next_state = state;

    case (state)
        IDLE:
            if (start)
                next_state = RUN;

        RUN:
            if (done)
                next_state = IDLE;

        default:
            next_state = IDLE;
    endcase
end
```

This separation makes the intended hardware structure easier to understand and verify.

---

* **Blocking and Nonblocking Assignments**

### **Blocking Assignment**

```verilog
=
```

Blocking assignments are commonly used in combinational procedural logic.

Example:

```verilog
always @(*)
begin
    y = a & b;
end
```

### **Nonblocking Assignment**

```verilog
<=
```

Nonblocking assignments are commonly used in clocked sequential logic.

Example:

```verilog
always @(posedge clk)
begin
    q <= d;
end
```

A simple rule for the user's Verilog-2001 RTL style is:

```text
Combinational Logic → =
Sequential Logic    → <=
```

---

* **RTL Registers**

A register stores data across clock cycles.

Example:

```verilog
module register (
    input clk,
    input reset,
    input d,
    output reg q
);

always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end

endmodule
```

Conceptually:

```text
          d
          │
          ▼
      +-------+
clk → |  FF   | → q
      +-------+
          ▲
        reset
```

The register changes its stored value at the active clock edge.

---

* **Combinational RTL Example**

A simple 2-to-1 multiplexer:

```verilog
module mux2to1 (
    input a,
    input b,
    input sel,
    output reg y
);

always @(*)
begin
    if (sel)
        y = b;
    else
        y = a;
end

endmodule
```

Behavior:

```text
sel = 0 → y = a
sel = 1 → y = b
```

The multiplexer does not store data.

---

* **RTL Coding for FSMs**

Finite State Machines are commonly implemented using RTL.

A typical three-block FSM structure contains:

```text
1. State Register
2. Next-State Logic
3. Output Logic
```

```text
             +----------------+
             | State Register |
             +-------+--------+
                     |
                  state
                     |
                     ▼
             +---------------+
             | Next-State    |
             | Logic         |
             +-------+-------+
                     |
                 next_state
                     |
                     ▼
             State Register
```

Example:

```verilog
always @(posedge clk)
begin
    if (reset)
        state <= IDLE;
    else
        state <= next_state;
end

always @(*)
begin
    next_state = state;

    case (state)
        IDLE:
            if (start)
                next_state = RUN;

        RUN:
            if (done)
                next_state = IDLE;

        default:
            next_state = IDLE;
    endcase
end
```

FSMs are widely used for controllers, protocols, traffic lights, communication interfaces, and control units.

---

* **RTL Coding for Counters**

Example:

```verilog
module counter (
    input clk,
    input reset,
    input enable,
    output reg [3:0] count
);

always @(posedge clk)
begin
    if (reset)
        count <= 4'b0000;
    else if (enable)
        count <= count + 1'b1;
end

endmodule
```

Behavior:

```text
reset = 1 → count = 0

reset = 0, enable = 1
        → count increments

reset = 0, enable = 0
        → count holds
```

---

* **RTL Coding for Datapath**

A datapath may contain multiple arithmetic and logical operations.

```text
             +-------------+
             |   Register  |
             +------+------+
                    |
                    ▼
             +-------------+
             |     ALU     |
             +------+------+
                    |
                    ▼
             +-------------+
             |   Register  |
             +-------------+
```

An ALU may perform:

- Addition
- Subtraction
- AND
- OR
- XOR
- Comparison
- Shifting

The control logic determines which operation is selected.

---

* **RTL Coding for Control and Datapath**

Many processors and complex digital systems can be conceptually divided into:

```text
             Control Path
                  │
                  │ Control Signals
                  ▼
             +---------+
             | Datapath|
             +---------+
                  │
                  ▼
              Data Output
```

**Control path** determines what should happen.

**Datapath** performs the actual data operation.

This separation is important when designing CPUs, controllers, communication blocks, and accelerators.

---

* **Parameters in RTL**

Parameters can make RTL reusable.

Example:

```verilog
module counter #(
    parameter WIDTH = 8
)(
    input clk,
    input reset,
    input enable,
    output reg [WIDTH-1:0] count
);

always @(posedge clk)
begin
    if (reset)
        count <= {WIDTH{1'b0}};
    else if (enable)
        count <= count + 1'b1;
end

endmodule
```

The same module can be configured for different counter widths.

For example:

```text
WIDTH = 4  → 4-bit counter
WIDTH = 8  → 8-bit counter
WIDTH = 16 → 16-bit counter
```

---

* **Synthesizable RTL**

Synthesizable RTL contains constructs that synthesis tools can convert into actual hardware.

Common synthesizable constructs include:

- `always @(posedge clk)`
- `always @(*)`
- `if`
- `else`
- `case`
- `for` loops with bounded/static behavior
- Arithmetic operations
- Comparisons
- Registers
- Combinational logic
- Parameters
- Module instantiation

Example:

```verilog
always @(posedge clk)
begin
    if (enable)
        q <= d;
end
```

This can synthesize into sequential hardware.

---

* **Non-Synthesizable Constructs**

Some Verilog constructs are mainly intended for simulation and verification.

Examples include:

```verilog
#10
$display(...)
$monitor(...)
```

These constructs do not normally represent synthesizable hardware in standard RTL design.

For example:

```verilog
#10 q = d;
```

The `#10` represents simulation time delay rather than a physical RTL timing structure.

---

* **Avoiding Latches**

Incomplete combinational assignments can unintentionally infer a latch.

Problematic example:

```verilog
always @(*)
begin
    if (enable)
        y = a;
end
```

When `enable = 0`, `y` has no assignment.

A safer combinational structure is:

```verilog
always @(*)
begin
    y = 1'b0;

    if (enable)
        y = a;
end
```

The default assignment ensures that `y` receives a value for every possible condition.

For combinational RTL:

> **Every output should have a defined value for every relevant input condition.**

---

* **Case Statements**

`case` statements are commonly used for multiplexing and FSM logic.

Example:

```verilog
always @(*)
begin
    case (sel)
        2'b00: y = a;
        2'b01: y = b;
        2'b10: y = c;
        2'b11: y = d;
        default: y = 1'b0;
    endcase
end
```

A `default` branch is useful for defining behavior for unexpected or uncovered conditions.

---

* **Reset Coding**

Reset behavior must follow the specification.

Example of synchronous active-high reset:

```verilog
always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

Example of asynchronous active-high reset:

```verilog
always @(posedge clk or posedge reset)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

These are different hardware behaviors.

Therefore:

> **Never choose reset style based only on coding preference. Follow the specification.**

---

* **RTL Coding and Timing**

RTL code describes logic whose physical implementation has timing behavior.

A simplified register-to-register path is:

```text
Launch Register
      │
      ▼
Combinational Logic
      │
      ▼
Capture Register
```

The clock period must provide enough time for data to travel through the path.

A simplified setup relationship is:

```text
Clock Period ≥
Clock-to-Q Delay
+ Combinational Delay
+ Setup Time
+ Timing Margin
```

RTL coding decisions can affect the amount of combinational logic and therefore influence timing.

---

* **RTL Coding and PPA**

RTL can influence:

```text
        RTL
         │
    ┌────┼────┐
    ▼    ▼    ▼
 Power Performance Area
```

Examples:

- Deep combinational logic can affect timing.
- Unnecessary registers can increase area and power.
- Large switching activity can increase dynamic power.
- Poorly structured logic can increase hardware resources.
- Excessive fanout can create timing and implementation challenges.

Therefore, good RTL should consider **Power, Performance, and Area (PPA)**.

---

* **RTL Coding and Verification**

RTL coding and verification work together:

```text
             Specification
                   │
                   ▼
               RTL Coding
                   │
                   ▼
             Testbench
                   │
                   ▼
               Simulation
                   │
                   ▼
             Waveform / Checks
                   │
             ┌─────┴─────┐
             ▼           ▼
           Pass          Fail
                         │
                         ▼
                       Debug
                         │
                         ▼
                      RTL Fix
```

RTL should be written so that its behavior can be clearly verified.

---

* **RTL Coding Example**

Consider a simple register with enable.

### **Requirement**

```text
- Store input data on the rising clock edge.
- Clear the register when reset is asserted.
- Update the register only when enable is high.
- Hold the previous value when enable is low.
```

### **RTL**

```verilog
module register_enable (
    input clk,
    input reset,
    input enable,
    input [7:0] d,
    output reg [7:0] q
);

always @(posedge clk)
begin
    if (reset)
        q <= 8'b00000000;
    else if (enable)
        q <= d;
end

endmodule
```

### **Behavior**

```text
reset = 1
    → q = 0

reset = 0, enable = 1
    → q captures d

reset = 0, enable = 0
    → q holds previous value
```

This demonstrates how a specification is converted into synthesizable RTL.

---

* **RTL Coding Best Practices**

1. Follow the specification exactly.
2. Use clear and meaningful signal names.
3. Separate combinational and sequential logic appropriately.
4. Use nonblocking assignments for clocked sequential logic.
5. Use blocking assignments for combinational procedural logic.
6. Provide complete combinational assignments.
7. Define reset behavior clearly.
8. Avoid unintended latches.
9. Handle default FSM states.
10. Keep RTL simple and readable.
11. Parameterize reusable modules where appropriate.
12. Avoid unnecessary logic and registers.
13. Consider timing, power, and area.
14. Verify boundary conditions.
15. Simulate RTL before synthesis.
16. Use synthesizable constructs for design RTL.
17. Avoid unnecessary vendor-specific constructs when portability is required.

---

* **Common RTL Coding Mistakes**

### **1. Using blocking assignment in sequential logic**

```verilog
always @(posedge clk)
    q = d;
```

For standard sequential RTL style, use:

```verilog
always @(posedge clk)
    q <= d;
```

---

### **2. Incomplete combinational assignment**

```verilog
always @(*)
begin
    if (sel)
        y = a;
end
```

This can infer a latch.

---

### **3. Missing default FSM behavior**

Not handling unexpected state values can make recovery behavior unclear.

---

### **4. Incorrect reset implementation**

Using asynchronous reset when the specification requires synchronous reset changes the hardware behavior.

---

### **5. Width mismatch**

For example:

```verilog
reg [3:0] a;
reg [7:0] b;

assign b = a;
```

The designer must understand how widths are extended and whether the result matches the intended hardware.

---

### **6. Unsigned/signed interpretation errors**

Arithmetic behavior can change depending on how values are interpreted.

---

### **7. Unintended multiple drivers**

A signal should not normally be driven by multiple procedural blocks unless the design explicitly requires a supported structure.

---

### **8. Writing software-style code**

RTL is not software.

For example, a loop in RTL generally represents replicated or repeated hardware structure rather than software execution over time.

---

* **Applications**

RTL Coding is used to design:

- CPUs
- GPUs
- Microcontrollers
- SoCs
- AI accelerators
- DSP blocks
- UART
- SPI
- I2C
- FIFOs
- Timers
- Counters
- Interrupt controllers
- DMA controllers
- Memory controllers
- Bus interfaces
- FSM-based controllers
- FPGA designs
- ASIC designs

---

* **Advantages**

- Provides a structured way to describe digital hardware.
- Supports simulation before fabrication.
- Enables automated synthesis.
- Can be reused across designs.
- Supports hierarchical design.
- Makes complex digital systems manageable.
- Allows verification before physical implementation.
- Can target ASIC and FPGA technologies.
- Enables hardware optimization for PPA.

---

* **Limitations**

- RTL does not directly describe transistor-level implementation.
- Final timing and physical behavior depend on synthesis and physical implementation.
- Poor RTL coding can lead to inefficient hardware.
- Complex RTL can be difficult to verify.
- HDL syntax can look similar to software while representing hardware.
- Technology-specific optimization may reduce portability.

---

* **Real-World Example**

A UART transmitter can be implemented using RTL components such as:

```text
             +----------------+
             | Control FSM    |
             +-------+--------+
                     |
                     ▼
             +----------------+
             | Baud Counter   |
             +-------+--------+
                     |
                     ▼
             +----------------+
             | Shift Register |
             +-------+--------+
                     |
                     ▼
                  TX Output
```

The RTL defines:

- Transmit states.
- Baud-rate timing.
- Data shifting.
- Start bit.
- Data bits.
- Stop bit.
- Transmission control.

The same RTL can then be simulated and synthesized for an appropriate target technology.

---

* **Key Points**

1. RTL Coding describes hardware at the Register Transfer Level.
2. RTL is written using HDLs such as Verilog or SystemVerilog.
3. RTL describes registers, combinational logic, control logic, and datapaths.
4. RTL should be synthesizable for implementation.
5. Sequential logic is generally described using clocked procedural blocks.
6. Combinational logic is generally described using combinational procedural blocks or continuous assignments.
7. Use `<=` for clocked sequential logic.
8. Use `=` for combinational procedural logic.
9. Incomplete combinational assignments can infer latches.
10. Reset behavior must follow the specification.
11. FSMs are common RTL control structures.
12. RTL coding affects timing, power, and area.
13. RTL must be functionally verified before implementation.
14. RTL is hardware description, not conventional software programming.
15. Good RTL should be **correct, synthesizable, readable, maintainable, and verification-friendly**.

---

* **Interview Questions**

**1. What is RTL?**

RTL stands for Register Transfer Level. It describes how data moves between registers through combinational logic under clock and control signals.

**2. What is RTL Coding?**

RTL Coding is the process of describing a hardware architecture using synthesizable HDL code.

**3. What is the difference between RTL and software code?**

RTL code describes hardware structure and behavior that can be synthesized into physical hardware, whereas software code describes instructions executed by a processor.

**4. What is sequential logic?**

Sequential logic stores information and its output depends on stored state and current inputs.

**5. What is combinational logic?**

Combinational logic produces outputs based on current input values without storing state.

**6. Why is `<=` commonly used in sequential logic?**

Nonblocking assignment models simultaneous updates of sequential elements at a clock event and avoids many simulation-ordering problems.

**7. Why is `=` commonly used in combinational procedural logic?**

Blocking assignment allows statements to execute in procedural order, which is useful for describing combinational calculations.

**8. What is an inferred latch?**

An inferred latch is storage hardware unintentionally created when combinational RTL does not assign an output for every relevant condition.

**9. How can unintended latches be avoided?**

Provide complete assignments for combinational outputs, often by assigning default values before conditional logic.

**10. What is synthesizable RTL?**

Synthesizable RTL uses HDL constructs that synthesis tools can convert into actual hardware.

**11. What is the purpose of an FSM in RTL?**

An FSM implements control behavior that changes between defined states based on inputs and conditions.

**12. How does RTL affect timing?**

RTL determines the logical structure and depth of combinational paths, which can influence the resulting hardware delay and timing.

**13. How does RTL affect PPA?**

Different RTL structures can synthesize into different hardware resources, affecting power, performance, and area.

**14. What is the difference between simulation and synthesis?**

Simulation evaluates the described behavior, while synthesis converts synthesizable RTL into a hardware representation such as a gate-level netlist.

**15. Can RTL compile successfully but still be wrong?**

Yes. Compilation only checks whether the code is syntactically and structurally acceptable to the tool. Functional verification is required to determine whether the design satisfies the specification.

---

* **Quick Revision**

```text
Specification
      │
      ▼
Architecture
      │
      ▼
RTL Coding
      │
      ├── Sequential Logic
      ├── Combinational Logic
      ├── Control Logic
      └── Datapath
      │
      ▼
Functional Verification
      │
      ▼
Synthesis
      │
      ▼
Gate-Level Hardware
```

**Remember:**

> **Specification → WHAT**

> **Architecture → HOW the system is organized**

> **RTL → HOW the hardware behavior is described**

> **Synthesis → HOW RTL becomes hardware cells**

---

* **Summary**

RTL Coding is the process of translating a hardware architecture into synthesizable HDL that describes registers, combinational logic, control logic, datapaths, and data transfers. It is a central activity for an RTL Design Engineer and forms the bridge between architecture, functional verification, synthesis, and physical implementation.

Good RTL coding is not simply about writing syntactically correct Verilog. It requires understanding **hardware behavior, clocking, reset, state, combinational paths, synthesizability, verification, and PPA**.

---

* **References**

- Neso Academy — Digital Electronics, Verilog and VLSI concepts
- All About Electronics — Digital Design and HDL concepts
- Samir Palnitkar — *Verilog HDL: A Guide to Digital Design and Synthesis*
- Michael D. Ciletti — *Advanced Digital Design with the Verilog HDL*
- Neil H. E. Weste & David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
