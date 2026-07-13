# **Full Subtractor Using Half Subtractors**

* **What Problem Does It Solve**
  
  - A Full Subtractor using Half Subtractors is a digital combinational circuit.
  - It subtracts three 1-bit binary numbers (A, B, and Borrow-in (Bin)).
  - It produces a Difference (D) and a Borrow-out (Bout).
  - It is implemented using two Half Subtractors and one OR gate.
    
* **Why is it used**
  
A Full Subtractor using Half Subtractors is used because:
It performs binary subtraction with a borrow input.
It is easy to design using basic digital building blocks.
It simplifies the implementation of binary subtraction.
It is used to build multi-bit subtractors.
It provides accurate Difference and Borrow outputs.
Where is it used?
A Full Subtractor using Half Subtractors is widely used in:
CPUs (Processors).
ALU (Arithmetic Logic Unit).
Digital calculators.
Microcontrollers.
Arithmetic circuits.
Digital VLSI and RTL design.
FPGA and ASIC designs.
Binary subtraction circuits.
Circuit Diagram:
�
Working
The first Half Subtractor subtracts B from A and produces Difference1 (D1) and Borrow1 (B1).
The second Half Subtractor subtracts Borrow-in (Bin) from Difference1 (D1) and produces the final Difference (D) and Borrow2 (B2).
An OR gate combines Borrow1 (B1) and Borrow2 (B2) to generate the final Borrow-out (Bout).
Function of Inputs and Outputs
A = Minuend (number from which B is subtracted).
B = Subtrahend (number to be subtracted).
Bin = Borrow input from the previous stage.
Difference (D) = Final subtraction result.
Borrow Out (Bout) = Final borrow sent to the next stage.
Boolean Expressions
Difference (D) = A ⊕ B ⊕ Bin
Borrow Out (Bout) = A̅·B + A̅·Bin + B·Bin
Easy Way to Remember
Half Subtractor 1: Subtracts A − B.
Half Subtractor 2: Subtracts Difference1 − Bin.
OR Gate: Combines Borrow1 and Borrow2 to produce Borrow Out (Bout).
