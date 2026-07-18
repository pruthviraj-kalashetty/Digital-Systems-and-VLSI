## Decoder
A decoder is a combinational logic circuit that converts n inputs lines a maximum of 2n unique output lines acting as a translator that activates one specfic output based on the binary input code.

#### Types Of Decoder
- 2 - to 4
- 3 - to - 8 
- 4 - to - 16

### Truth Table

| X | Y | Z |   | D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 |        
|:-:|:-:|:-:|:-:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 0 |   | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  |
| 0 | 0 | 1 |   | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  |
| 0 | 1 | 0 |   | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  |  
| 0 | 1 | 1 |   | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 
| 1 | 0 | 0 |   | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  |
| 1 | 0 | 1 |   | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 
| 1 | 1 | 0 |   | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  |
| 1 | 1 | 1 |   | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  |

### Logic Equation

- D0 = X'Y'Z'

- D1 = X'Y'Z

- D2 = X'YZ'

- D3 = X'YZ

- D4 = XY'Z'

- D5 = XY'Z

- D6 = XYZ'

- D7 = XYZ


