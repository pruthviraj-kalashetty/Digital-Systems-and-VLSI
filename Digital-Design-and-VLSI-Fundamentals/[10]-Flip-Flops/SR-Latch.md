# **SR Latch**

## **Overview**

An **SR Latch (Set-Reset Latch)** is a basic level-sensitive sequential logic circuit used to store one bit of binary information. It has two main inputs, **S (Set)** and **R (Reset)**, and two outputs, **Q** and **Q'**. Unlike a Flip-Flop, an SR Latch does not require a clock signal.

## **Definition**

An **SR Latch** is a 1-bit level-sensitive storage element that can set, reset, or hold its output depending on the Set and Reset inputs.

## **Why is it needed?**

* To store one bit of binary information.
* To provide basic memory functionality.
* To understand sequential logic.
* To build more advanced latches and Flip-Flops.
* To implement simple control and storage circuits.
* To provide the basic concept of feedback-based storage.
* To understand Set and Reset operations.

## **Working Principle**

The SR Latch uses **feedback** to maintain its previous state.

For a basic **NOR-gate SR Latch**:

**S = 0, R = 0 → Hold**

The previous state is retained.

**S = 1, R = 0 → Set**

The output becomes:

**Q = 1**

**S = 0, R = 1 → Reset**

The output becomes:

**Q = 0**

**S = 1, R = 1 → Invalid**

Both outputs are forced low in the NOR implementation, violating the complementary-output requirement and making the resulting stored state undefined when the inputs return to the hold condition.

Therefore:

**00 → Hold**

**01 → Reset**

**10 → Set**

**11 → Invalid**

* **Circuit Diagram:**

![SR_LATCH](Circuit-Images/sr-latch.png)

## **Truth Table**

For a basic active-high NOR-gate SR Latch:

| S | R | Q(next) | Operation |
|:---:|:---:|:---:|---|
| 0 | 0 | Q | Hold |
| 0 | 1 | 0 | Reset |
| 1 | 0 | 1 | Set |
| 1 | 1 | X | Invalid |

**X = Invalid / Undefined**

The truth table changes for NAND-gate implementations because NAND-based SR Latches generally use **active-low inputs**.

## **Boolean Expression**

For the valid operating conditions of an active-high NOR-based SR Latch:

**Q(next) = S + R'Q**

The invalid condition must be avoided:

**S = 1, R = 1**

The feedback term **R'Q** allows the latch to retain its previous state when both inputs are inactive.

## **Input & Output Description**

| Signal | Type | Description |
|---|---|---|
| S | Input | Set input |
| R | Input | Reset input |
| Q | Output | Normal output |
| Q' | Output | Complementary output |

The SR Latch does not require a clock input.

## **Working Example**

Assume initially:

**Q = 0**

### **Case 1: S = 0, R = 0**

The latch maintains its previous state:

**Q(next) = Q**

Therefore:

**Q = 0**

### **Case 2: S = 1, R = 0**

The Set input is activated:

**Q = 1**

The latch stores a logic HIGH.

### **Case 3: S = 0, R = 1**

The Reset input is activated:

**Q = 0**

The latch stores a logic LOW.

### **Case 4: S = 1, R = 1**

Both Set and Reset are activated.

For the basic NOR implementation, this is the invalid condition.

Therefore:

**S = 1, R = 1 → Invalid**

## **Applications**

* Basic Memory Elements.
* Set/Reset Control.
* Switch Debouncing.
* Control Circuits.
* Data Storage.
* Timing Circuits.
* Sequential Logic.
* State Storage.
* Control Signal Generation.
* Digital Systems.
* CMOS Storage Circuits.
* VLSI Design.

## **Advantages**

* Very simple circuit.
* Stores one bit of information.
* Easy to understand and implement.
* Provides direct Set and Reset control.
* Does not require a clock.
* Forms the basic building block for more advanced storage elements.
* Can be implemented using simple logic gates.

## **Limitations**

* Has an invalid input condition.
* The Set and Reset inputs must be controlled carefully.
* It is level-sensitive.
* It can be affected by input transitions and propagation delays.
* Not suitable for all synchronous storage applications.
* NAND and NOR implementations have different active input conventions.

## **Real-World Example**

An SR Latch can be used in a **switch debouncing circuit**.

When a mechanical switch is pressed, it may produce multiple rapid transitions instead of one clean transition. An SR Latch can be used to maintain a stable logical state after the switch changes.

For example:

**S = 1 → Q = 1**

After the Set signal is removed:

**S = 0, R = 0**

the latch continues to hold:

**Q = 1**

When the Reset signal is activated:

**R = 1 → Q = 0**

Therefore, the latch provides stable Set and Reset behavior.

## **Key Points**

* SR Latch stands for **Set-Reset Latch**.
* It is a **1-bit storage element**.
* It is **level-sensitive**.
* It does not require a clock.
* Main inputs are **S and R**.
* Main outputs are **Q and Q'**.
* **S = 0, R = 0 → Hold**.
* **S = 0, R = 1 → Reset**.
* **S = 1, R = 0 → Set**.
* **S = 1, R = 1 → Invalid** for the basic NOR implementation.
* It uses feedback to retain its previous state.
* It can be built using cross-coupled NOR or NAND gates.
* NOR-based SR Latches generally use active-high inputs.
* NAND-based SR Latches generally use active-low inputs.
* It is the basic building block for understanding latches and Flip-Flops.

## **Interview Questions**

**1. What is an SR Latch?**

**Answer:**

An SR Latch is a level-sensitive 1-bit storage element with Set and Reset inputs.

**2. What does SR stand for?**

**Answer:**

SR stands for **Set-Reset**.

**3. Does an SR Latch require a clock?**

**Answer:**

No. A basic SR Latch does not require a clock signal.

**4. What happens when S = 0 and R = 0?**

**Answer:**

The latch holds its previous state.

**5. What happens when S = 1 and R = 0?**

**Answer:**

The latch is set:

**Q = 1**

**6. What happens when S = 0 and R = 1?**

**Answer:**

The latch is reset:

**Q = 0**

**7. What happens when S = 1 and R = 1 in a NOR SR Latch?**

**Answer:**

It produces the invalid condition.

**8. Why is S = 1 and R = 1 invalid in a NOR SR Latch?**

**Answer:**

Both NOR outputs are forced LOW, so Q and Q' are no longer complementary. When the inputs return to the hold condition, the final state can become unpredictable.

**9. What is the difference between an SR Latch and an SR Flip-Flop?**

**Answer:**

An SR Latch is **level-sensitive and does not require a clock**, while an SR Flip-Flop is **edge-triggered and uses a clock**.

**10. What gates can be used to build an SR Latch?**

**Answer:**

An SR Latch can be built using **cross-coupled NOR gates or NAND gates**.

**11. What is feedback in an SR Latch?**

**Answer:**

Feedback means that the outputs are connected back to the inputs of the opposite logic gates, allowing the circuit to retain its previous state.

**12. What is the main limitation of an SR Latch?**

**Answer:**

The main limitation is its invalid input condition.

## **Quick Revision**

**Main Topic → Sequential Logic**

**Subtopic → SR Latch**

**Storage → 1 Bit**

**Inputs → S, R**

**Outputs → Q, Q'**

**Clock → Not Required**

**Type → Level-Sensitive**

**00 → Hold**

**01 → Reset**

**10 → Set**

**11 → Invalid**

**S → Set**

**R → Reset**

**Main Principle → Feedback**

**Basic Implementation → Cross-Coupled NOR/NAND Gates**

**Main Problem → Invalid Condition**

**SR Latch → Level Sensitive**

**SR Flip-Flop → Edge Sensitive**

## **Summary**

An **SR Latch** is a basic level-sensitive 1-bit storage element that uses feedback to retain information. It provides **Set, Reset, and Hold** operations depending on the input combination. In a basic NOR implementation, **S = 1 and R = 1** is the invalid condition. SR Latches form the foundation for understanding **D Latches, Flip-Flops, registers, memory elements, and sequential logic design**.

## **References**

* M. Morris Mano – *Digital Design*.
* Thomas L. Floyd – *Digital Fundamentals*.
* Ronald J. Tocci – *Digital Systems: Principles and Applications*.
* Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
* Neso Academy – Digital Electronics.
