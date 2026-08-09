# **Finite State Machine (FSM) Introduction**

* **Overview**

A **Finite State Machine (FSM)** is a sequential logic model used to design digital systems whose output depends on the current state and input signals. An FSM changes from one state to another based on clock signals and input conditions. It is one of the most important concepts in digital design, FPGA, ASIC, RTL design, and VLSI systems.

---

* **Definition**

A **Finite State Machine (FSM)** is a sequential logic circuit that consists of a finite number of states and transitions between those states. The next state of the machine depends on the present state and the input signals, while the output depends on either the present state alone or both the present state and the inputs.

---

* **Purpose**
  - To control the sequence of operations in digital systems.
  - To model systems that change between different states.
  - To simplify the design of complex sequential circuits.
  - To implement control logic efficiently.

---

* **Importance**
  - It is the foundation of sequential circuit design.
  - It is widely used in digital controllers and processors.
  - It simplifies the implementation of complex control logic.
  - It is essential in FPGA, ASIC, RTL, and VLSI designs.

---

* **Working Principle**
  - An FSM operates by moving between predefined states.
  - At every clock edge, the machine checks the input conditions.
  - Based on the current state and inputs, it decides the next state.
  - The output is generated according to the FSM type:
    - **Moore FSM** → Output depends only on the present state.
    - **Mealy FSM** → Output depends on the present state and inputs.
  - This process continues until the system is reset or powered off.

---

* **Circuit Description**
  - A Finite State Machine consists of:
    - State Register (Flip-Flops).
    - Next State Logic.
    - Output Logic.
    - Clock Signal.
    - Reset Signal.
  - The State Register stores the current state.
  - The Next State Logic determines the upcoming state.
  - The Output Logic generates the output based on the FSM type.

---

* **Truth Table:**

| Present State | Input | Next State | Output |
|---------------|-------|------------|--------|
| S0 | 0 | S0 | 0 |
| S0 | 1 | S1 | 0 |
| S1 | 0 | S0 | 1 |
| S1 | 1 | S1 | 1 |

*(Example FSM truth table. Actual truth tables depend on the FSM design.)*

---

* **Boolean Expression**

There is **no single Boolean expression** for an FSM. The Boolean equations depend on the **state transition logic** and **output logic** of the specific FSM being designed.

---

* **Input and Output Description**
  - Inputs:-
    - Clock (CLK)
    - Reset (RST)
    - External Input(s) (X, A, B, etc.)
  - Outputs:-
    - Output Signal(s) (Y, Z, etc.)

  - **Clock (CLK)** synchronizes all state transitions.
  - **Reset (RST)** initializes the FSM to its starting state.
  - **Input Signals** determine state transitions.
  - **Output Signals** are generated based on the current state or both state and inputs.

---

* **Working Example**
  - Consider a simple FSM with two states:
    - **S0** → Idle State
    - **S1** → Active State

Initial State:

- Present State = **S0**
- Input = **1**

Output:

- FSM transitions from **S0 → S1**.

Another Example:

- Present State = **S1**
- Input = **0**

Output:

- FSM transitions from **S1 → S0**.

---

* **Applications**

  *Finite State Machines are used in:*

  - Traffic Light Controllers.
  - Vending Machines.
  - Washing Machines.
  - Elevator Controllers.
  - UART Controllers.
  - Sequence Detectors.
  - Communication Protocols.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Easy to design and understand.
  - Provides predictable system behavior.
  - Simplifies complex control logic.
  - Suitable for synchronous digital systems.
  - Easy to implement using Verilog or VHDL.

---

* **Limitations**
  - Large FSMs require many states.
  - State complexity increases hardware usage.
  - Modifying large FSMs can be difficult.
  - Complex designs require careful state optimization.

---

* **Real-World Example**
  - ATM Machines.
  - Traffic Signal Controllers.
  - Automatic Washing Machines.
  - Digital Locks.
  - Communication Controllers.

---

* **Key Points**
  - FSM stands for **Finite State Machine**.
  - It is a **Sequential Logic Circuit**.
  - State transitions occur on clock edges.
  - Consists of State Register, Next State Logic, and Output Logic.
  - Two main types:
    - Moore FSM.
    - Mealy FSM.
  - Widely used in FPGA, ASIC, RTL, and VLSI designs.

---

* **Interview Questions**

**1. What is a Finite State Machine (FSM)?**

**Answer:**

A Finite State Machine is a sequential logic circuit that transitions between a finite number of states based on input signals and clock events.

---

**2. Why is an FSM called "Finite"?**

**Answer:**

Because it contains only a limited (finite) number of predefined states.

---

**3. What are the main components of an FSM?**

**Answer:**

- State Register.
- Next State Logic.
- Output Logic.
- Clock.
- Reset.

---

**4. What are the two types of FSM?**

**Answer:**

- Moore FSM.
- Mealy FSM.

---

**5. What is the difference between Moore and Mealy FSM?**

**Answer:**

- **Moore FSM:** Output depends only on the current state.
- **Mealy FSM:** Output depends on both the current state and the input.

---

**6. Why are Flip-Flops used in an FSM?**

**Answer:**

Flip-Flops store the current state of the FSM.

---

**7. Where are FSMs commonly used?**

**Answer:**

FSMs are used in traffic light controllers, vending machines, communication protocols, processors, FPGA, ASIC, and embedded systems.

---

**8. Why are FSMs important in RTL design?**

**Answer:**

FSMs provide a structured and efficient way to design control logic, making RTL circuits easier to implement, verify, and synthesize.

---

* **Quick Revision**
  - FSM → Finite State Machine
  - Circuit Type → Sequential Logic
  - Stores → Current State
  - Changes State → On Clock Edge
  - Main Components → State Register, Next State Logic, Output Logic
  - Types → Moore FSM, Mealy FSM
  - Applications → Controllers, Processors, FPGA, ASIC, RTL

---

* **Summary**

A **Finite State Machine (FSM)** is a sequential logic circuit that transitions through a finite number of states based on clock signals and input conditions. It consists of a state register, next-state logic, and output logic, making it a fundamental building block for designing digital control systems. FSMs are extensively used in FPGA, ASIC, RTL, and VLSI applications because they provide a systematic and reliable approach to implementing sequential behavior.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Samir Palnitkar – *Verilog HDL*.
  - Neil H. E. Weste & David Harris – *CMOS VLSI Design*.
  - Neso Academy – Digital Electronics & FSM.
  - GeeksforGeeks – Finite State Machine.

