# **Full Adder Using Two Half Adders**

* **What Problem Does It Solve**
   - A Full Adder using Half Adders is a digital combinational circuit.
   - It adds three 1-bit binary numbers (A, B, and Carry-in (Cin)).
   - It produces a Sum (S) and a Carry-out (Cout).
   - It is implemented using two Half Adders and one OR gate.

---

* **Why is it used**
  
   *A Full Adder using Half Adders is used because:*
    - It adds two binary bits along with a carry input.
    - It is easy to design using basic digital building blocks.
    - It simplifies the implementation of binary addition.
    - It is used to build multi-bit adders.
    - It provides accurate Sum and Carry outputs.

---

* **Where is it used**
  
  *A Full Adder using Half Adders is widely used in:*
   - CPUs (Processors).
   - ALU (Arithmetic Logic Unit).
   - Digital calculators.
   - Microcontrollers.
   - Digital VLSI and RTL design.
   - FPGA and ASIC designs.
   - Binary arithmetic circuits.
   - Digital signal processing systems.
   - Circuit Diagram:

---

* **Circuit Diagram:**

![FULL_ADDER_USING_TWO_HALF_ADDER](Images/full-adder-using-two-half-adder.png)

---

* **Function of Inputs and Outputs**
  
  - A = First binary input bit.
  - B = Second binary input bit.
  - Cin = Carry input from the previous stage.
  - Sum (S) = Final addition result.
  - Carry Out (Cout) = Final carry sent to the next stage.

---

* **Truth Table**

| A | B | Cin | Sum1 (A⊕B) | Carry1 (A·B) | Sum (Sum1⊕Cin) | Carry2 (Sum1·Cin) | Cout (Carry1+Carry2) |
|:-:|:-:|:---:|:----------:|:------------:|:--------------:|:-----------------:|:--------------------:|
| 0 | 0 |  0  |     0      |      0       |       0        |         0         |          0           |
| 0 | 0 |  1  |     0      |      0       |       1        |         0         |          0           |
| 0 | 1 |  0  |     1      |      0       |       1        |         0         |          0           |
| 0 | 1 |  1  |     1      |      0       |       0        |         1         |          1           |
| 1 | 0 |  0  |     1      |      0       |       1        |         0         |          0           |
| 1 | 0 |  1  |     1      |      0       |       0        |         1         |          1           |
| 1 | 1 |  0  |     0      |      1       |       0        |         0         |          1           |
| 1 | 1 |  1  |     0      |      1       |       1        |         0         |          1           |
    
---

* **Boolean Expressions**
  - Sum (S) = A ⊕ B ⊕ Cin
  - Carry Out (Cout) = (A · B) + (Cin · (A ⊕ B))

 ---
 
* **Waveform / Timing Diagram:**

  ![FULL_ADDER_USING_TWO_HALF_ADDER Timing Waveform](Image/full_adder_using_two_half_adder_waveform.png)

