# **Contamination Delay**

* **Overview**

Contamination delay is the minimum time after an input changes before the output of a logic circuit can begin to change.

It represents the **earliest possible output response** of a digital circuit.

---

* **Definition**

Contamination delay (**tcd**) is the minimum propagation time from an input transition to the first observable change at the output.

It is different from propagation delay, which generally represents the time required for the output to complete its transition.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand contamination delay because:

- It is important for **hold-time analysis**.
- It determines how quickly new data can start affecting the output.
- It helps understand minimum delay paths.
- It is useful for understanding hold violations in STA.
- It complements propagation delay in timing analysis.

---

* **Core Concept**

The key difference is:

**Contamination Delay → Earliest output change**

**Propagation Delay → Latest/complete output response**

A simple path is:

    Input
      │
      ▼
    Logic
      │
      ▼
    Output

After the input changes:

    Input changes
         │
         │<---- tcd ---->
         │
         ▼
    Output can begin changing

The output does not start changing before the contamination delay has elapsed.

---

* **Timing Diagram**

    Input:
    _________|‾‾‾‾‾‾‾‾‾‾
             ↑
        Input Change
             │
             │<-- tcd -->
             │
    Output:
    _____________|‾‾‾‾‾‾
                 ↑
          Earliest Output
             Change

`tcd` represents the minimum delay before the output can begin changing.

---

* **Important Terms**

- **Contamination Delay (tcd)** → Minimum delay before an output can start changing.
- **Propagation Delay (tpd)** → Delay associated with the output completing its transition.
- **Minimum Delay Path** → Path with the smallest possible data delay.
- **Hold Time** → Time for which data must remain stable after the capture clock edge.
- **Hold Violation** → Occurs when new data reaches the capture element too early.

---

* **Formula**

For a simplified combinational path:

**t<sub>cd,path</sub> = Σ Minimum Cell Delays + Σ Minimum Interconnect Delays**

Where:

- **tcd,path** = Minimum delay through the path.
- **Minimum Cell Delay** = Earliest delay contributed by each logic cell.
- **Minimum Interconnect Delay** = Earliest delay contributed by the interconnect.

The important relationship is:

**Contamination Delay < Propagation Delay**

for the same path under normal timing definitions.

---

* **Simple Example**

Consider a logic path with:

- Gate 1 contamination delay = **0.2 ns**
- Gate 2 contamination delay = **0.3 ns**

Ignoring interconnect delay:

**tcd = 0.2 + 0.3**

**tcd = 0.5 ns**

Therefore, the output cannot begin changing before approximately **0.5 ns** after the input transition under the given conditions.

---

* **STA Connection**

Contamination delay is especially important in **hold analysis**.

Consider:

    Launch FF
       │
       │ Clock-to-Q
       ▼
    Combinational Logic
       │
       │ Minimum Data Delay
       ▼
    Capture FF

If the new data reaches the capture flip-flop too early, it may change the captured value before the required hold time has passed.

Therefore:

**Very Small Minimum Delay → Earlier Data Arrival → Possible Hold Violation**

A simplified hold relationship is:

**Launch Clock-to-Q + Minimum Data Path Delay ≥ Hold Requirement**

Clock skew and other timing effects are also included in real STA calculations.

---

* **RTL Relevance**

At RTL, contamination delay is not normally specified directly in functional code.

However, RTL structure can influence minimum data-path delay after synthesis.

An RTL engineer should understand that:

- Very short paths can create hold problems.
- Removing logic from a path can reduce its minimum delay.
- Adding pipeline or bypass paths can create short timing paths.
- Hold problems are usually associated with data arriving **too early**, not too late.

---

* **Common Mistakes**

- Confusing contamination delay with propagation delay.
- Thinking contamination delay represents the time for the output to fully change.
- Associating contamination delay mainly with setup analysis.
- Forgetting that very short paths can cause hold violations.
- Assuming zero delay in real hardware.

---

* **Interview Questions**

**1. What is contamination delay?**

**Answer:**

Contamination delay is the minimum time after an input transition before the output can begin changing.

---

**2. What is the difference between contamination delay and propagation delay?**

**Answer:**

Contamination delay represents the **earliest output change**, while propagation delay represents the delay associated with the output reaching its corresponding final transition.

---

**3. Which timing check is mainly affected by contamination delay?**

**Answer:**

Contamination delay is mainly important for **hold-time analysis** because it determines how early new data can reach the capture flip-flop.

---

**4. What happens if the minimum data-path delay is too small?**

**Answer:**

New data may reach the capture flip-flop too early and overwrite the previous data before the hold requirement is satisfied, causing a hold violation.

---

**5. Is contamination delay normally written directly in RTL?**

**Answer:**

No. Synthesizable RTL primarily describes functionality. Actual minimum cell and interconnect delays are obtained from implementation and timing libraries and analyzed by STA.

---

* **Quick Revision**

- **Contamination Delay → Earliest output change**
- It is a **minimum delay**.
- **Propagation Delay → Output transition delay**
- Contamination delay is important for **hold analysis**.
- Very small minimum delay → possible **hold violation**.
- It depends on the minimum delays of cells and interconnects.
- RTL does not normally specify physical contamination delay directly.
- STA uses minimum-delay information for hold checks.

---

* **Summary**

Contamination delay is the minimum time required before a circuit output can begin responding to an input change.

For an ASIC RTL engineer, its main importance is understanding **hold timing**: if data travels through a path too quickly, it can reach the capture flip-flop too early and cause a hold violation.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Static Timing Analysis and Timing Constraints documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
