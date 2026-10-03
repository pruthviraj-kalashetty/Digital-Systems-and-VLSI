# **Arrival Time**

* **Overview**

Arrival Time is the time at which a signal reaches a specific point in a timing path. In Static Timing Analysis (STA), the arrival time of data at the endpoint is calculated by adding the delays along the path.

---

* **Definition**

**Arrival Time** is the calculated time at which a signal reaches a timing point, such as a register input or output port, relative to the reference clock or timing startpoint.

For a register-to-register path, STA calculates how long the launched data takes to reach the capture register.

---

* **Why is it needed?**

Arrival Time is needed to:

- Determine when data actually reaches the endpoint.
- Perform setup analysis.
- Perform hold analysis.
- Compare actual arrival with required arrival time.
- Calculate timing slack.
- Identify timing violations.

The basic idea is:

    Arrival Time = When data actually arrives

---

* **Core Concept**

Consider a simple register-to-register path:

    Launch FF
        │
        │ Clock-to-Q Delay
        ▼
    Combinational Logic
        │
        │ Data Path Delay
        ▼
    Capture FF

After the launch clock edge:

1. The launch flip-flop produces the new data after its clock-to-Q delay.
2. The data travels through the combinational logic.
3. The data reaches the capture register.
4. STA calculates the time at which this happens.

Simplified:

    Arrival Time
    = Launch Time
    + Clock-to-Q Delay
    + Data Path Delay

---

* **Timing Diagram**

    Launch Clock Edge
           ↑
           │
    ───────┼──────────────────────────────────────► Clock
           │
           │
           └── tCQ ──► Data Path Delay ──► Arrival
                                              │
                                              ▼
                                          Capture FF

Example:

    Launch Edge
         │
         ▼
         ├── 1 ns ──► Q changes
         │
         ├──── 5 ns Data Path ────►
         │
         ▼
       Arrival
         = 6 ns

---

* **Important Terms**

| Term | Meaning |
|---|---|
| **Launch Time** | Reference time at which data is launched |
| **Clock-to-Q Delay (`tCQ`)** | Delay from the active clock edge to the launch register output |
| **Data Path Delay (`tDATA`)** | Delay through combinational logic and interconnect |
| **Arrival Time** | Time at which the signal reaches the endpoint |
| **Maximum Arrival Time** | Latest possible arrival, mainly used for setup analysis |
| **Minimum Arrival Time** | Earliest possible arrival, mainly used for hold analysis |
| **Endpoint** | Destination point where arrival time is evaluated |
| **Required Time** | Time by which the signal must arrive |
| **Slack** | Difference between required time and arrival time |

---

* **Formula**

For a simplified register-to-register path:

    Arrival Time
    = Launch Time
    + tCQ
    + tDATA

If the launch clock edge is considered time zero:

    Arrival Time
    = tCQ + tDATA

For setup analysis, maximum delays are used:

    Arrival(max)
    = Launch Time
    + tCQ(max)
    + tDATA(max)

For hold analysis, minimum delays are used:

    Arrival(min)
    = Launch Time
    + tCQ(min)
    + tDATA(min)

In real STA, clock network delays, skew, uncertainty, and timing constraints are also included.

---

* **Simple Example**

Consider:

    Launch FF → Combinational Logic → Capture FF

Given:

    Launch Time       = 0 ns
    Clock-to-Q Delay  = 1 ns
    Data Path Delay   = 5 ns

Therefore:

    Arrival Time
    = 0 + 1 + 5
    = 6 ns

So the data reaches the capture register at **6 ns** relative to the launch edge.

### Setup Example

Suppose:

    Required Time = 9 ns
    Arrival Time  = 6 ns

Then:

    Setup Slack
    = Required Time − Arrival Time
    = 9 − 6
    = +3 ns

The setup requirement is satisfied.

---

* **Maximum and Minimum Arrival Time**

STA considers different delay values depending on the timing check.

### Maximum Arrival Time

Used mainly for setup analysis.

    Launch FF
        │
        │ Maximum tCQ
        ▼
    Data Path
        │
        │ Maximum Delay
        ▼
    Capture FF

The goal is to determine the **latest possible arrival**.

---

### Minimum Arrival Time

Used mainly for hold analysis.

    Launch FF
        │
        │ Minimum tCQ
        ▼
    Data Path
        │
        │ Minimum Delay
        ▼
    Capture FF

The goal is to determine the **earliest possible arrival**.

Therefore:

    Setup → Maximum Arrival

    Hold → Minimum Arrival

---

* **STA Connection**

Arrival Time is one of the fundamental quantities calculated by STA.

A simplified timing analysis is:

    Timing Path
         ↓
    Calculate Path Delays
         ↓
    Calculate Arrival Time
         ↓
    Calculate Required Time
         ↓
    Compare
         ↓
    Slack
         ↓
    Pass / Violation

For setup:

    Setup Slack
    = Required Time − Arrival Time

For hold:

    Hold Slack
    = Arrival Time − Required Time

Therefore, Arrival Time and Required Time work together to determine timing slack.

---

* **RTL Relevance**

RTL determines the combinational logic and register structure that eventually form timing paths.

For example:

    always @(posedge clk)
        q <= a & b;

The synthesized hardware may contain:

    Launch FF
        │
        ▼
       AND
        │
        ▼
    Capture FF

Adding more logic between registers can increase the data-path delay and therefore increase arrival time.

For example:

    FF → AND → OR → MUX → FF

generally has a longer data path than:

    FF → AND → FF

A longer maximum path can increase the maximum arrival time and create setup-timing pressure.

---

* **Common Mistakes**

- Thinking Arrival Time means only the combinational delay.
- Forgetting clock-to-Q delay.
- Using maximum arrival time for hold analysis.
- Using minimum arrival time for setup analysis.
- Confusing Arrival Time with Required Time.
- Assuming a smaller arrival time is always better without considering the timing check.
- Ignoring clock-path effects in real STA analysis.

---

* **Interview Questions**

**1. What is Arrival Time?**

Arrival Time is the calculated time at which a signal reaches a specific timing point in the design.

**2. How is arrival time calculated in a simple register-to-register path?**

    Arrival Time
    = Launch Time + tCQ + Data Path Delay

**3. Which arrival time is important for setup analysis?**

Maximum arrival time, because setup analysis checks the latest possible data arrival.

**4. Which arrival time is important for hold analysis?**

Minimum arrival time, because hold analysis checks the earliest possible data arrival.

**5. What is the difference between Arrival Time and Required Time?**

Arrival Time represents when data actually reaches the endpoint, while Required Time represents when the data is required to arrive.

---

* **Quick Revision**

    Arrival Time
    → When data reaches the endpoint.

    Basic formula:

    Arrival Time
    = Launch Time + tCQ + tDATA

    Setup:
    → Maximum Arrival Time

    Hold:
    → Minimum Arrival Time

    Setup Slack:

    Required Time − Arrival Time

    Hold Slack:

    Arrival Time − Required Time

    Key idea:

    Arrival Time = Actual timing

    Required Time = Allowed timing

    Slack = Timing margin

---

* **Summary**

Arrival Time tells STA when a signal reaches a timing point. It is calculated by propagating timing information through the timing path, including clock-to-Q delay and data-path delays. Maximum arrival time is mainly used for setup analysis, while minimum arrival time is mainly used for hold analysis. Arrival Time is then compared with Required Time to calculate slack and identify timing violations.

---

* **References**

- Harris, S. L. & Harris, D. M., *Digital Design and Computer Architecture*, Morgan Kaufmann.
- Weste, N. H. E. & Harris, D. M., *CMOS VLSI Design: A Circuits and Systems Perspective*, Pearson.
- Synopsys, *PrimeTime Static Timing Analysis* documentation.
- Cadence, *Static Timing Analysis* technical documentation.
- Neso Academy, Digital Electronics and VLSI Design lectures.
