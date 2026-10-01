# **Setup Analysis**

* **Overview**

Setup analysis checks whether data reaches a capture register early enough before the active capture clock edge. It uses the maximum delay of the data path to verify that the setup-time requirement is satisfied.

---

* **Definition**

Setup analysis is a Static Timing Analysis (STA) check that verifies whether data arrives at the capture register at least the required setup time before the capture clock edge.

---

* **Why is it needed?**

Setup analysis is needed to:

- Verify correct data capture at the required clock edge.
- Identify paths with excessive maximum delay.
- Determine whether the target clock period is sufficient.
- Calculate setup slack.
- Detect setup timing violations before chip fabrication.

---

* **Core Concept**

Consider two registers connected through combinational logic.

    Launch Register
          │
          ▼
    Combinational Logic
          │
          ▼
    Capture Register

The launch register sends data after its active clock edge.

The data travels through the combinational logic before reaching the capture register.

The data must arrive early enough to remain stable for the required setup time before the next capture edge.

If the data arrives too late, a **setup violation** occurs.

---

* **Timing Diagram**

    Clock:
           ↑                         ↑
           │                         │
       Launch Edge               Capture Edge
           │                         │
           └──── Clock Period ───────┘

    Data:
           ── Old Data ──┐
                         └──── New Data ─────────
                                      ▲
                                      │
                              Data Arrival

    Capture Edge:
                                      ↑
                           Setup Time  │
                           ←───────────┤
                         Data must be stable
                         before this edge.

The new data must arrive no later than the capture edge minus the setup time.

---

* **Important Terms**

| Term | Meaning |
|---|---|
| **Clock Period (`TCLK`)** | Time between consecutive active clock edges |
| **Clock-to-Q Delay (`tCQ`)** | Delay from the launch clock edge to the register output |
| **Maximum Data Delay (`tDATA(max)`)** | Maximum delay through combinational logic and interconnect |
| **Setup Time (`tSETUP`)** | Minimum time data must be stable before the capture edge |
| **Arrival Time** | Time at which data reaches the capture register |
| **Required Time** | Latest allowed data arrival time for setup |
| **Setup Slack** | Difference between required time and arrival time |
| **Setup Violation** | Condition where data arrives later than permitted |

---

* **Formula**

For a simplified register-to-register setup check with the same clock arrival time at both registers:

    tCQ(max) + tDATA(max) + tSETUP ≤ TCLK

Where:

- `tCQ(max)` = maximum clock-to-Q delay
- `tDATA(max)` = maximum combinational and interconnect delay
- `tSETUP` = setup time of the capture register
- `TCLK` = clock period

The setup slack is:

    Setup Slack = Required Time − Arrival Time

For a more general setup check, clock arrival times, clock uncertainty, and other timing constraints must also be considered.

---

* **Simple Example**

Assume:

    Clock Period       = 10 ns
    Clock-to-Q Delay   = 1 ns
    Data Path Delay    = 6 ns
    Setup Time         = 1 ns

**Step 1: Calculate arrival time**

    Arrival Time
    = Clock-to-Q + Data Path Delay
    = 1 + 6
    = 7 ns

**Step 2: Calculate required time**

    Required Time
    = Clock Period − Setup Time
    = 10 − 1
    = 9 ns

**Step 3: Calculate setup slack**

    Setup Slack
    = Required Time − Arrival Time
    = 9 − 7
    = +2 ns

**Result:** Setup timing passes with **2 ns positive slack**.

If the data path delay increased to 9 ns:

    Arrival Time = 1 + 9 = 10 ns
    Required Time = 9 ns
    Setup Slack = 9 − 10 = −1 ns

**Result:** Setup timing fails with a 1 ns violation.

---

* **STA Connection**

STA performs setup analysis using:

- Maximum cell and interconnect delays.
- Launch and capture clock arrival times.
- Clock period and timing constraints.
- Capture-register setup time.
- Clock uncertainty and other applicable timing adjustments.

A simplified setup-analysis flow is:

    Timing Graph
         ↓
    Find Setup Timing Paths
         ↓
    Calculate Maximum Data Arrival
         ↓
    Calculate Required Arrival Time
         ↓
    Calculate Setup Slack
         ↓
    Report Violations

A negative setup slack indicates that the path does not meet the setup requirement under the analyzed conditions.

---

* **RTL Relevance**

RTL structure affects the logic synthesized between registers.

For example:

    always @(posedge clk)
        q <= a & b & c & d;

Depending on the surrounding design and synthesis results, the combinational logic feeding a register can contribute to the data-path delay.

A path containing too much logic may fail setup timing.

RTL Design Engineers can help improve setup timing by:

- Reducing unnecessary combinational logic.
- Avoiding unnecessarily deep logic paths.
- Using appropriate pipeline stages when the design specification permits.
- Reviewing timing reports to identify critical paths.
- Preserving the required functional behavior while optimizing RTL.

---

* **Common Mistakes**

- Using minimum delay instead of maximum delay for setup analysis.
- Forgetting the capture register's setup time.
- Assuming positive slack means a timing violation.
- Ignoring clock skew and clock uncertainty in real timing reports.
- Assuming that correct simulation results guarantee setup timing.
- Adding pipeline registers without checking the required functionality and latency.

---

* **Interview Questions**

**1. What is setup analysis?**

Setup analysis verifies that data arrives at the capture register early enough before the active capture clock edge.

**2. Which delay is important for setup analysis?**

Maximum data-path delay is important because setup analysis checks whether data arrives late.

**3. What causes a setup violation?**

A setup violation occurs when data arrives later than the latest permitted arrival time.

**4. How can setup timing be improved?**

Possible methods include reducing logic depth, optimizing the combinational path, and adding pipeline stages when permitted by the design specification.

**5. What does negative setup slack mean?**

Negative setup slack means the data arrives later than the required time, so the setup requirement is violated.

---

* **Quick Revision**

    Setup Analysis
    → Checks late data arrival.

    Main delay:
    Maximum Data Delay

    Basic path:
    Launch FF → Data Path → Capture FF

    Setup Requirement:
    Data must arrive before the capture edge
    by at least the setup time.

    Setup Slack:
    Required Time − Arrival Time

    Positive Slack:
    Setup requirement satisfied.

    Zero Slack:
    Timing requirement exactly met.

    Negative Slack:
    Setup violation.

---

* **Summary**

Setup analysis verifies that data reaches the capture register early enough to satisfy its setup-time requirement. It primarily uses maximum data-path delay and compares arrival time with required time. Understanding setup analysis is essential for identifying critical paths and determining whether an ASIC design can operate at its target clock period.

---

* **References**

- Harris, S. L. & Harris, D. M., *Digital Design and Computer Architecture*, Morgan Kaufmann.
- Weste, N. H. E. & Harris, D. M., *CMOS VLSI Design: A Circuits and Systems Perspective*, Pearson.
- Synopsys, *PrimeTime Static Timing Analysis* documentation.
- Cadence, *Static Timing Analysis* technical documentation.
- Neso Academy, Digital Electronics and VLSI Design lectures.
