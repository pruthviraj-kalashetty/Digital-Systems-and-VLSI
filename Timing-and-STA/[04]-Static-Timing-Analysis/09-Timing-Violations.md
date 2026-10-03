# **Timing Violations**

* **Overview**

A timing violation occurs when a signal does not satisfy the required timing condition of a digital circuit.

In STA, timing violations are mainly identified using **negative slack**.

The two most important violations are:

- **Setup Violation** → Data arrives too late.
- **Hold Violation** → Data arrives too early.

---

* **Definition**

A timing violation occurs when the actual signal arrival does not satisfy the required timing constraint.

    Setup Violation → Arrival Time > Required Time

    Hold Violation → Arrival Time < Required Time

Therefore:

    Negative Slack → Timing Violation

---

* **Why is it needed?**

Timing analysis helps identify whether a design can reliably operate at its target clock speed.

Timing violations can cause:

- Incorrect data capture.
- Unreliable circuit operation.
- Reduced maximum operating frequency.
- Failure at the intended clock speed.
- Possible intermittent hardware failures.

For an RTL Design Engineer, understanding timing violations is important because RTL structure affects the data path and therefore timing.

---

* **Core Concept**

A basic register-to-register path is:

    Launch FF
        │
        │ Clock-to-Q
        ▼
    Combinational Logic
        │
        │ Data Path
        ▼
    Capture FF

STA checks whether the data reaches the capture register at the correct time.

There are two main checks:

    ┌───────────────────────┐
    │       Setup          │
    │ Data must arrive     │
    │ early enough         │
    └───────────────────────┘

    ┌───────────────────────┐
    │        Hold          │
    │ Data must not arrive  │
    │ too early             │
    └───────────────────────┘

---

* **Setup Violation**

A setup violation occurs when data arrives **too late** at the capture register.

The simplified condition is:

    Arrival Time > Required Time

Therefore:

    Setup Slack < 0

### Example

    Required Time = 9 ns
    Arrival Time  = 10 ns

    Setup Slack = 9 - 10
                = -1 ns

The path has a **1 ns setup violation**.

### Timing View

    Launch Edge                         Capture Edge
         │                                  │
         ▼                                  ▼
    ─────┼──────────────────────────────────┼────────► Time
         │                                  │
         │                         Required │
         │                            │     │
         │                            ▼     │
         │                         Arrival │
         │                            │     │
         │                            └─────┘
         │
         └────────── Data arrives too late

The data misses the required setup window.

---

* **Hold Violation**

A hold violation occurs when new data arrives **too early** after the capture clock edge.

The simplified condition is:

    Arrival Time < Required Time

Therefore:

    Hold Slack < 0

### Example

    Arrival Time  = 0.5 ns
    Required Time = 1 ns

    Hold Slack = 0.5 - 1
               = -0.5 ns

The path has a **0.5 ns hold violation**.

### Timing View

    Capture Edge
         │
         ▼
    ─────┼──────────────────────────────────► Time
         │
         │──── Hold Requirement ────│
         │                          │
         │                    Required Time
         │
       New Data
       arrives here
         │
         ▼
       Too early

The new data changes the destination input before the required hold time has passed.

---

* **Setup vs Hold Violation**

| Feature | Setup Violation | Hold Violation |
|---|---|---|
| Main problem | Data arrives too late | Data arrives too early |
| Delay considered | Maximum delay | Minimum delay |
| Slack | Negative setup slack | Negative hold slack |
| Main path concern | Long/slow data path | Very short/fast data path |
| Basic question | "Did data arrive early enough?" | "Did old data remain long enough?" |
| Clock period effect | Increasing period can help setup | Increasing period does not directly fix hold |

Remember:

    SETUP → Too Late

    HOLD → Too Early

---

* **Important Terms**

| Term | Meaning |
|---|---|
| Timing Violation | Timing requirement is not satisfied |
| Setup Violation | Data arrives too late |
| Hold Violation | Data arrives too early |
| Slack | Timing margin |
| Negative Slack | Indicates a timing violation |
| Critical Path | Path with the worst timing margin |
| Data Path | Logic path between launch and capture elements |
| Timing Constraint | Requirement used by STA to evaluate timing |

---

* **Common Causes**

### Setup Violation Causes

Common causes include:

- Long combinational logic path.
- Too many logic levels.
- Large routing delay.
- High fanout.
- Slow cells.
- Clock period being too short.
- Excessive clock uncertainty.

Simplified relationship:

    Data Delay ↑
         ↓
    Arrival Time ↑
         ↓
    Setup Slack ↓
         ↓
    Setup Violation

---

### Hold Violation Causes

Common causes include:

- Very short data path.
- Very fast cells.
- Small minimum propagation delay.
- Clock skew.
- Clock-tree effects.
- Insufficient delay in the data path.

Simplified relationship:

    Data Delay ↓
         ↓
    Arrival Time ↓
         ↓
    Hold Slack ↓
         ↓
    Hold Violation

---

* **How Setup Violations Can Be Improved**

At the RTL/design level, possible approaches include:

- Reduce unnecessary combinational logic.
- Reduce logic depth.
- Improve the architecture.
- Avoid unnecessarily long critical paths.
- Use appropriate pipelining when the architecture allows it.
- Reduce unnecessary high-fanout control logic.

Example:

    Before:

    FF → Logic → Logic → Logic → Logic → FF

    After optimization:

    FF → Logic → Logic → FF

Reducing the amount of combinational work can reduce data-path delay.

Actual implementation fixes can also involve cell sizing, buffering, placement, and routing.

---

* **How Hold Violations Can Be Improved**

Hold violations are commonly addressed during implementation using techniques such as:

- Adding delay to the data path.
- Buffer insertion.
- Cell selection.
- Clock-tree optimization.
- Adjusting implementation-related timing.

Conceptually:

    Data arrives too early
           ↓
    Add controlled delay
           ↓
    Data arrives later
           ↓
    Hold slack improves

An RTL designer should understand hold timing, but hold fixes are often handled during physical implementation rather than by adding arbitrary RTL delays.

---

* **Formula**

### Setup

    Setup Slack = Required Time - Arrival Time

    Setup Violation:
    Setup Slack < 0

### Hold

    Hold Slack = Arrival Time - Required Time

    Hold Violation:
    Hold Slack < 0

---

* **Simple Example**

### Setup

Given:

    Required Time = 9 ns
    Arrival Time  = 11 ns

Then:

    Setup Slack = 9 - 11
                = -2 ns

Therefore:

    Setup Violation = 2 ns

---

### Hold

Given:

    Arrival Time  = 0.5 ns
    Required Time = 1 ns

Then:

    Hold Slack = 0.5 - 1
               = -0.5 ns

Therefore:

    Hold Violation = 0.5 ns

---

* **STA Connection**

Timing violations are identified after STA calculates arrival and required times.

    Timing Path
         ↓
    Arrival Time
         ↓
    Required Time
         ↓
    Slack
         ↓
    ┌───────────────────┐
    │ Positive Slack?   │
    └─────────┬─────────┘
              │
       ┌──────┴──────┐
       │             │
      YES            NO
       │             │
       ▼             ▼
    Timing        Timing
     Pass        Violation

This connects the concepts learned so far:

    Timing Path
        ↓
    Arrival Time
        ↓
    Required Time
        ↓
    Slack
        ↓
    Timing Violation

---

* **RTL Relevance**

RTL designers should understand how RTL structure can affect timing.

For example:

    FF
     │
     ▼
    MUX
     │
     ▼
    ALU
     │
     ▼
    Comparator
     │
     ▼
    FF

A large amount of combinational logic between registers can create a long data path.

This can increase:

    Data Delay
         ↓
    Arrival Time
         ↓
    Setup Violation

Therefore, good RTL design considers both:

- Functional correctness.
- Timing requirements.

However, RTL simulation passing does **not** guarantee that the design is timing-clean.

---

* **Common Mistakes**

1. **Thinking setup and hold violations are the same**

   Setup → data too late.

   Hold → data too early.

2. **Thinking increasing the clock period fixes every timing problem**

   Increasing the period can help setup timing, but it does not directly solve a hold violation.

3. **Adding arbitrary RTL delays to fix hold**

   RTL delay statements are generally not an appropriate way to fix real ASIC hold timing.

4. **Assuming simulation passing means no timing violation**

   Functional simulation and STA check different aspects of the design.

5. **Ignoring negative slack**

   Negative slack means the timing requirement is not satisfied for that analyzed path/corner/constraint.

---

* **Interview Questions**

**Q1. What is a timing violation?**

A timing violation occurs when a signal fails to satisfy its required timing constraint.

**Q2. What is a setup violation?**

A setup violation occurs when data arrives too late at the capture register.

**Q3. What is a hold violation?**

A hold violation occurs when new data arrives too early after the capture clock edge.

**Q4. Which type of delay is mainly used for setup analysis?**

Setup analysis mainly uses **maximum/late delay**.

**Q5. Which type of delay is mainly used for hold analysis?**

Hold analysis mainly uses **minimum/early delay**.

---

* **Quick Revision**

    Setup Violation
    ───────────────
    Data arrives too late
    Setup Slack < 0

    Hold Violation
    ──────────────
    Data arrives too early
    Hold Slack < 0

    Setup:
    Slack = Required - Arrival

    Hold:
    Slack = Arrival - Required

    Setup → Long/slow path is a common concern

    Hold → Short/fast path is a common concern

    Negative Slack → Timing Violation

---

* **Summary**

Timing violations occur when a digital circuit fails to meet its timing requirements.

The two main types are:

    Setup Violation → Data arrives too late.

    Hold Violation → Data arrives too early.

STA identifies these violations using **Arrival Time, Required Time, and Slack**.

For an RTL Design Engineer, understanding these concepts helps connect RTL architecture and logic depth with the timing behavior of the final ASIC implementation.

---

* **References**

- *Digital Design and Computer Architecture* — David Harris and Sarah Harris
- *CMOS VLSI Design* — Neil H. E. Weste and David Harris
- *Digital Integrated Circuits* — Jan M. Rabaey, Anantha Chandrakasan, and Borivoje Nikolić
- Synopsys — Static Timing Analysis documentation
- Cadence — Timing Analysis and Signoff documentation
