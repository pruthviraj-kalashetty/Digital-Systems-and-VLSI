# **Clock-to-Q Delay**

* **Overview**

Clock-to-Q delay is the time taken by a flip-flop to produce a valid output change after the active clock edge.

It is a key part of the data-path delay between a launch flip-flop and a capture flip-flop.

---

* **Definition**

Clock-to-Q delay (**tCQ**) is the time between the active clock edge at a flip-flop and the corresponding transition at its Q output.

It is commonly measured from the 50% point of the clock transition to the 50% point of the Q transition.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand clock-to-Q delay because:

- It contributes to the total data-path delay.
- It affects setup timing.
- It affects the maximum operating frequency.
- It appears in STA timing calculations.
- It helps understand how data moves from one register to another.

---

* **Core Concept**

When the active clock edge arrives, a flip-flop does not change its Q output instantaneously.

The sequence is:

    Clock Edge
        │
        ▼
    Flip-Flop
        │
        │  tCQ
        ▼
      Q Output

Therefore:

**Clock Edge → Clock-to-Q Delay → Q Changes**

For a positive-edge-triggered flip-flop, the process is:

    Rising Clock Edge
          ↓
       Flip-Flop
          ↓
       tCQ delay
          ↓
       Q changes

---

* **Timing Diagram**

    Clock:
    ________/‾‾‾‾‾‾‾‾\________
             ↑
          Active Edge
             │
             │<--- tCQ --->
             │
    Q:
    _____________/‾‾‾‾‾‾‾‾‾‾
                  ↑
              Q Changes

The time between the active clock edge and the corresponding Q transition is **clock-to-Q delay**.

---

* **Important Terms**

- **tCQ** → Clock-to-Q delay.
- **Launch Flip-Flop** → Flip-flop that launches data into the data path.
- **Q Output** → Output of the flip-flop.
- **Active Clock Edge** → Clock edge that causes the flip-flop to capture data.
- **Data Path** → Logic path through which launched data travels.
- **Capture Flip-Flop** → Flip-flop that receives and captures the data.

---

* **Formula**

For a simple register-to-register path:

**Data Arrival Time = Launch Edge + tCQ + Data Path Delay**

Where:

- **Launch Edge** = Time at which the launch flip-flop receives its active clock edge.
- **tCQ** = Clock-to-Q delay.
- **Data Path Delay** = Delay through combinational logic and interconnect.

A simplified setup condition is:

**Tclk ≥ tCQ + tData + tSetup**

Where:

- **Tclk** = Clock period.
- **tCQ** = Clock-to-Q delay.
- **tData** = Combinational data-path delay.
- **tSetup** = Setup time of the capture flip-flop.

---

* **Simple Example**

Given:

- Clock period = **10 ns**
- Clock-to-Q delay = **1 ns**
- Combinational delay = **6 ns**
- Setup time = **1 ns**

Check the setup timing:

**Required time = 10 ns**

**Data arrival time = 1 + 6 = 7 ns**

Setup requirement:

**7 + 1 ≤ 10 ns**

**8 ns ≤ 10 ns**

Therefore, the setup timing requirement is satisfied with:

**Setup Slack = 10 − 8 = 2 ns**

---

* **STA Connection**

Clock-to-Q delay is a major component of a register-to-register timing path.

    Launch FF
       │
       │ tCQ
       ▼
    Combinational
       Logic
       │
       │ tData
       ▼
    Capture FF

For setup analysis:

**tCQ + tData + tSetup ≤ Tclk**

A larger clock-to-Q delay increases data arrival time and reduces setup slack.

Therefore:

**Higher tCQ → Later Arrival → Lower Setup Slack**

---

* **RTL Relevance**

At RTL, the engineer normally does not specify the physical clock-to-Q delay of a flip-flop.

For example:

    always_ff @(posedge clk)
        q <= d;

This describes the sequential behavior.

The actual clock-to-Q delay is determined by the selected standard cell and operating conditions and is analyzed during STA.

An RTL engineer should understand tCQ when:

- Designing pipelined datapaths.
- Analyzing timing paths.
- Understanding setup violations.
- Reading STA reports.
- Estimating timing budgets.

---

* **Common Mistakes**

- Thinking Q changes exactly at the clock edge.
- Confusing clock-to-Q delay with setup time.
- Forgetting to include tCQ in setup timing calculations.
- Assuming tCQ is the same for every flip-flop.
- Confusing clock-to-Q delay with combinational logic delay.

---

* **Interview Questions**

**1. What is clock-to-Q delay?**

**Answer:**

Clock-to-Q delay is the time between the active clock edge of a flip-flop and the corresponding transition at its Q output.

---

**2. Why is clock-to-Q delay important in setup analysis?**

**Answer:**

It contributes to data arrival time. A larger tCQ causes data to arrive later and reduces setup slack.

---

**3. Where does clock-to-Q delay occur in a timing path?**

**Answer:**

It occurs immediately after the launch flip-flop's active clock edge and before the combinational data-path delay.

---

**4. What is the difference between clock-to-Q delay and setup time?**

**Answer:**

Clock-to-Q delay is the time taken for the flip-flop output to respond after the clock edge. Setup time is the minimum time the input data must be stable before the capture clock edge.

---

**5. What happens if clock-to-Q delay increases?**

**Answer:**

Data arrives later at the capture flip-flop, reducing setup slack and potentially causing a setup violation.

---

* **Quick Revision**

- **tCQ** → Time from active clock edge to Q transition.
- tCQ occurs at the **launch flip-flop**.
- It contributes to data arrival time.
- **Arrival ≈ Launch Edge + tCQ + Data Path Delay**
- Setup condition: **Tclk ≥ tCQ + tData + tSetup**
- Higher tCQ → Later data arrival.
- Higher tCQ → Lower setup slack.
- Actual tCQ comes from the flip-flop cell timing characteristics.

---

* **Summary**

Clock-to-Q delay is the time required for a flip-flop's Q output to respond after its active clock edge.

For an ASIC RTL engineer, tCQ is important because it forms part of the register-to-register data path and directly affects setup timing, maximum frequency, and STA analysis.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Static Timing Analysis and Timing Constraints documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
