# **Full Adder**

  - A full adder is a digital combinational circuit that adds three 1-bit binary numbers (two inputs A , B and carry-in Cin) to produce a sum (S) and a carry-out (Cout)

 - Inputs:- Three (A , B , Cin).

 - Outputs:- Two (Sum and carry out).
  
---

* **Why is it used?**

*A Full Adder is used because*

 - It performs binary addition with a carry input.
 - It is the basic building block for multi-bit adders.
 - It enables arithmetic operations in digital systems.
 - It ensures correct addition by forwarding the carry to the next stage.
 - It is simple, fast, and efficient for digital circuit design.
 
---

* **Where is it used?**

*A Full Adder is widely used in*

  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Digital calculators.
  - Microcontrollers.
  - Memory address calculation circuits.
  - Digital Signal Processing (DSP) systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.

---

  * **Circuit Diagram:**

![HALF_ADDER](Image/half-adder.png)

---

* **Function of Inputs and Outputs**

  - A = First binary input bit.
  - B = Second binary input bit.
  - Cin = Carry input Full Adder stage.
  - Sum (S) = Result of adding A, B, and Cin.
  - Carry Out (Cout).

---

* **Truth Table** 

|     input     |     Output     |
|:-------------:|:--------------:|
|  A   B   Cin  | Sum  Carry out |
|  0   0    0   |  0       0     |
|  0   0    1   |  1       0     |
|  0   1    0   |  1       0     | 
|  0   1    1   |  0       1     |
|  1   0    0   |  1       0     |
|  1   0    1   |  0       1     |
|  1   1    0   |  0       1     |
|  1   1    1   |  1       1     | 


* **Boolean Equation**

   - Sum = (A'B'C) + (A'Bc') + (AB'c') + (ABC)

   - Sum = c'(A'B + AB') + C(A'B' + AB)

   - Carry out = (A'BC) + (AB'C) + (ABC') + (ABC)

   - Carry out = C(A'B + AB') + AB(C" + C)

   - Carry out = AB + BC + AC

---

* **Waveform / Timing Diagram:**

  ![HALF_ADDER Timing Waveform](Image/half_adder.png)
