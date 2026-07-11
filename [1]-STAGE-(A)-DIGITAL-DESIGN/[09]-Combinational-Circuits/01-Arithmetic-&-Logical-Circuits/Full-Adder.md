## Full Adder 
A full adder is a digital combinational circuit that adds three 1-bit binary numbers (two inputs A , B and carry-in Cin)
to produce a sum (S) and a carry-out (Cout). 

- Inputs:- Three (A , B , Cin)

- Outputs:- Two (Sum and carry out)

### Truth Table 

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

### Logic Equation 
 - Sum = (A'B'C) + (A'Bc') + (AB'c') + (ABC)

 - Sum = c'(A'B + AB') + C(A'B' + AB)

 - Carry out = (A'BC) + (AB'C) + (ABC') + (ABC)

 - Carry out = C(A'B + AB') + AB(C" + C)

 - Carry out = AB + BC + AC



