# **Half Subtractor**

* **What Problem Does It Solve**
  
  - A Half Subtractor is a digital combinational circuit.
  - It subtracts two 1-bit binary numbers (A and B).
  - It produces a Difference (D) and a Borrow (Bout).

---

* **Why is it used**
  
  *A Half Subtractor is used because:*
  
  - It performs the subtraction of two binary bits.
  - It generates both Difference and Borrow outputs.
  - It is the basic building block for binary subtraction circuits.
  - It is simple, fast, and requires fewer logic gates.
  - It is used as a part of Full Subtractor and other arithmetic circuits.

---

* **Where is it used**
  
  *A Half Subtractor is widely used in:*
  
  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Digital calculators.
  - Arithmetic circuits.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Binary subtraction circuits.
  - Digital logic systems.

---

* **Circuit Diagram:**

![HALF_SUBCTRACTOR](Image/half-subctractor.png)

---

* **Function of Inputs and Outputs**
  
  - A = Minuend (number from which B is subtracted).
  - B = Subtrahend (number to be subtracted).
  - Difference (D) = Result of A − B.
  - Borrow (Bout) = Borrow generated when A is less than B.

---

* **Truth Table**

| A | B | Difference (D)| Borrow (Bout)|
|---|---|---------------|--------------|
|0| 0| 0| 0|
|0| 1| 1| 1|
|1| 0| 1| 0|
|1| 1| 0| 0|

---

* **Boolean Expressions**

    - Difference (D) = A ⊕ B
    - Borrow (Bout) = A̅ · B

---

* **Waveform / Timing Diagram:**

  ![HALF_SUBCTRACTOR Timing Waveform](Image/half_subctractor_waveform.png)

