## Encoder 
A encoder is a sensor or circuit that converts motion or data into electrical or digital signals. It provides feedback on speed,position,and direction,primarily using optical or magnetic technology to count pulses ,commonly used in motor controll,robotics and automation to ensure precsion motion.

#### Types Of Motion
- Rotary Encoders
- Linear Encoder

### Trut Table
| D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 |      | X | Y | Z | 
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:----:|:-:|:-:|:-:
| 1  |  0 |  0 | 0  | 0  |  0 |  0 |  0 |      | 0 | 0 | 0 |              
| 0  |  1 |  0 | 0  |  0 |  0 |  0 |  0 |      | 0 | 0 | 1 | 
| 0  |  0 |  1 | 0  | 0  |  0 |  0 |  0 |      | 0 | 1 | 0 |            
| 0  |  0 |  0 | 1  | 0  |  0 |  0 |  0 |      | 0 | 1 | 1 |           
| 0  |  0 |  0 | 0  | 1  |  0 |  0 |  0 |      | 1 | 0 | 0 | 
| 0  |  0 |  0 | 0  | 0  |  1 |  0 |  0 |      | 1 | 0 | 1 |
| 0  |  0 |  0 | 0  | 0  |  0 |  1 |  0 |      | 1 | 1 | 0 |
| 0  |  0 |  0 | 0  | 0  |  0 |  0 |  1 |      | 1 | 1 | 1 |

### Logic Equation

- X = D4 + D5 + D6 + D7
  
- Y = D2 + D3 + D6 + D7
  
- Z = D1 + D3 + D5 + D7




