# **Data Path**

* **Overview**

A data path is the part of a timing path through which data travels from the launch element to the capture element.

It mainly contains combinational logic and the interconnect between registers. The delay of the data path directly affects setup and hold timing.

* **Definition**

The **data path** is the signal path that carries data from the output of a launch element to the input of a capture element.

A basic register-to-register data path is:

    Launch FF
        │
        │ Q
        ▼
    ┌──────────────┐
    │ Combinational│
    │    Logic     │
    └──────┬───────┘
           │
           ▼
      Capture FF
           │
           │ D

* **Why is it needed?**

The data path determines how long the launched data takes to reach the capture element.

STA analyzes the data path to determine:

- Data arrival time
- Maximum data-path delay
- Minimum data-path delay
- Setup timing
- Hold timing
- Timing slack
- Critical paths

A longer data path generally makes setup timing more difficult.

A very short data path can make hold timing more difficult.

* **Core Concept**

A practical data path can contain several types of logic:

    Launch FF
        │
        ▼
    ┌─────────┐
    │   AND   │
    └────┬────┘
         │
         ▼
    ┌─────────┐
    │   MUX   │
    └────┬────┘
         │
         ▼
    ┌─────────┐
    │   OR    │
    └────┬────┘
         │
         ▼
     Capture FF

The complete delay of the data path depends on the delays of the logic cells and interconnect.

For example:

    Data Path Delay
       ≈
    AND Delay
    + MUX Delay
    + OR Delay
    + Interconnect Delay

* **Timing Diagram**

A simplified data-path timing relationship is:

    Launch Clock Edge
           │
           ▼
    ───────┼──────────────────────────────────
           │
           │ Clock-to-Q
           │<───────>
           ▼
        Data Changes
           │
           │
           │ Data Path Delay
           │<────────────────>
           │
           ▼
      Data Arrives
                              Capture Clock Edge
                                      │
                                      ▼
    ──────────────────────────────────┼────────

The data path must deliver the data within the available timing window.

* **Important Terms**

**Launch Point**

The starting point of the data path, usually the Q output of a flip-flop.

**Capture Point**

The ending point of the data path, usually the D input of a flip-flop.

**Combinational Logic**

Logic that processes the data without storing it.

Examples include:

- AND gates
- OR gates
- Multiplexers
- Adders
- Comparators

**Interconnect**

The physical connection between cells. It also contributes to the total data-path delay.

**Data-Path Delay**

The time required for data to travel through the combinational logic and interconnect.

**Maximum Delay**

The largest relevant delay through the data path. It is mainly used for setup analysis.

**Minimum Delay**

The smallest relevant delay through the data path. It is mainly used for hold analysis.

**Critical Path**

The timing path with the most limiting timing behavior for a particular analysis, commonly the path with the smallest setup slack.

* **Formula**

For a simplified register-to-register path:

    Arrival Time
    =
    Clock-to-Q Delay
    +
    Data-Path Delay

For setup analysis:

    tCQ(max) + tDATA(max) + tSETUP ≤ TCLK

For hold analysis, a simplified relationship is:

    tCQ(min) + tDATA(min) ≥ tHOLD

Where:

- `tCQ` = Clock-to-Q delay
- `tDATA` = Data-path delay
- `tSETUP` = Setup time
- `tHOLD` = Hold time
- `TCLK` = Clock period

* **Simple Example**

Assume a path contains:

    Clock-to-Q Delay = 1 ns
    AND Delay        = 2 ns
    MUX Delay        = 2 ns
    Interconnect    = 1 ns

Therefore:

    Data-Path Delay
    = 2 + 2 + 1
    = 5 ns

Total data arrival from the launch clock edge:

    Arrival Time
    = Clock-to-Q + Data-Path Delay
    = 1 + 5
    = 6 ns

If the clock period is 10 ns and setup time is 1 ns:

    Required Time
    = 10 - 1
    = 9 ns

    Setup Slack
    = 9 - 6
    = +3 ns

The simplified setup requirement is satisfied.

* **STA Connection**

STA analyzes the data path using timing libraries and design information.

A simplified STA view is:

    Launch FF
        │
        │ Clock-to-Q
        ▼
    ┌───────────────────┐
    │     Data Path     │
    │                   │
    │  Logic + Wires    │
    └─────────┬─────────┘
              │
              ▼
         Capture FF

STA calculates the delay through this path and uses it to determine arrival time.

For setup:

    Maximum Data Delay → Important

For hold:

    Minimum Data Delay → Important

This is why both maximum and minimum delay information is required for timing analysis.

* **RTL Relevance**

RTL code determines the combinational logic that may appear in the data path.

For example:

    always @(*) begin
        y = (a & b) | c;
    end

If this logic is placed between two registers:

    Launch FF → AND/OR Logic → Capture FF

the AND and OR operations contribute to the data-path delay.

A large amount of combinational logic between registers can increase the data-path delay and may reduce the available setup margin.

Pipeline registers are commonly used to divide a long data path into smaller sections.

* **Common Mistakes**

- Thinking the data path contains only combinational gates.
- Forgetting interconnect delay.
- Ignoring clock-to-Q delay when calculating total arrival time.
- Using maximum delay for hold analysis.
- Using minimum delay for setup analysis.
- Assuming a shorter data path is always better.
- Forgetting that an excessively short path can create hold problems.
- Confusing the data path with the clock path.

* **Interview Questions**

**1. What is a data path?**

A data path is the path through which data travels from the launch element to the capture element.

**2. What does a data path contain?**

It can contain combinational logic and interconnect between the launch and capture elements.

**3. Why is data-path delay important?**

It determines when data reaches the capture element and therefore directly affects setup and hold timing.

**4. Which data-path delay is mainly used for setup analysis?**

The maximum data-path delay.

**5. Which data-path delay is mainly used for hold analysis?**

The minimum data-path delay.

* **Quick Revision**

- Data path = path followed by data.
- Typical path → Launch FF → Logic → Capture FF.
- Logic and interconnect contribute to data-path delay.
- Maximum delay → mainly important for setup.
- Minimum delay → mainly important for hold.
- Long data path → setup becomes harder.
- Very short data path → hold can become harder.
- Data path is different from the clock path.

* **Summary**

The data path carries data from the launch element to the capture element. It consists mainly of combinational logic and interconnect, both of which contribute to data-path delay. STA analyzes the maximum and minimum delays of this path for setup and hold checks. Understanding the data path is essential for understanding arrival time, required time, slack, critical paths, and timing violations.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
