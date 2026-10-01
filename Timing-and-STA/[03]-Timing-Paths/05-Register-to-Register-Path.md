# **Register-to-Register Path**

* **Overview**

A register-to-register path is a timing path in which data travels from one sequential element, usually a flip-flop, to another flip-flop.

It is one of the most common timing paths analyzed in STA for synchronous digital designs.

* **Definition**

A **register-to-register path** is a timing path that starts at the output of a launch register and ends at the input of a capture register.

The basic structure is:

    Launch Register
          │
          │ Q
          ▼
    Combinational Logic
          │
          ▼
    Capture Register
          │
          │ D

* **Why is it needed?**

Register-to-register paths are important because they form the basic data-transfer paths in synchronous digital circuits.

STA analyzes these paths to determine:

- Whether data reaches the capture register in time.
- Whether setup timing is satisfied.
- Whether hold timing is satisfied.
- The timing slack.
- Whether the path is critical.
- The maximum operating frequency of the design.

* **Core Concept**

Consider two registers connected through combinational logic:

                    Clock
                   │
          ┌────────┴────────┐
          │                 │
          ▼                 ▼
       ┌─────┐          ┌─────┐
       │ FF1 │          │ FF2 │
       │     │          │     │
       └──┬──┘          └──▲──┘
          │ Q              │ D
          │                │
          ▼                │
      ┌───────────┐         │
      │Combinational│       │
      │   Logic    │────────┘
      └───────────┘

      FF1 = Launch Register
      FF2 = Capture Register

When the active clock edge occurs:

1. FF1 launches new data.
2. Data appears at FF1's Q after clock-to-Q delay.
3. Data travels through the combinational logic.
4. Data reaches FF2's D input.
5. FF2 captures the data at the capture clock edge.

* **Timing Diagram**

A simplified register-to-register timing path is:

    Clock
          ↑                         ↑
          │                         │
    ──────┼─────────────────────────┼──────
          │                         │
       Launch                    Capture
        Edge                      Edge
          │                         │
          ▼                         │
       FF1 launches                │
          │                         │
          │ Clock-to-Q             │
          ▼                         │
       Data changes                │
          │                         │
          │ Data Path Delay        │
          ├───────────────────────►│
                                    │
                                FF2 captures

The data must arrive at FF2 early enough to satisfy its setup requirement.

* **Important Terms**

**Launch Register**

The register that sends or launches data into the data path.

**Capture Register**

The register that receives and captures the data.

**Clock-to-Q Delay**

The delay between the active clock edge and the corresponding change at the launch register's Q output.

**Data Path**

The combinational logic and interconnect between the launch and capture registers.

**Setup Time**

The minimum time for which data must be stable before the capture clock edge.

**Hold Time**

The minimum time for which data must remain stable after the capture clock edge.

**Launch Clock Path**

The path through which the clock reaches the launch register.

**Capture Clock Path**

The path through which the clock reaches the capture register.

* **Formula**

For a simplified setup check:

    tCQ(max) + tDATA(max) + tSETUP
    ≤
    TCLK

Including simplified clock skew:

    tCQ(max) + tDATA(max) + tSETUP
    ≤
    TCLK + tSKEW

Where:

- `tCQ` = Clock-to-Q delay
- `tDATA` = Data-path delay
- `tSETUP` = Setup time
- `TCLK` = Clock period
- `tSKEW` = Capture clock arrival − Launch clock arrival

For setup slack:

    Setup Slack
    = Required Time - Arrival Time

* **Simple Example**

Assume:

    Clock Period      = 10 ns
    Clock-to-Q Delay  = 1 ns
    Data Path Delay   = 6 ns
    Setup Time        = 1 ns

Data arrival:

    Arrival Time
    = tCQ + tDATA
    = 1 + 6
    = 7 ns

Latest allowed arrival:

    Required Time
    = TCLK - tSETUP
    = 10 - 1
    = 9 ns

Therefore:

    Setup Slack
    = 9 - 7
    = +2 ns

The register-to-register path satisfies the simplified setup requirement.

* **STA Connection**

STA analyzes a register-to-register path as a combination of clock paths and a data path:

             Clock Source
                  │
           ┌──────┴──────┐
           │             │
           ▼             ▼
      Launch Clock   Capture Clock
          Path           Path
           │             │
           ▼             ▼
       Launch FF      Capture FF
           │
           │ Q
           ▼
       Data Path
           │
           ▼
       Capture FF
           │
           │ D
           ▼
       Timing Check

STA determines:

1. Launch clock arrival.
2. Launch register clock-to-Q delay.
3. Data-path delay.
4. Data arrival time.
5. Capture clock arrival.
6. Required arrival time.
7. Setup or hold slack.

For setup analysis, maximum path delays are generally important.

For hold analysis, minimum path delays are generally important.

* **RTL Relevance**

Register-to-register paths are directly created by synchronous RTL.

For example:

    always @(posedge clk)
        q1 <= d;

    always @(posedge clk)
        q2 <= q1;

Here:

    q1 → Launch Register
    q2 → Capture Register

If combinational logic is placed between them:

    q1 → Combinational Logic → q2

that logic becomes part of the register-to-register data path.

A long combinational path can increase delay and create a setup violation.

* **Common Mistakes**

- Forgetting the clock-to-Q delay of the launch register.
- Ignoring the capture register's setup or hold requirement.
- Confusing the data path with the clock path.
- Assuming the clock reaches both registers at exactly the same time.
- Using maximum delay for hold analysis.
- Using minimum delay for setup analysis.
- Assuming a functionally correct RTL path automatically meets timing.
- Forgetting that a very short data path can cause hold problems.

* **Interview Questions**

**1. What is a register-to-register path?**

It is a timing path from the output of a launch register to the input of a capture register.

**2. What are the main components of a register-to-register path?**

    Launch Register
          ↓
    Clock-to-Q Delay
          ↓
    Data Path
          ↓
    Capture Register

The associated launch and capture clock paths are also analyzed.

**3. What causes setup problems in a register-to-register path?**

Excessive clock-to-Q delay, excessive data-path delay, setup time, clock skew, or insufficient clock period can contribute to setup problems.

**4. What causes hold problems?**

A data path that is too fast, along with the relevant clock relationship and hold requirement, can cause a hold violation.

**5. Why is the register-to-register path important in STA?**

It is one of the fundamental timing paths used to verify whether synchronous data transfers meet setup and hold requirements.

* **Quick Revision**

- Register-to-register path = register → logic → register.
- Launch register sends data.
- Capture register receives data.
- Data path contains combinational logic and interconnect.
- Clock-to-Q contributes to data arrival.
- Setup checks maximum delay.
- Hold checks minimum delay.
- Clock paths determine when launch and capture edges arrive.
- STA checks the complete path for timing violations.

* **Summary**

A register-to-register path is a fundamental synchronous timing path in digital design. Data is launched from one register, travels through the data path, and is captured by another register. STA analyzes the launch and capture clock paths together with the data path to verify setup and hold timing. Understanding this path provides the foundation for arrival time, required time, slack, critical path, and timing-violation analysis.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
