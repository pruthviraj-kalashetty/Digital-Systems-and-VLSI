# **Required Time**

* **Overview**

Required Time is the time by which data must arrive at a timing point to satisfy the timing requirement. In STA, it is compared with the actual **Arrival Time** to calculate **Slack**.

* **Definition**

Required Time is the **latest allowed arrival time for setup analysis** or the **earliest allowed arrival time for hold analysis**.

In simple words:

> **Arrival Time = When data actually arrives**  
> **Required Time = When data is allowed to arrive**

* **Why is it needed?**

STA needs Required Time to answer:

- Is the data arriving early enough?
- Is the data arriving too late?
- Is there enough timing margin?
- Does the path have positive or negative slack?

Without Required Time, we cannot determine whether a timing path passes or fails.

---

* **Core Concept**

Consider a simple register-to-register path:

    Launch FF
        │
        │ Clock-to-Q
        ▼
    Combinational Logic
        │
        │ Data Delay
        ▼
    Capture FF

For **setup analysis**, data must arrive **before the capture clock edge**, with enough time for the capture flip-flop's setup requirement.

    Capture Clock Edge
            │
            ▼
    ────────┼──────────────────────────────► Time
            │
       Required Time
            ▲
            │
       Data must arrive
       before this point

For a simple same-clock example:

    Required Time = TCLK - tSETUP

---

* **Setup Required Time**

Setup analysis asks:

> "What is the latest time the data can arrive?"

For a simple same-clock path:

    Required Time(setup) = TCLK - tSETUP

Example:

    Clock Period = 10 ns
    Setup Time   = 1 ns

Therefore:

    Required Time = 10 - 1
                  = 9 ns

So the data must arrive at or before **9 ns**.

If:

    Arrival Time = 7 ns
    Required Time = 9 ns

Then:

    Setup Slack = Required Time - Arrival Time
                = 9 - 7
                = +2 ns

The path has 2 ns of setup timing margin.

---

* **Hold Required Time**

Hold analysis asks:

> "What is the earliest time the new data is allowed to arrive?"

For a simple same-clock path:

    Required Time(hold) = tHOLD

Example:

    Hold Time = 1 ns

Therefore:

    Required Time = 1 ns

If:

    Arrival Time = 3 ns
    Required Time = 1 ns

Then:

    Hold Slack = Arrival Time - Required Time
               = 3 - 1
               = +2 ns

The path satisfies the hold requirement.

---

* **Timing Diagram**

### Setup

    Launch Edge                         Capture Edge
         │                                  │
         ▼                                  ▼
    ─────┼──────────────────────────────────┼──────► Time
         │                         │
         │                         │
         │                    Required Time
         │                         │
         └────── Data Path ────────┘
                          Arrival Time

    Arrival Time ≤ Required Time
    → Setup requirement satisfied

### Hold

    Capture Edge
         │
         ▼
    ─────┼──────────────────────────────────────────► Time
         │
         │── Hold Window ──│
         │                 │
       Edge          Required Time
         
         Data must NOT arrive before
         the required hold time.

---

* **Important Terms**

| Term | Meaning |
|---|---|
| Arrival Time | Time at which data reaches the endpoint |
| Required Time | Allowed timing limit for data arrival |
| Setup Required Time | Latest allowed data arrival |
| Hold Required Time | Earliest allowed data arrival |
| Setup Slack | Required Time − Arrival Time |
| Hold Slack | Arrival Time − Required Time |
| Capture Edge | Clock edge where destination register captures data |

---

* **Formula**

### Setup

    Required Time(setup) = TCLK - tSETUP

    Setup Slack = Required Time - Arrival Time

### Hold

    Required Time(hold) = tHOLD

    Hold Slack = Arrival Time - Required Time

These are simplified formulas for a basic same-clock path.

Real STA can also include clock skew, clock uncertainty, input/output delays, clock latency, and timing exceptions.

---

* **Simple Example**

Given:

    Clock Period = 10 ns
    Setup Time   = 1 ns
    Arrival Time = 7 ns

### Step 1 — Find Required Time

    Required Time = 10 - 1
                  = 9 ns

### Step 2 — Calculate Slack

    Setup Slack = 9 - 7
                = +2 ns

Therefore:

    Arrival Time  = 7 ns
    Required Time = 9 ns
    Slack         = +2 ns

The data arrives 2 ns before the latest allowed time.

---

* **STA Connection**

Required Time is one of the three important quantities in STA:

    Arrival Time
          │
          ▼
    ┌─────────────┐
    │ Compare     │
    │ AT vs RT    │
    └──────┬──────┘
           │
           ▼
        Slack

For setup:

    Slack = Required Time - Arrival Time

For hold:

    Slack = Arrival Time - Required Time

This connects directly to the previous topic:

    Timing Path
        ↓
    Arrival Time
        ↓
    Required Time
        ↓
    Slack
        ↓
    Timing Pass / Violation

---

* **RTL Relevance**

RTL structure affects the data path delay.

For example:

    Register
       │
       ▼
    Logic 1
       │
       ▼
    Logic 2
       │
       ▼
    Logic 3
       │
       ▼
    Register

More combinational logic can increase the **Arrival Time**.

If Arrival Time becomes greater than the Required Time:

    Setup Slack < 0

This creates a **setup timing violation**.

Therefore, an RTL designer should avoid unnecessarily deep combinational paths.

---

* **Common Mistakes**

1. **Thinking Required Time is when data actually arrives**

   Required Time is a timing limit. Arrival Time is the actual calculated arrival.

2. **Using the same slack formula for setup and hold**

   Setup:

       Slack = Required - Arrival

   Hold:

       Slack = Arrival - Required

3. **Thinking Required Time is always the clock period**

   For setup, the setup requirement must also be considered.

4. **Ignoring the clock relationship**

   Real STA considers launch and capture clock timing, skew, uncertainty, and constraints.

---

* **Interview Questions**

**Q1. What is Required Time?**

Required Time is the allowed timing limit for data arrival at a timing endpoint.

**Q2. What is the setup Required Time in a simple same-clock path?**

    Required Time = TCLK - tSETUP

**Q3. What is the difference between Arrival Time and Required Time?**

Arrival Time tells when data reaches the endpoint. Required Time tells when data is allowed to arrive.

**Q4. How is setup slack calculated?**

    Setup Slack = Required Time - Arrival Time

**Q5. How is hold slack calculated?**

    Hold Slack = Arrival Time - Required Time

---

* **Quick Revision**

    Arrival Time  → When data arrives

    Required Time → When data is allowed to arrive

    Setup:
    Required = TCLK - tSETUP
    Slack = Required - Arrival

    Hold:
    Required = tHOLD
    Slack = Arrival - Required

    Positive Slack → Timing requirement satisfied
    Negative Slack → Timing violation

---

* **Summary**

Required Time defines the timing limit that the data path must satisfy.

For setup analysis, data must arrive **before the latest allowed time**.

For hold analysis, data must arrive **after the earliest allowed time**.

Required Time is compared with Arrival Time to calculate Slack, making it a fundamental concept in Static Timing Analysis.

---

* **References**

- *Digital Integrated Circuits* — Jan M. Rabaey, Anantha Chandrakasan, Borivoje Nikolić
- *Digital Design and Computer Architecture* — David Harris and Sarah Harris
- *CMOS VLSI Design* — Neil H. E. Weste and David Harris
- Synopsys — Static Timing Analysis documentation
- Cadence — Timing Analysis and Signoff documentation
