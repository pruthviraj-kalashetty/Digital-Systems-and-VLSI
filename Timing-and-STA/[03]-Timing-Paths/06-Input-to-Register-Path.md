# **Input-to-Register Path**

* **Overview**

An input-to-register path is a timing path in which data starts from an external input port of the design and ends at the input of a register.

It is an important timing path in STA because external input data must arrive at the register within the required timing window.

* **Definition**

An **input-to-register path** is a timing path that starts at an input port and ends at the D input of a sequential element, usually a flip-flop.

The basic structure is:

    Input Port
        │
        ▼
    Combinational Logic
        │
        ▼
    Register
        │
        D

* **Why is it needed?**

STA analyzes input-to-register paths to verify that externally provided data reaches the register at the correct time.

It helps check:

- Input data arrival time
- Setup timing
- Hold timing
- Input delay constraints
- Timing slack
- Timing violations

This path is especially important when a design communicates with another chip, module, or external interface.

* **Core Concept**

A simple input-to-register path looks like:

              External Source
                    │
                    │ Data
                    ▼
              ┌──────────┐
              │ Input    │
              │   Port   │
              └────┬─────┘
                   │
                   ▼
             ┌───────────┐
             │Combinational│
             │   Logic   │
             └─────┬─────┘
                   │
                   ▼
               ┌───────┐
    Clock ────► │  FF   │
               │       │
               └───────┘
                   ▲
                   │
                   D

The external source provides the data.

The data travels through the input logic.

The register captures the data on the active clock edge.

* **Timing Diagram**

A simplified input-to-register timing relationship is:

    External Data
    ────────────────┐
                    │
                    │ Input Delay
                    │<────────────>
                    ▼
                 Data Arrives
                    │
                    │ Combinational
                    │ Logic Delay
                    ▼
                 FF D Input
                                      Capture Edge
                                            │
                                            ▼
    Clock ──────────────────────────────────┼──────

The data must arrive at the register early enough to satisfy its setup requirement.

* **Important Terms**

**Input Port**

The external input boundary of the design.

**Input Delay**

The amount of time required for data to travel from the external source to the design input relative to the reference clock.

**Combinational Logic**

Logic between the input port and the destination register.

**Capture Register**

The register that receives and captures the input data.

**Capture Clock**

The clock used by the destination register to capture the incoming data.

**Setup Time**

The minimum time for which the data must be stable before the capture clock edge.

**Hold Time**

The minimum time for which the data must remain stable after the capture clock edge.

**Input-to-Register Path**

    Input Port → Logic → Register

* **Formula**

For a simplified setup check:

    tINPUT + tDATA + tSETUP
    ≤
    TCLK

Where:

- `tINPUT` = external/input arrival delay
- `tDATA` = combinational data-path delay
- `tSETUP` = setup time of the capture register
- `TCLK` = clock period

A simplified setup slack can be expressed as:

    Setup Slack
    = Required Time - Arrival Time

In real STA, the input arrival time is normally defined using an input-delay constraint.

* **Simple Example**

Assume:

    Clock Period       = 10 ns
    Input Delay        = 2 ns
    Logic Delay        = 5 ns
    Setup Time         = 1 ns

Data arrival at the register:

    Arrival Time
    = Input Delay + Logic Delay
    = 2 + 5
    = 7 ns

Latest allowed arrival:

    Required Time
    = 10 - 1
    = 9 ns

Therefore:

    Setup Slack
    = 9 - 7
    = +2 ns

The simplified input-to-register path satisfies the setup requirement.

* **STA Connection**

STA needs to know when the external data is expected to arrive at the input port.

This is normally described using an input-delay constraint.

A simplified view is:

    External Source
          │
          ▼
       Input Port
          │
          │ Input Delay
          ▼
    Combinational Logic
          │
          │ Data Delay
          ▼
       Capture FF
          ▲
          │
       Clock Path
          │
       Clock Source

STA uses the input delay and internal path delay to calculate the data arrival time at the capture register.

The timing analysis then checks the arrival time against the required capture time.

* **RTL Relevance**

Input-to-register paths are commonly created when external signals are sampled into registers.

For example:

    always @(posedge clk) begin
        data_reg <= data_in;
    end

Here:

    data_in  → Input Port
    data_reg → Capture Register

If combinational logic exists between them:

    data_in
       │
       ▼
    Logic
       │
       ▼
    data_reg

the logic becomes part of the input-to-register data path.

At the RTL level, designers should understand that external inputs do not automatically arrive at the register at the clock edge. Their timing relative to the clock must be defined and analyzed.

* **Common Mistakes**

- Assuming an input signal always arrives exactly at the clock edge.
- Ignoring input-delay constraints.
- Forgetting the setup time of the capture register.
- Confusing input delay with internal combinational delay.
- Treating the input port as a launch flip-flop.
- Forgetting that external devices can determine when input data becomes available.
- Assuming RTL simulation alone verifies the external timing relationship.

* **Interview Questions**

**1. What is an input-to-register path?**

It is a timing path from an input port to the D input of a register.

**2. What is the basic structure of an input-to-register path?**

    Input Port → Combinational Logic → Capture Register

**3. Why is input delay important?**

Input delay describes when external data is expected to arrive at the design input relative to the reference clock. STA uses it to calculate the data arrival time.

**4. Is an input port a launch element?**

No. An input port is not normally a sequential launch element. The external source or device provides the data, and the input-delay constraint models its timing relationship.

**5. Which timing requirement is especially important at the destination register?**

The destination register must satisfy its setup and hold requirements.

* **Quick Revision**

- Input-to-register path = Input Port → Logic → Register.
- Input data comes from an external source.
- Input delay describes external data arrival.
- The destination register is the capture element.
- Setup and hold requirements must be satisfied.
- Input-delay constraints are important in STA.
- STA analyzes the external arrival time plus internal path delay.

* **Summary**

An input-to-register path carries data from an external input port to a register inside the design. STA uses input-delay constraints and internal data-path delays to determine when the data reaches the capture register. The register must receive the data within the required setup and hold timing window. Understanding input-to-register paths is important for analyzing the timing interface between an external source and an ASIC design.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
