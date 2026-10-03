# **Hold Analysis**

* **Overview**

Hold analysis checks whether data remains stable at the capture register for the required time after the active capture clock edge. It mainly uses the minimum delay of the data path.

---

* **Definition**

Hold analysis is a Static Timing Analysis (STA) check that verifies that newly launched data does not reach the capture register too early after the capture clock edge.

---

* **Why is it needed?**

Hold analysis is needed to:

- Verify that the capture register does not capture new data too early.
- Detect paths with insufficient minimum delay.
- Check the hold-time requirement of the capture register.
- Identify hold timing violations.
- Ensure reliable operation of sequential logic.

---

* **Core Concept**

Consider a register-to-register path:

    Launch Register
          │
          ▼
    Combinational Logic
          │
          ▼
    Capture Register

After the capture clock edge, the capture register needs the old data to remain stable for a certain amount of time.

If the newly launched data travels through the data path too quickly and changes the capture-register input during this hold window, a **hold violation** can occur.

The key idea is:

    Setup → Data must not arrive too late.

    Hold  → Data must not arrive too early.

---

* **Timing Diagram**

    Capture Clock:
                  ↑
                  │
                  │
    ──────────────┼──────────────────────────►
                  │
                  │←── Hold Time ──→
                  │
                  │
    Data:
    ──────────────┐
                  │
                  └──────── New Data
                       ▲
                       │
                 Must not change
                 during hold window

The data at the capture register must remain stable for at least the required hold time after the capture clock edge.

---

* **Important Terms**

| Term | Meaning |
|---|---|
| **Hold Time (`tHOLD`)** | Minimum time data must remain stable after the capture clock edge |
| **Minimum Clock-to-Q (`tCQ(min)`)** | Earliest time the launch register output can change |
| **Minimum Data Delay (`tDATA(min)`)** | Minimum delay through combinational logic and interconnect |
| **Arrival Time** | Earliest time newly launched data reaches the capture register |
| **Required Time** | Earliest permitted data arrival time for the hold check |
| **Hold Slack** | Margin between actual early arrival and the hold requirement |
| **Hold Violation** | Condition where new data arrives too early |

---

* **Formula**

For a simplified same-clock register-to-register hold check:

    tCQ(min) + tDATA(min) ≥ tHOLD

Where:

- `tCQ(min)` = minimum clock-to-Q delay
- `tDATA(min)` = minimum data-path delay
- `tHOLD` = hold time of the capture register

A simplified hold slack can be expressed as:

    Hold Slack = Arrival Time − Required Time

Therefore:

    Positive Hold Slack → Hold timing passes
    Zero Hold Slack     → Hold requirement is exactly met
    Negative Hold Slack → Hold violation

In a real STA analysis, clock skew, clock uncertainty, and other timing effects are also included.

---

* **Simple Example**

Assume:

    Minimum Clock-to-Q Delay = 1 ns
    Minimum Data Path Delay  = 2 ns
    Hold Time                = 1 ns

**Step 1: Calculate earliest data arrival**

    Arrival Time
    = tCQ(min) + tDATA(min)
    = 1 + 2
    = 3 ns

**Step 2: Compare with hold requirement**

    Hold Requirement = 1 ns

    Hold Slack
    = 3 − 1
    = +2 ns

**Result:** Hold timing passes with **2 ns positive slack**.

Now assume the minimum data-path delay is only 0 ns:

    Arrival Time
    = 1 + 0
    = 1 ns

    Hold Slack
    = 1 − 1
    = 0 ns

The path exactly meets the hold requirement.

If the minimum clock-to-Q delay were 0.5 ns and the minimum data-path delay were 0 ns:

    Arrival Time = 0.5 ns

    Hold Slack
    = 0.5 − 1
    = −0.5 ns

**Result:** Hold timing fails with a **0.5 ns violation**.

---

* **Setup vs Hold**

| Feature | Setup Analysis | Hold Analysis |
|---|---|---|
| Main concern | Data arrives too late | Data arrives too early |
| Important delay | Maximum delay | Minimum delay |
| Main parameter | Setup time | Hold time |
| Clock relationship | Usually next capture edge | Same capture edge |
| Violation | Late data | Early data |
| Typical fix | Reduce delay / optimize path / pipeline | Add delay to the data path |
| Clock frequency impact | Directly related to maximum operating frequency | Not directly fixed by increasing clock period |

A useful way to remember:

    Setup → Too Slow → Data arrives late

    Hold → Too Fast → Data arrives early

---

* **STA Connection**

STA performs hold analysis using minimum-delay information.

A simplified flow is:

    Timing Graph
         ↓
    Find Hold Timing Paths
         ↓
    Calculate Earliest Data Arrival
         ↓
    Calculate Hold Requirement
         ↓
    Calculate Hold Slack
         ↓
    Report Violations

Hold analysis is particularly sensitive to:

- Minimum cell delays
- Minimum interconnect delays
- Clock skew
- Clock uncertainty
- Capture-register hold time

---

* **RTL Relevance**

RTL designers should understand hold timing because RTL determines the structure of the synthesized data path.

A very short path such as:

    Launch FF → Small Logic → Capture FF

may have very little minimum delay.

However, hold fixing is commonly performed later in the implementation flow by adding delay to the data path, rather than changing RTL simply to add arbitrary delay.

The important RTL-level goal is to create a correct synchronous architecture and understand how the resulting timing paths behave.

---

* **Common Mistakes**

- Using maximum delay for hold analysis.
- Thinking hold timing is fixed by increasing the clock period.
- Thinking hold means data must arrive before the clock edge.
- Forgetting that hold is checked around the capture clock edge.
- Assuming a fast data path is always beneficial.
- Ignoring clock skew in hold analysis.
- Adding arbitrary RTL delay elements as a timing fix without understanding synthesis and implementation behavior.

---

* **Interview Questions**

**1. What is hold analysis?**

Hold analysis checks whether newly launched data arrives at the capture register too early after the capture clock edge.

**2. Which delay is important for hold analysis?**

Minimum data-path delay is important because hold analysis is concerned with the earliest possible arrival of new data.

**3. What causes a hold violation?**

A hold violation occurs when new data reaches the capture register before the required hold time has elapsed.

**4. Does increasing the clock period fix a hold violation?**

No. A basic hold check is associated with the same capture clock edge, so simply increasing the clock period does not fix a hold violation.

**5. How is a hold violation commonly fixed?**

The data path can be given additional delay, for example by inserting appropriate delay cells during implementation. Clock-tree adjustments may also affect hold timing.

---

* **Quick Revision**

    Hold Analysis
    → Checks early data arrival.

    Main delay:
    Minimum Data Delay

    Basic path:
    Launch FF → Data Path → Capture FF

    Hold Requirement:
    Data must remain stable after
    the capture clock edge.

    Simplified condition:
    tCQ(min) + tDATA(min) ≥ tHOLD

    Positive Slack:
    Hold requirement satisfied.

    Zero Slack:
    Exactly meets the requirement.

    Negative Slack:
    Hold violation.

    Remember:

    Setup → Too late

    Hold → Too early

---

* **Summary**

Hold analysis verifies that newly launched data does not reach the capture register too early. Unlike setup analysis, which focuses mainly on maximum delay, hold analysis focuses on minimum delay. Clock skew and other clock effects are also important in real STA. Understanding hold analysis is essential for analyzing timing violations and designing reliable synchronous ASIC circuits.

---

* **References**

- Harris, S. L. & Harris, D. M., *Digital Design and Computer Architecture*, Morgan Kaufmann.
- Weste, N. H. E. & Harris, D. M., *CMOS VLSI Design: A Circuits and Systems Perspective*, Pearson.
- Synopsys, *PrimeTime Static Timing Analysis* documentation.
- Cadence, *Static Timing Analysis* technical documentation.
- Neso Academy, Digital Electronics and VLSI Design lectures.
