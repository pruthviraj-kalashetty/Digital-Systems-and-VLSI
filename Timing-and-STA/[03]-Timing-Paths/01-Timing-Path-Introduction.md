# **Timing Path Introduction**

* **Overview**

A timing path is the path followed by a signal as it travels from a source element to a destination element in a digital circuit.

In synchronous ASIC designs, timing paths are mainly analyzed between sequential elements such as flip-flops.

---

* **Definition**

A **timing path** is a logical and physical path through which a signal travels from a **launch point** to a **capture point**.

A basic register-to-register timing path contains:

**Launch Flip-Flop → Data Path → Capture Flip-Flop**

STA analyzes this path to determine whether the data arrives within the required timing limits.

---

* **Why is it needed?**

Understanding timing paths is important for an ASIC RTL Design Engineer because:

- STA analyzes timing paths to verify circuit timing.
- Setup and hold checks are performed on timing paths.
- Timing violations occur when a path does not satisfy its timing requirement.
- Critical paths determine the maximum operating frequency.
- RTL changes can create, remove, or modify timing paths.

---

* **Core Concept**

Consider two flip-flops connected through combinational logic:

    Launch FF                 Combinational Logic              Capture FF
    ┌─────────┐              ┌──────────────────┐             ┌─────────┐
    │         │              │                  │             │         │
    │ Launch  │─────────────►│   Data Path      │────────────►│ Capture │
    │   FF    │              │                  │             │   FF    │
    └─────────┘              └──────────────────┘             └─────────┘
         ▲                                                        ▲
         │                                                        │
    Launch Clock                                             Capture Clock

The launch flip-flop changes its output after the launch clock edge.

The data then travels through the combinational logic.

The capture flip-flop receives and captures the data at the next appropriate clock edge.

The complete path is:

    Launch Clock
         ↓
    Launch Flip-Flop
         ↓
    Clock-to-Q Delay
         ↓
    Combinational Logic
         ↓
    Data Arrival
         ↓
    Capture Flip-Flop

---

* **Timing Diagram**

A simple positive-edge-triggered register-to-register path can be represented as:

    Launch Clock:
    ________/‾‾‾‾‾‾‾‾‾\________________/‾‾‾‾‾‾‾‾‾\____
             ↑                              ↑
        Launch Edge                    Capture Edge


    Data:
    ____________/‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\________
                 ↑                         ↑
              Data Launch              Data Capture

    Timing Path:

    Launch FF
       │
       │ tCQ
       ▼
    Combinational Logic
       │
       │ tDATA
       ▼
    Capture FF

The data launched at the first clock edge must reach the capture flip-flop within the required timing window.

---

* **Important Terms**

- **Timing Path** → Path followed by a signal between timing points.
- **Launch Element** → Sequential element that launches data.
- **Capture Element** → Sequential element that captures data.
- **Data Path** → Path followed by the data signal.
- **Clock Path** → Path followed by the clock signal.
- **Launch Clock** → Clock reaching the launch element.
- **Capture Clock** → Clock reaching the capture element.
- **Clock-to-Q Delay (tCQ)** → Time between the active clock edge and a change at the flip-flop output.
- **Data Arrival Time** → Time when data reaches the capture point.
- **Required Time** → Latest or earliest allowable arrival time depending on the timing check.
- **Slack** → Difference between required time and arrival time.

---

* **Formula**

For a basic register-to-register setup path:

**Data Arrival Time = Launch Clock Arrival + tCQ + tDATA**

Where:

- **Launch Clock Arrival** = Time the launch clock edge reaches the launch flip-flop.
- **tCQ** = Clock-to-Q delay of the launch flip-flop.
- **tDATA** = Delay through the combinational data path.

A simplified setup timing condition is:

**tCQ + tDATA + tSETUP ≤ TCLK**

Where:

- **tSETUP** = Setup time of the capture flip-flop.
- **TCLK** = Clock period.

---

* **Simple Example**

Assume:

- Clock period = **10 ns**
- Launch flip-flop clock-to-Q delay = **1 ns**
- Combinational data-path delay = **6 ns**
- Capture flip-flop setup time = **1 ns**

Data arrival relative to the launch edge:

**Data Arrival = 1 + 6**

**Data Arrival = 7 ns**

Required maximum data arrival:

**10 − 1 = 9 ns**

Therefore:

**Setup Slack = 9 − 7**

**Setup Slack = +2 ns**

The timing path satisfies the basic setup requirement.

---

* **STA Connection**

Timing paths are the basic objects analyzed by Static Timing Analysis.

STA determines:

- Where the path starts.
- Where the path ends.
- How long the data takes to travel.
- When the data is required.
- Whether setup and hold requirements are satisfied.
- How much timing slack is available.

A simplified STA flow is:

    Identify Timing Path
            ↓
    Calculate Data Arrival
            ↓
    Calculate Required Time
            ↓
    Calculate Slack
            ↓
    Pass or Violation

A path with negative slack indicates a timing violation.

---

* **RTL Relevance**

RTL describes the functional structure that eventually becomes timing paths after synthesis.

For example:

    always @(posedge clk)
        Q1 <= D;

    always @(posedge clk)
        Q2 <= Q1 + A;

This creates a register-to-register path conceptually similar to:

    Q1 → Combinational Logic → Q2

The combinational logic between Q1 and Q2 contributes to the data-path delay.

An RTL engineer should therefore understand how:

**RTL → Registers + Logic → Timing Paths → STA Analysis**

---

* **Common Mistakes**

- Thinking a timing path is only the combinational logic.
- Forgetting the launch and capture elements.
- Confusing the data path with the clock path.
- Assuming every timing path has the same delay.
- Ignoring timing paths when modifying RTL logic.

---

* **Interview Questions**

**1. What is a timing path?**

**Answer:**

A timing path is the path followed by a signal from a launch point to a capture point through the circuit.

---

**2. What are the main elements of a register-to-register timing path?**

**Answer:**

The main elements are the launch flip-flop, clock-to-Q delay, combinational data path, and capture flip-flop.

---

**3. What is a launch element?**

**Answer:**

A launch element is a sequential element that launches data into a timing path after receiving its active clock edge.

---

**4. What is a capture element?**

**Answer:**

A capture element is a sequential element that receives and captures data at the end of a timing path.

---

**5. Why are timing paths important in STA?**

**Answer:**

STA analyzes timing paths to determine whether data reaches the capture element within the required timing limits and whether setup and hold requirements are satisfied.

---

* **Quick Revision**

- **Timing Path → Signal path from launch to capture.**
- Basic path:

      Launch FF → Data Path → Capture FF

- **Launch Element → Starts the data transfer.**
- **Capture Element → Captures the data.**
- **Data Path → Carries the data.**
- **Clock Path → Carries the clock.**
- STA analyzes timing paths.
- Timing paths are used for setup and hold checks.
- Negative slack indicates a timing violation.
- RTL structure directly affects the resulting timing paths.

---

* **Summary**

A timing path is the signal path between a launch point and a capture point.

For a typical synchronous ASIC design, the path consists of a launch flip-flop, combinational data logic, and a capture flip-flop. STA analyzes these paths to calculate arrival time, required time, and slack and to identify timing violations.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Static Timing Analysis and Timing Constraints documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
