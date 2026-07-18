# **Full Subtractor Using Half Subtractors**

* **What Problem Does It Solve**
  
  - A Full Subtractor using Half Subtractors is a digital combinational circuit.
  - It subtracts three 1-bit binary numbers (A, B, and Borrow-in (Bin)).
  - It produces a Difference (D) and a Borrow-out (Bout).
  - It is implemented using two Half Subtractors and one OR gate.

---
  
* **Why is it used**
  
  *A Full Subtractor using Half Subtractors is used because:*
  
  - It performs binary subtraction with a borrow input.
  - It is easy to design using basic digital building blocks.
  - It simplifies the implementation of binary subtraction.
  - It is used to build multi-bit subtractors.
  - It provides accurate Difference and Borrow outputs.

---
  
* **Where is it used**
  
   *A Full Subtractor using Half Subtractors is widely used in:*
  
    - CPUs (Processors).
    - ALU (Arithmetic Logic Unit).
    - Digital calculators.
    - Microcontrollers.
    - Arithmetic circuits.
    - Digital VLSI and RTL design.
    - FPGA and ASIC designs.
    - Binary subtraction circuits.
    - Circuit Diagram:

---

* **Circuit Diagram:**

![FULL_SUBCTRACTOr_USING_TWO_HALF_SUBCTRACTOR](Subctractors-Images/full-subctractor-using-two-half-subctractor.png)

---

* **Function of Inputs and Outputs**
  
  - A = Minuend (number from which B is subtracted).
  - B = Subtrahend (number to be subtracted).
  - Bin = Borrow input from the previous stage.
  - Difference (D) = Final subtraction result.
  - Borrow Out (Bout) = Final borrow sent to the next stage.

---

## Truth Table

| A | B | Bin | Half Subtractor 1<br>Difference1 | Half Subtractor 1<br>Borrow1 | Half Subtractor 2<br>Difference | Half Subtractor 2<br>Borrow2 | Final Borrow<br>(Bout) |
|:-:|:-:|:---:|:--------------------------------:|:----------------------------:|:-------------------------------:|:----------------------------:|:-----------------------:|
| 0 | 0 |  0  |                0                 |              0               |               0                 |              0               |            0            |
| 0 | 0 |  1  |                0                 |              0               |               1                 |              1               |            1            |
| 0 | 1 |  0  |                1                 |              1               |               1                 |              0               |            1            |
| 0 | 1 |  1  |                1                 |              1               |               0                 |              0               |            1            |
| 1 | 0 |  0  |                1                 |              0               |               1                 |              0               |            0            |
| 1 | 0 |  1  |                1                 |              0               |               0                 |              0               |            0            |
| 1 | 1 |  0  |                0                 |              0               |               0                 |              0               |            0            |
| 1 | 1 |  1  |                0                 |              0               |               1                 |              1               |            1            |

---

* **Boolean Expressions**
  
  - Difference (D) = A ⊕ B ⊕ Bin
  - Borrow Out (Bout) = A̅·B + A̅·Bin + B·Bin
 
---

* **Waveform / Timing Diagram:**

  ![FULL_SUBCTRACTOR_USING_TWO_HALF_SUBCTRACTOR Timing Waveform](Image/full_subctractor_using_two_half_subctractor_waveform.png)

