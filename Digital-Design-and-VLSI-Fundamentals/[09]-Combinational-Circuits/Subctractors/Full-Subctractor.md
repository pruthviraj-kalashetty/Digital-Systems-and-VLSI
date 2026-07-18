# **Full Subtractor**

* **What Problem Does It Solve**
    - A Full Subtractor is a digital combinational circuit.
    - It subtracts three 1-bit binary numbers (A, B, and Borrow-in (Bin)).
    - It produces a Difference (D) and a Borrow-out (Bout).

---

* **Why is it used**
  
  *A Full Subtractor is used because:*
  
  - It performs binary subtraction with a borrow input.
  - It is the basic building block for multi-bit subtractors.
  - It enables arithmetic subtraction in digital systems.
  - It forwards the borrow to the next stage for correct subtraction.
  - It is simple, fast, and efficient for digital circuit design.

---

* **Where is it used**
  
  *A Full Subtractor is widely used in:*
  
  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Digital calculators.
  - Microcontrollers.
  - Arithmetic and logic circuits.
  - Digital Signal Processing (DSP) systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.

---

* **Circuit Diagram:**

![FULL_SUBCTRACTOR](SubctractorsImage/full-subctractor.png)

---

* **Function of Inputs and Outputs**
  
  - A = Minuend (number from which B is subtracted).
  - B = Subtrahend (number to be subtracted).
  - Bin = Borrow input from the previous stage.
  - Difference (D) = Result of A − B − Bin.
  - Borrow Out (Bout) = Borrow generated and sent to the next stage.

---

* **Truth Table**

|A | B | Bin| Difference (D)| Borrow (Bout)|
|--|---|----|---------------|--------------|
|0| 0| 0| 0| 0|
|0| 0| 1| 1| 1|
|0| 1| 0| 1| 1|
|0| 1| 1| 0| 1|
|1| 0| 0| 1| 0|
|1| 0| 1| 0| 0|
|1| 1| 0| 0| 0|
|1| 1| 1| 1| 1|

---

* **Boolean Expressions**

   - Difference (D) = A ⊕ B ⊕ Bin
   - Borrow Out (Bout) = A̅·B + A̅·Bin + B·Bin

---

* **Waveform / Timing Diagram:**

  ![FULL_SUBCTRACTOR Timing Waveform](Image/full_subctractor_waveform.png)

