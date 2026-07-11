## Full Subctractor 
A full subctractor is a conbinational circuit that subctracts three single bit binary number (A B and cin) producing difference (D) a borrow (Bout) output.

- Inputs: Three (A , B , cin)

- Outputs: Two (D - difference , B - borrow)

### Truth Table 

|   Input   |  Output  |
|:---------:|:--------:|
|  A  B  C  |   D   B  |
|  0  0  0  |   0   0  | 
|  0  0  1  |   1   1  |
|  0  1  0  |   1   1  |
|  0  1  1  |   0   1  |
|  1  0  0  |   1   0  |
|  1  0  1  |   0   0  |
|  1  1  0  |   0   0  |
|  1  1  1  |   1   1  | 

### Logic Equation 

- Difference = A'B'C + A'BC' + AB'C' + ABC

- Borrow = A'C + BC + A'B



