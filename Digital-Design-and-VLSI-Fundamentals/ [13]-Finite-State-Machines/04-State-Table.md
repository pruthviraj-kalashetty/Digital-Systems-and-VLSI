# **State Table**

* **Overview**

A **State Table** is a tabular representation of a Finite State Machine (FSM). It shows the present state, input conditions, next state, and output for every possible combination. A state table provides the same information as a state diagram but in a structured table format, making it easier to analyze and implement FSMs.

---

* **Definition**

A **State Table** is a table that describes the behavior of a Finite State Machine by listing the present state, input, next state, and corresponding output for every possible input condition.

---

* **Purpose**
  - To represent the behavior of an FSM in tabular form.
  - To define state transitions clearly.
  - To simplify FSM analysis and implementation.
  - To assist in writing RTL and Verilog code.

---

* **Importance**
  - Provides a clear and organized representation of an FSM.
  - Makes state transitions easy to understand.
  - Helps verify FSM behavior before implementation.
  - Serves as the basis for designing state diagrams and RTL code.

---

* **Working Principle**
  - The FSM starts in a present state.
  - An input is applied to the system.
  - Based on the present state and input, the next state is determined.
  - The corresponding output is generated.
  - On the next clock edge, the FSM moves to the next state, which becomes the new present state.

---

* **Circuit Description**
  - A State Table consists of:
    - Present State.
    - Input.
    - Next State.
    - Output.
  - Each row represents one possible state transition.
  - Every combination of present state and input is included in the table.

---

* **Circuit Diagram:**

![State Table Representation](Image/state-table.png)

---

* **Truth Table:**

| Present State | Input | Next State | Output |
|---------------|-------|------------|--------|
| S0 | 0 | S0 | 0 |
| S0 | 1 | S1 | 0 |
| S1 | 0 | S0 | 1 |
| S1 | 1 | S1 | 1 |

*(Example State Table. Actual values depend on the FSM design.)*

---

* **Boolean Expression**

There is **no single Boolean expression** for a State Table. The Boolean equations depend on the next-state logic and output logic of the specific FSM.

---

* **Input and Output Description**
  - Inputs:-
    - Clock (CLK)
    - Reset (RST)
    - External Input(s) (X, A, B, etc.)
  - Outputs:-
    - Output Signal(s) (Y, Z, etc.)

  - **Clock (CLK)** synchronizes state transitions.
  - **Reset (RST)** initializes the FSM to its starting state.
  - **Input Signals** determine the next state.
  - **Output Signals** are generated according to the FSM design.

---

* **Working Example**
  - Consider the following state table:

| Present State | Input | Next State | Output |
|---------------|-------|------------|--------|
| S0 | 0 | S0 | 0 |
| S0 | 1 | S1 | 0 |
| S1 | 0 | S0 | 1 |
| S1 | 1 | S1 | 1 |

Example:

- Present State = **S0**
- Input = **1**

Output:

- Next State = **S1**
- Output = **0**

Another Example:

- Present State = **S1**
- Input = **0**

Output:

- Next State = **S0**
- Output = **1**

---

* **Applications**

  *State Tables are used in:*

  - FSM Design.
  - Traffic Light Controllers.
  - Vending Machines.
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
  - Easy to understand and organize.
  - Represents all state transitions clearly.
  - Simplifies FSM verification.
  - Helps convert FSMs into RTL code.
  - Useful for simulation and debugging.

---

* **Limitations**
  - Large FSMs result in very large tables.
  - Difficult to manage when many states and inputs are present.
  - Less intuitive than a state diagram for visualizing behavior.

---

* **Real-World Example**
  - Traffic Signal Controller.
  - ATM Machine.
  - Elevator Controller.
  - Automatic Washing Machine.
  - Communication Controller.

---

* **Key Points**
  - A State Table is a tabular representation of an FSM.
  - It contains Present State, Input, Next State, and Output.
  - Every possible input condition is included.
  - Used before writing Verilog or VHDL code.
  - Helps verify FSM functionality.

---

* **Interview Questions**

**1. What is a State Table?**

**Answer:**

A State Table is a tabular representation of an FSM that lists the present state, input, next state, and output for every possible condition.

---

**2. Why is a State Table used?**

**Answer:**

It provides a structured representation of state transitions, making FSM analysis, verification, and implementation easier.

---

**3. What are the main columns of a State Table?**

**Answer:**

- Present State.
- Input.
- Next State.
- Output.

---

**4. What information does a State Table provide?**

**Answer:**

It shows how an FSM transitions from one state to another and what output is produced for each input condition.

---

**5. What is the difference between a State Table and a State Diagram?**

**Answer:**

A State Table represents FSM behavior in tabular form, whereas a State Diagram represents the same behavior graphically.

---

**6. Can a State Table represent both Moore and Mealy FSMs?**

**Answer:**

Yes. A State Table can represent both Moore and Mealy FSMs.

---

**7. Why is a State Table important in RTL design?**

**Answer:**

It helps designers convert FSM behavior into Verilog or VHDL code accurately and efficiently.

---

**8. Where are State Tables commonly used?**

**Answer:**

State Tables are commonly used in FPGA, ASIC, RTL design, embedded systems, communication protocols, and digital controllers.

---

* **Quick Revision**
  - Tabular representation of an FSM.
  - Columns → Present State, Input, Next State, Output.
  - Defines all possible state transitions.
  - Used before RTL coding.
  - Applicable to Moore and Mealy FSMs.

---

* **Summary**

A **State Table** is a structured tabular representation of a Finite State Machine that defines the relationship between the present state, input, next state, and output. It simplifies the analysis, verification, and implementation of sequential circuits and serves as an essential step before designing FSMs in Verilog, VHDL, FPGA, ASIC, and VLSI systems.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Samir Palnitkar – *Verilog HDL*.
  - Neso Academy – Finite State Machines.
  - GeeksforGeeks – State Table.

---

* **Waveform / Timing Diagram:**

![State Table Timing Waveform](Image/state_table_waveform.png)
