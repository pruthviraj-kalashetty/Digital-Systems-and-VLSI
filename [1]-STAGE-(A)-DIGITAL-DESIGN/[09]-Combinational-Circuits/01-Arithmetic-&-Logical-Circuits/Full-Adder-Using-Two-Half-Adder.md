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

* **Function of Inputs and Outputs**
  
  - A = First binary input bit.
  - B = Second binary input bit.
  - Cin = Carry input from the previous stage.
  - Sum (S) = Final addition result.
  - Carry Out (Cout) = Final carry sent to the next stage.
  - Boolean Expressions
  - Sum (S) = A ⊕ B ⊕ Cin
  - Carry Out (Cout) = (A · B) + (Cin · (A ⊕ B))
