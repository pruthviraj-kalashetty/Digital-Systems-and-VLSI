# **Half Adder**

* **What Problem Does It Solve?**
  - A Half Adder is a digital combinational circuit.
  - It adds two 1-bit binary numbers (A and B).
  - It produces a Sum (S) and a Carry (C).

---

* **Why is it used?**

  *A Half Adder is used because:*

  - It performs the addition of two binary bits.
  - It generates both Sum and Carry outputs.
  - It is the basic building block for binary addition circuits.
  - It is simple, fast, and requires fewer logic gates.
  - It is used as a part of Full Adder and other arithmetic circuits.

---

 * **Where is it used?**
 
   *A Half Adder is widely used in*

   - CPUs (Processors).
   - ALU (Arithmetic Logic Unit).
   - Digital calculators.
   - Arithmetic circuits.
   - Digital VLSI and RTL design.
   - FPGA and ASIC designs.
   - Binary addition circuits.
   - Digital logic systems.

---

   * **Circuit Diagram:**

![HALF_ADDER](Images/half-adder.png)

---

* **Function of Inputs and Outputs**

  - A = First binary input bit.
  - B = Second binary input bit.
  - Sum (S) = Result of adding A and B.
  - Carry (C) = Carry generated when both inputs are 1.

---

* **Truth Table**

|   Input   |   output   |
|:---------:|:----------:|
|  A    B   |  S     C   |
|  0    0   |  0     0   |   
|  0    1   |  1     0   |
|  1    0   |  1     0   |
|  1    1   |  0     1   |

---

* **Boolean Equation** 

  - Sum = a' * b + a * b'

  - Carry = a * b

---

* **Waveform / Timing Diagram:**

  ![HALF_ADDER Timing Waveform](Image/half_adder_waveform.png)
