# **Propagation Delay**

* **Overview**

Propagation delay is the time taken for a change at the input of a logic circuit to appear as the corresponding change at its output.

It is an important timing parameter because real digital circuits do not respond instantaneously.

---

* **Definition**

Propagation delay is the time difference between an input transition and the corresponding output transition of a digital circuit.

It is commonly measured between the **50% voltage points** of the input and output transitions.

Two common types are:

- **tPLH** → Delay when output changes from LOW to HIGH.
- **tPHL** → Delay when output changes from HIGH to LOW.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand propagation delay because:

- It determines how fast logic can respond.
- It contributes to the delay of a timing path.
- It affects the maximum operating frequency.
- It affects setup timing.
- It helps identify critical paths.
- It is an important concept in STA.

---

* **Core Concept**

When an input changes, the output does not change immediately.

The basic relationship is:

**Input Transition → Logic Circuit → Output Transition**

For multiple logic gates:

    Input
      │
      ▼
    Gate 1
      │
      ▼
    Gate 2
      │
      ▼
    Gate 3
      │
      ▼
    Output

Each gate can add delay, so the complete path can take longer to produce the final output.

---

* **Timing Diagram**

For a LOW-to-HIGH output transition:

    Input:
    _________|‾‾‾‾‾‾‾‾‾‾
             ↑
          Input
         Transition
             │
             │<--- tPLH --->
             │
    Output:
    _____________|‾‾‾‾‾‾‾‾
                 ↑
              Output
             Transition

The time between the corresponding input and output reference points is the propagation delay.

For a HIGH-to-LOW transition, the delay is called **tPHL**.

---

* **Important Terms**

- **Propagation Delay (tpd)** → Time taken for an input change to appear at the output.
- **tPLH** → LOW-to-HIGH output propagation delay.
- **tPHL** → HIGH-to-LOW output propagation delay.
- **Cell Delay** → Delay introduced by a standard-cell logic element.
- **Path Delay** → Total delay through a timing path.
- **Interconnect Delay** → Delay caused by physical wiring.

---

* **Formula**

**tpd = max(tPLH, tPHL)**

Where:

- **tpd** = Worst-case propagation delay.
- **tPLH** = LOW-to-HIGH propagation delay.
- **tPHL** = HIGH-to-LOW propagation delay.

For a simplified timing path:

**Tpath ≈ Cell Delays + Interconnect Delays**

---

* **Simple Example**

Given:

- tPLH = **80 ps**
- tPHL = **100 ps**

Therefore:

**tpd = max(80 ps, 100 ps)**

**tpd = 100 ps**

So, the worst-case propagation delay is **100 ps**.

---

* **STA Connection**

In STA, propagation delay contributes to the **data-path delay**.

A simplified path is:

    Launch FF
        │
        ▼
    Combinational Logic
        │
        ▼
    Capture FF

The data arrival time depends on delays such as:

- Clock-to-Q delay.
- Combinational cell delay.
- Interconnect delay.

A larger propagation delay means the data arrives later at the capture element.

Therefore:

**Higher Path Delay → Later Arrival → Lower Setup Slack**

If data arrives too late, a **setup violation** can occur.

---

* **RTL Relevance**

At RTL, the engineer mainly describes functionality rather than the exact physical propagation delay.

For example:

    always_comb
        y = a & b;

This describes the logic function. The actual delay depends on the synthesized standard cells, loading, interconnect, and operating conditions.

An RTL engineer should therefore:

- Avoid unnecessarily deep combinational logic.
- Understand critical paths.
- Use pipelining when required.
- Consider timing when designing large datapaths.

---

* **Common Mistakes**

- Assuming output changes instantly after an input change.
- Confusing propagation delay with contamination delay.
- Assuming tPLH and tPHL are always equal.
- Ignoring interconnect delay in real ASIC timing.
- Assuming RTL simulation alone gives the actual ASIC propagation delay.

---

* **Interview Questions**

**1. What is propagation delay?**

**Answer:**

Propagation delay is the time between an input transition and the corresponding output transition of a digital circuit.

---

**2. What are tPLH and tPHL?**

**Answer:**

- **tPLH** → Output LOW-to-HIGH propagation delay.
- **tPHL** → Output HIGH-to-LOW propagation delay.

---

**3. Why can tPLH and tPHL be different?**

**Answer:**

The pull-up and pull-down transistor networks can have different characteristics, resulting in different rising and falling delays.

---

**4. How does propagation delay affect setup timing?**

**Answer:**

Higher propagation delay causes the data to arrive later at the capture element, reducing setup slack and potentially causing a setup violation.

---

**5. How can a long propagation delay be reduced at the RTL level?**

**Answer:**

Possible methods include reducing combinational logic depth, optimizing the logic structure, and using pipelining where appropriate.

---

* **Quick Revision**

- **Propagation Delay** → Time between input and corresponding output transition.
- **tPLH** → LOW → HIGH delay.
- **tPHL** → HIGH → LOW delay.
- **tpd = max(tPLH, tPHL)**.
- Larger path delay → Later data arrival.
- Larger delay can reduce setup slack.
- Propagation delay is analyzed in STA.
- RTL describes functionality; actual cell/interconnect delays come from implementation and timing analysis.

---

* **Summary**

Propagation delay represents how long a digital circuit takes to respond to an input transition. It contributes to the total data-path delay and directly affects timing performance.

For an ASIC RTL engineer, understanding propagation delay helps in designing efficient combinational logic, identifying timing-critical paths, and understanding setup timing and STA reports.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Static Timing Analysis and Timing Constraints documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
