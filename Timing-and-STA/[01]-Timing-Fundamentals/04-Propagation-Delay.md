# **Propagation Delay**

* **Overview**

Propagation delay is the time taken for a change at the input of a digital circuit or logic gate to produce the corresponding change at its output.

In digital and VLSI design, no real logic circuit responds instantaneously. When an input changes, the output changes after a finite amount of time. This delay is caused by factors such as transistor switching behavior, capacitive loading, resistance, logic depth, and interconnect effects.

Propagation delay is an important timing parameter because it directly affects the maximum operating frequency of a synchronous digital circuit.

---

* **Definition**

Propagation delay is the time interval between a specified transition at the input of a logic circuit and the corresponding transition at its output.

It is commonly measured between the **50% voltage points** of the input and output transitions.

There are two commonly considered propagation delays:

- **t<sub>PLH</sub>** → Propagation delay for an output transition from LOW to HIGH.
- **t<sub>PHL</sub>** → Propagation delay for an output transition from HIGH to LOW.

The propagation delay of a logic cell is often represented as:

**t<sub>pd</sub> = Maximum(t<sub>PLH</sub>, t<sub>PHL</sub>)**

---

* **Why is it needed?**

Propagation delay is important because it determines how quickly a digital circuit can respond to an input change.

It is needed to:

- Determine circuit operating speed.
- Calculate timing paths.
- Determine maximum operating frequency.
- Analyze combinational logic.
- Perform setup timing analysis.
- Identify critical paths.
- Estimate timing margins.
- Understand the delay introduced by logic gates.
- Optimize RTL architectures.
- Support Static Timing Analysis.

For an ASIC RTL engineer, propagation delay is important because excessive combinational delay can prevent a design from operating at its target clock frequency.

---

* **Key Concept**

The key idea is:

**Input changes → Logic processes the change → Output changes after a delay**

For example:

    Input
       │
       │ Transition
       ▼
    ┌─────────┐
    │   AND   │
    │   Gate  │
    └─────────┘
       │
       │ After propagation delay
       ▼
    Output

The output does not change exactly at the same instant as the input.

For a logic path containing multiple gates:

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

The total path delay is approximately related to the delays of the individual cells and interconnects.

More logic stages generally result in a longer timing path.

---

* **Working Principle**

Propagation delay can be understood step by step:

1. The input signal changes state.
2. The transistor network inside the logic cell begins switching.
3. Internal capacitances and load capacitances must charge or discharge.
4. The output voltage begins to change.
5. The output reaches the specified transition point.
6. The elapsed time between the input transition and output transition is the propagation delay.

For example, for a LOW-to-HIGH output transition:

    Input:
    _________|‾‾‾‾‾‾‾‾‾‾‾

              ↑
              │ Input transition
              │
              │<---- tPLH ---->
                              ↑
    Output:   ________________|‾‾‾‾‾‾‾‾‾

The output changes after a finite delay.

---

* **Timing Diagram**

A simplified propagation-delay diagram is:

    Input:
    _____________|‾‾‾‾‾‾‾‾‾‾‾‾
                 ↑
                 │
              50% Input
                 │
                 │<---- tpd ---->
                 │
    Output:
    ____________________|‾‾‾‾‾‾‾
                        ↑
                     50% Output

The propagation delay is measured between the specified reference points of the input and output transitions.

For a falling transition:

    Input:
    ‾‾‾‾‾‾‾‾‾‾|______________
               ↑
               │
               │<---- tPHL ---->
               │
    Output:
    ‾‾‾‾‾‾‾‾‾‾‾‾‾‾|__________
                    ↑

For a rising output transition:

**t<sub>PLH</sub> = Time from the input transition to the output LOW-to-HIGH transition**

For a falling output transition:

**t<sub>PHL</sub> = Time from the input transition to the output HIGH-to-LOW transition**

---

* **Important Parameters**

| Parameter | Description |
|---|---|
| **t<sub>PLH</sub>** | Delay associated with an output LOW-to-HIGH transition |
| **t<sub>PHL</sub>** | Delay associated with an output HIGH-to-LOW transition |
| **t<sub>pd</sub>** | Propagation delay, commonly represented by the worst-case of t<sub>PLH</sub> and t<sub>PHL</sub> |
| **Input Transition Time** | Time taken by the input signal to change between specified voltage levels |
| **Output Transition Time** | Time taken by the output signal to change between specified voltage levels |
| **Load Capacitance** | Capacitance driven by the output of the logic cell |
| **Logic Depth** | Number of logic stages in a timing path |
| **Interconnect Delay** | Delay caused by wires and physical interconnect |

Propagation delay can vary depending on:

- Input transition.
- Output load.
- Cell size.
- Logic function.
- Process corner.
- Supply voltage.
- Temperature.
- Interconnect characteristics.

---

* **Formula**

For a basic timing measurement:

**t<sub>pd</sub> = t<sub>output</sub> − t<sub>input</sub>**

Where:

- **t<sub>input</sub>** = Reference time of the input transition.
- **t<sub>output</sub>** = Reference time of the corresponding output transition.
- **t<sub>pd</sub>** = Propagation delay.

For two common transitions:

**t<sub>PLH</sub> = t<sub>output,LH</sub> − t<sub>input</sub>**

**t<sub>PHL</sub> = t<sub>output,HL</sub> − t<sub>input</sub>**

A simplified worst-case propagation delay can be represented as:

**t<sub>pd</sub> = max(t<sub>PLH</sub>, t<sub>PHL</sub>)**

For a multi-stage combinational path, a simplified representation is:

**T<sub>path</sub> ≈ Σ T<sub>cell</sub> + Σ T<sub>interconnect</sub>**

Where:

- **T<sub>path</sub>** = Total path delay.
- **T<sub>cell</sub>** = Delay contributed by each logic cell.
- **T<sub>interconnect</sub>** = Delay contributed by each interconnect segment.

In real STA, cell and interconnect delays depend on library models, input slew, output load, operating conditions, and other timing parameters.

---

* **Step-by-Step Analysis**

Consider a simple combinational path:

    Input → Gate 1 → Gate 2 → Gate 3 → Output

Assume:

- Gate 1 delay = **1 ns**
- Gate 2 delay = **2 ns**
- Gate 3 delay = **1.5 ns**
- Interconnect delay = **0.5 ns**

### Step 1 — Add Cell Delays

**T<sub>cell</sub> = 1 + 2 + 1.5**

**T<sub>cell</sub> = 4.5 ns**

### Step 2 — Add Interconnect Delay

**T<sub>path</sub> = 4.5 + 0.5**

**T<sub>path</sub> = 5 ns**

Therefore, the simplified total propagation delay of the path is:

**5 ns**

This means that after the input transition, the corresponding output transition occurs approximately 5 ns later under the given assumptions.

---

* **Example**

Consider a logic gate with:

**t<sub>PLH</sub> = 80 ps**

**t<sub>PHL</sub> = 100 ps**

The worst-case propagation delay is:

**t<sub>pd</sub> = max(80 ps, 100 ps)**

**t<sub>pd</sub> = 100 ps**

Therefore:

**Propagation Delay = 100 ps**

The falling output transition is slower than the rising output transition in this example.

---

* **Practical / RTL Relevance**

Propagation delay is not directly written as a fixed delay in normal synthesizable RTL.

For example:

    always_comb begin
        y = a & b;
    end

The RTL describes the logical behavior of the AND operation. The actual physical delay is determined later by synthesis, cell selection, physical implementation, parasitics, and operating conditions.

An RTL engineer should understand that:

- More combinational logic can increase path delay.
- Long logic chains can create critical paths.
- Complex arithmetic operations can create large timing paths.
- Pipelining can divide a long path into smaller timing stages.
- RTL structure can influence the synthesized logic and therefore timing.
- STA is used to determine the actual timing characteristics of the implemented design.

For example:

    Register
       │
       ▼
    Complex Logic
       │
       ▼
    Register

If the complex logic has excessive delay, the path may fail setup timing.

---

* **STA Relevance**

Propagation delay is a fundamental component of STA.

STA calculates timing through a path using delays associated with:

- Standard cells.
- Interconnects.
- Input transitions.
- Output loads.
- Operating conditions.
- Timing libraries.

A simplified timing path is:

    Launch FF
       │
       │ Clock-to-Q
       ▼
    Combinational Logic
       │
       │ Propagation Delay
       ▼
    Capture FF

The data arrival time depends on the delays along the path.

A simplified arrival-time relationship is:

**Arrival Time ≈ Launch Time + Clock-to-Q + Data Path Delay**

For a setup check, excessive propagation delay can cause:

**Arrival Time > Required Time**

which results in:

**Negative Slack**

Therefore:

**Large Propagation Delay → Larger Arrival Time → Reduced Setup Slack**

---

* **Common Mistakes**

- Assuming propagation delay is zero in real hardware.
- Confusing propagation delay with contamination delay.
- Assuming t<sub>PLH</sub> and t<sub>PHL</sub> are always identical.
- Ignoring interconnect delay.
- Ignoring load capacitance.
- Assuming RTL simulation delay represents actual ASIC timing.
- Treating gate delay as a fixed value under all conditions.
- Ignoring process, voltage, and temperature variations.
- Assuming reducing logic count always guarantees timing improvement.
- Ignoring input slew and output load effects in cell timing.

---

* **Best Practices**

- Minimize unnecessary combinational logic depth.
- Identify long and critical timing paths.
- Use appropriate pipelining for high-performance datapaths.
- Avoid unnecessarily complex combinational logic between registers.
- Understand that actual delays depend on implementation conditions.
- Use STA rather than RTL simulation alone for timing verification.
- Review cell and interconnect contributions in timing reports.
- Consider both setup and hold implications when optimizing paths.
- Use appropriate synthesis and implementation constraints.
- Optimize the RTL architecture when timing cannot be achieved through simple logic changes.

---

* **Applications**

Propagation delay is important in:

- Combinational Logic.
- ASIC Design.
- RTL Design.
- FPGA Design.
- Processor Datapaths.
- Arithmetic Circuits.
- Digital Logic Gates.
- Pipeline Design.
- Static Timing Analysis.
- Critical Path Analysis.
- Timing Closure.
- High-Speed Digital Systems.

---

* **Advantages**

Understanding propagation delay helps to:

- Determine circuit speed.
- Estimate timing-path performance.
- Identify critical paths.
- Determine maximum operating frequency.
- Improve RTL architecture.
- Optimize combinational logic.
- Understand STA reports.
- Analyze timing violations.
- Support timing closure.

---

* **Limitations**

Propagation delay cannot be represented by a single constant value for every operating condition.

It can vary because of:

- Process variation.
- Supply voltage variation.
- Temperature.
- Input slew.
- Output load.
- Cell size.
- Logic configuration.
- Interconnect parasitics.
- Manufacturing variations.

Therefore, realistic STA uses characterized timing libraries and multiple operating conditions rather than assuming one fixed delay.

---

* **Real-World Example**

Consider a processor datapath:

    Register
       │
       ▼
    ALU
       │
       ▼
    Multiplexer
       │
       ▼
    Comparator
       │
       ▼
    Register

Suppose the total combinational path becomes too long.

The data may not reach the destination register before the next capture clock edge.

This can cause a setup violation.

One possible architectural solution is pipelining:

    Register
       │
       ▼
      ALU
       │
    Register
       │
       ▼
     MUX
       │
    Register
       │
       ▼
   Comparator
       │
    Register

Pipelining reduces the amount of combinational logic that must be completed within a single clock period and can therefore improve the achievable operating frequency.

---

* **Key Points**

- Propagation delay is the time between an input transition and the corresponding output transition.
- It is commonly measured using specified voltage reference points, often 50% points.
- **t<sub>PLH</sub>** represents LOW-to-HIGH output propagation delay.
- **t<sub>PHL</sub>** represents HIGH-to-LOW output propagation delay.
- Worst-case propagation delay is commonly represented as **max(t<sub>PLH</sub>, t<sub>PHL</sub>)**.
- Propagation delay contributes to the total timing-path delay.
- Long combinational paths generally increase timing delay.
- Propagation delay affects setup timing.
- Larger path delay increases data arrival time.
- Excessive delay can produce negative setup slack.
- Actual ASIC delay depends on cells, interconnect, load, slew, PVT, and timing libraries.
- STA is used to analyze realistic timing delays.
- RTL simulation does not by itself determine actual ASIC propagation delay.

---

* **Interview Questions**

**1. What is propagation delay?**

**Answer:**

Propagation delay is the time between a specified transition at the input of a circuit and the corresponding transition at its output.

---

**2. What are t<sub>PLH</sub> and t<sub>PHL</sub>?**

**Answer:**

**t<sub>PLH</sub>** is the propagation delay associated with an output transition from LOW to HIGH.

**t<sub>PHL</sub>** is the propagation delay associated with an output transition from HIGH to LOW.

---

**3. Why are t<sub>PLH</sub> and t<sub>PHL</sub> different?**

**Answer:**

They can differ because the pull-up and pull-down transistor networks may have different characteristics, and their effective resistance, capacitance, loading, and operating conditions can be different.

---

**4. What is the effect of propagation delay on circuit performance?**

**Answer:**

Higher propagation delay increases the time required for data to travel through a logic path and can reduce the maximum operating frequency of the circuit.

---

**5. How does propagation delay affect setup timing?**

**Answer:**

Higher propagation delay increases data arrival time. If the data arrives later than the required time, setup slack becomes smaller and can eventually become negative.

---

**6. What is the difference between propagation delay and contamination delay?**

**Answer:**

Propagation delay represents the maximum delay for a signal to propagate through a logic path, while contamination delay represents the minimum time after an input change before the output can begin changing.

---

**7. Does RTL code contain the actual propagation delay of an ASIC gate?**

**Answer:**

Normally, synthesizable RTL describes functionality rather than the final physical propagation delay. Actual cell and interconnect delays are determined during synthesis and physical implementation and analyzed using STA.

---

**8. What factors affect propagation delay?**

**Answer:**

Important factors include:

- Input slew.
- Output load.
- Cell characteristics.
- Process.
- Voltage.
- Temperature.
- Interconnect parasitics.
- Logic structure.

---

**9. How can propagation delay be reduced in a digital design?**

**Answer:**

Possible methods include reducing logic depth, optimizing the RTL architecture, selecting suitable implementation structures, reducing excessive loading, and using pipelining when appropriate.

---

**10. Why is propagation delay important in STA?**

**Answer:**

STA uses cell and interconnect delays to calculate data arrival times. Excessive path delay can cause setup timing violations and reduce the maximum achievable operating frequency.

---

**11. What is the relationship between path delay and maximum frequency?**

**Answer:**

In a simplified synchronous design, a longer data path requires a longer clock period. Therefore, reducing the critical-path delay can allow a higher maximum operating frequency.

---

**12. Can propagation delay be the same for every input transition?**

**Answer:**

No. Delay can depend on the input transition, output transition, input slew, output load, cell characteristics, and operating conditions.

---

* **Quick Revision**

- **Propagation Delay** → Time between input transition and corresponding output transition.
- **t<sub>PLH</sub>** → LOW-to-HIGH output delay.
- **t<sub>PHL</sub>** → HIGH-to-LOW output delay.
- **Worst-Case t<sub>pd</sub>** → max(t<sub>PLH</sub>, t<sub>PHL</sub>).
- Propagation delay contributes to data-path delay.
- Higher path delay → Later data arrival.
- Later arrival → Lower setup slack.
- Excessive delay → Possible setup violation.
- Delay depends on load, slew, PVT, cells, and interconnect.
- RTL describes functionality; implementation determines actual timing.
- STA analyzes realistic cell and interconnect delays.
- Reducing critical-path delay can improve maximum operating frequency.

---

* **Summary**

Propagation delay is the time required for a signal transition to propagate through a digital circuit from its input to its corresponding output. It is commonly characterized using **t<sub>PLH</sub>** and **t<sub>PHL</sub>**.

In ASIC design, propagation delay contributes directly to data-path delay and therefore affects arrival time, setup slack, critical paths, and maximum operating frequency.

For an ASIC RTL engineer, understanding propagation delay is important for recognizing why long combinational paths create timing problems and why techniques such as logic optimization and pipelining may be required to achieve timing closure.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Jan M. Rabaey, Anantha Chandrakasan and Borivoje Nikolić – *Digital Integrated Circuits*.
- M. Morris Mano – *Digital Design*.
- Synopsys – Static Timing Analysis and Design Constraints documentation.
- Cadence – Digital Design and Timing Analysis documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
