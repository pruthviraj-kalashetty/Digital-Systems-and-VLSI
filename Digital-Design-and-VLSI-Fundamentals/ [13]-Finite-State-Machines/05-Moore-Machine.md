# **Moore Machine**

* **Overview**

A **Moore Machine** is a type of Finite State Machine (FSM) in which the output depends **only on the current state** and not directly on the input signals. The output changes only when the FSM changes its state, usually on the active edge of the clock. Moore machines are widely used because they provide stable and predictable outputs.

---

* **Definition**

A **Moore Machine** is a sequential logic circuit in which the output is determined solely by the present state of the FSM. The input signals affect only the state transitions, while the output remains dependent only on the current state.

---

* **Purpose**
  - To generate stable outputs.
  - To implement sequential control logic.
  - To simplify FSM design.
  - To design reliable synchronous digital systems.

---

* **Importance**
  - Produces stable outputs independent of input glitches.
  - Easy to design and debug.
  - Widely used in FPGA, ASIC, and RTL design.
  - Suitable for control circuits requiring reliable outputs.

---

* **Working Principle**
  - The FSM starts in an initial state.
  - Input signals determine the next state.
  - On the active clock edge, the FSM moves to the next state.
  - The output is generated **only from the current state**.
  - Even if the inputs change, the output does not change until the state changes.

---

* **Circuit Description**
  - A Moore Machine consists of:
    - State Register (Flip-Flops).
    - Next State Logic.
    - Output Logic.
    - Clock Signal.
    - Reset Signal.
  - The State Register stores the current state.
  - The Next State Logic determines the next state using the current state and inputs.
  - The Output Logic depends **only on the current state**.

---

* **Circuit Diagram:**

![Moore Machine Block Diagram](Image/moore-machine.png)

---

* **Truth Table:**

| Present State | Input | Next State | Output |
|---------------|-------|------------|--------|
| S0 | 0 | S0 | 0 |
| S0 | 1 | S1 | 0 |
| S1 | 0 | S0 | 1 |
| S1 | 1 | S1 | 1 |

*(Example Moore Machine State Table. Actual values depend on the design.)*

---

* **Boolean Expression**

There is **no single Boolean expression** for a Moore Machine. The Boolean equations depend on the next-state logic and the output logic of the specific FSM.

---

* **Input and Output Description**
  - Inputs:-
    - Clock (CLK)
    - Reset (RST)
    - External Input(s) (X, A, B, etc.)
  - Outputs:-
    - Output Signal(s) (Y, Z, etc.)

  - **Clock (CLK)** controls state transitions.
  - **Reset (RST)** initializes the FSM to the starting state.
  - **Input Signals** determine the next state.
  - **Output Signals** depend only on the current state.

---

* **Working Example**
  - Consider an FSM with two states:

    - **S0 → Output = 0**
    - **S1 → Output = 1**

Initial State:

- Present State = **S0**
- Input = **1**

Output:

- Next State becomes **S1** after the clock edge.
- Output changes to **1** only after entering **S1**.

Another Example:

- Present State = **S1**
- Input = **0**

Output:

- Next State becomes **S0** after the clock edge.
- Output changes to **0** only after entering **S0**.

---

* **Applications**

  *Moore Machines are used in:*

  - Traffic Light Controllers.
  - Elevator Controllers.
  - Washing Machines.
  - Sequence Detectors.
  - Communication Controllers.
  - CPU Control Units.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Stable outputs.
  - Less sensitive to input glitches.
  - Easy to design and verify.
  - Predictable operation.
  - Reliable for synchronous systems.

---

* **Limitations**
  - May require more states than a Mealy Machine.
  - Output changes only after a state transition.
  - Can introduce one clock-cycle delay in output response.

---

* **Real-World Example**
  - Traffic Signal Controller.
  - Automatic Washing Machine.
  - Elevator Controller.
  - Digital Lock System.
  - Industrial Automation Controller.

---

* **Key Points**
  - Moore Machine is a type of FSM.
  - Output depends **only on the present state**.
  - Inputs affect only state transitions.
  - Output changes after the state changes.
  - Produces stable and glitch-free outputs.
  - Commonly used in FPGA, ASIC, RTL, and VLSI designs.

---

* **Interview Questions**

**1. What is a Moore Machine?**

**Answer:**

A Moore Machine is a Finite State Machine in which the output depends only on the current state.

---

**2. On what does the output of a Moore Machine depend?**

**Answer:**

The output depends only on the present state of the FSM.

---

**3. When does the output of a Moore Machine change?**

**Answer:**

The output changes only after the FSM changes to a new state, usually on the active clock edge.

---

**4. What is the main advantage of a Moore Machine?**

**Answer:**

It provides stable and glitch-free outputs because the output is independent of input changes.

---

**5. What is the main disadvantage of a Moore Machine?**

**Answer:**

It may require more states and can introduce a one clock-cycle delay in the output.

---

**6. What are the main components of a Moore Machine?**

**Answer:**

- State Register.
- Next State Logic.
- Output Logic.
- Clock.
- Reset.

---

**7. Where are Moore Machines commonly used?**

**Answer:**

They are used in traffic light controllers, sequence detectors, communication systems, FPGA, ASIC, and embedded systems.

---

**8. What is the difference between a Moore Machine and a Mealy Machine?**

**Answer:**

In a Moore Machine, the output depends only on the current state, whereas in a Mealy Machine, the output depends on both the current state and the input.

---

* **Quick Revision**
  - Type → Finite State Machine (FSM)
  - Output depends on → Current State Only
  - Inputs affect → Next State
  - Output changes → After State Transition
  - Stable and glitch-free outputs
  - Used in FPGA, ASIC, RTL, and VLSI systems

---

* **Summary**

A **Moore Machine** is a Finite State Machine in which the output depends only on the current state. The output changes only after a state transition occurs, making it stable and less sensitive to input changes. Due to its predictable behavior and reliable operation, the Moore Machine is widely used in FPGA, ASIC, RTL, embedded systems, and VLSI applications.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Samir Palnitkar – *Verilog HDL*.
  - Neso Academy – Finite State Machines.
  - GeeksforGeeks – Moore Machine.

---

* **Waveform / Timing Diagram:**

![Moore Machine Timing Waveform](Image/moore_machine_waveform.png)
