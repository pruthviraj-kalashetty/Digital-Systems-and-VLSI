# **Input-to-Output Path**

* **Overview**

An input-to-output path is a timing path in which data travels directly from an input port to an output port through combinational logic.

Unlike a register-to-register path, this path does not contain a sequential element between the input and output.

* **Definition**

An **input-to-output path** is a timing path that starts at an input port and ends at an output port, with combinational logic between them.

The basic structure is:

    Input Port
        │
        ▼
    Combinational Logic
        │
        ▼
    Output Port

* **Why is it needed?**

Input-to-output paths are important when a design contains combinational logic that directly connects an external input to an external output.

STA analyzes these paths to determine:

- Input-to-output propagation delay
- Maximum path delay
- Minimum path delay
- Input and output timing requirements
- Timing slack
- Timing violations

These paths are common in combinational blocks and interface logic.

* **Core Concept**

A simple input-to-output path looks like:

          External Source
                │
                ▼
           Input Port
                │
                ▼
          ┌──────────┐
          │   AND    │
          └────┬─────┘
               │
               ▼
          ┌──────────┐
          │   MUX    │
          └────┬─────┘
               │
               ▼
          Output Port
                │
                ▼
          External Device

The input signal enters the design through the input port.

It passes through combinational logic.

The resulting signal appears at the output port.

* **Timing Diagram**

A simplified input-to-output timing relationship is:

    Input
    ────────┐
            │
            │
            ▼
        Input Arrives
            │
            │
            │ Combinational
            │ Logic Delay
            │<────────────>
            ▼
        Output Changes
            │
            ▼
        Output Port

The output cannot respond before the input signal propagates through the combinational logic.

* **Important Terms**

**Input Port**

The external entry point of the design.

**Output Port**

The external exit point of the design.

**Combinational Logic**

Logic that processes the input without storing data in a sequential element.

**Input Arrival Time**

The time at which the input data becomes available at the design input.

**Output Arrival Time**

The time at which the resulting data reaches the output port.

**Propagation Delay**

The delay from the input change to the corresponding output change.

**Input Delay**

The timing relationship describing when external data arrives at the input port.

**Output Delay**

The timing requirement describing when the output is expected to be available to the external environment.

* **Formula**

For a simplified combinational input-to-output path:

    Output Arrival Time
    =
    Input Arrival Time
    +
    Combinational Delay

For example:

    Input Arrival Time = 2 ns
    Logic Delay        = 5 ns

Therefore:

    Output Arrival Time
    = 2 + 5
    = 7 ns

For STA, input and output timing constraints are used to describe the external environment.

* **Simple Example**

Consider:

    Input Delay  = 2 ns
    AND Delay    = 2 ns
    MUX Delay    = 3 ns
    Output Requirement = 8 ns

Total combinational delay:

    Data Path Delay
    = 2 + 3
    = 5 ns

Output arrival time:

    Arrival Time
    = Input Delay + Data Path Delay
    = 2 + 5
    = 7 ns

If the output must be available by 8 ns:

    Slack
    = 8 - 7
    = +1 ns

The simplified timing requirement is satisfied.

* **STA Connection**

STA analyzes the complete path:

    Input Port
        │
        │ Input Arrival
        ▼
    Combinational Logic
        │
        │ Logic Delay
        ▼
    Output Port
        │
        │ Output Requirement
        ▼
    External Environment

Unlike a register-to-register path, there is no launch or capture flip-flop inside this path.

STA instead uses the input and output timing constraints to determine whether the input-to-output delay satisfies the external timing requirements.

* **RTL Relevance**

Input-to-output paths are created by combinational RTL.

For example:

    always @(*) begin
        y = (a & b) | c;
    end

Here:

    a, b, c → Input Ports
          │
          ▼
      AND / OR Logic
          │
          ▼
          y → Output Port

There is no register between the inputs and output.

The output therefore depends directly on the combinational logic delay.

* **Common Mistakes**

- Assuming every timing path contains registers.
- Treating an input port as a launch flip-flop.
- Treating an output port as a capture flip-flop.
- Ignoring input arrival time.
- Ignoring output timing requirements.
- Confusing propagation delay with clock-to-Q delay.
- Assuming RTL simulation alone verifies the external timing requirements.
- Forgetting that combinational paths can also have timing constraints.

* **Interview Questions**

**1. What is an input-to-output path?**

It is a timing path that starts at an input port and ends at an output port through combinational logic.

**2. Does an input-to-output path require flip-flops?**

No. It can be a completely combinational path.

**3. What determines the output arrival time?**

The input arrival time plus the delay through the combinational logic.

**4. What timing constraints are important for this path?**

Input-delay and output-delay constraints are commonly used to describe the external timing environment.

**5. How is it different from a register-to-register path?**

A register-to-register path has launch and capture registers, while an input-to-output path can have only input/output ports and combinational logic between them.

* **Quick Revision**

- Input-to-output = Input Port → Logic → Output Port.
- It can be completely combinational.
- No internal launch or capture register is required.
- Input arrival time affects output arrival.
- Combinational logic contributes to path delay.
- Input and output constraints describe the external timing environment.
- STA can analyze combinational input-to-output paths.

* **Summary**

An input-to-output path directly connects an input port to an output port through combinational logic. The output timing depends on when the input arrives and how long the combinational logic takes to process it. Unlike register-to-register paths, this path does not require internal launch and capture registers. STA uses input and output timing constraints to verify whether the path satisfies its required timing.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
