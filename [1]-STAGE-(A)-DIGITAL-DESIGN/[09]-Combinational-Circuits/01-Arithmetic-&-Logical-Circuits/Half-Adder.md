## Half Adder 
A half adder is a fundamental combinational logic circuit that add two single bit binary digit (A and B) and produces two outputs: Sum(S) and Carry(C). it uses an XOR gate for the sum and an AND gate for the carry

- Inputs: Two inputs (A,B)

- Outputs: Two outputs Sum(S) , Carry(C)

### Truth Table

|   Input   |   output   |
|:---------:|:----------:|
|  A    B   |  S     C   |
|  0    0   |  0     0   |   
|  0    1   |  1     0   |
|  1    0   |  1     0   |
|  1    1   |  0     1   |

### Logic Equation 

- Sum = a' * b + a * b'

- Carry = a * b

