# Hardware Specification: *AND Gate*

* **What Problem Does It Solve?**
  - The and gate checks if all condition are true
  - If one inputs is 'ON' then output will be 'ON'
  - If both inputs is 'ON' output will be 'OFF'  
  
* **What is the Circuit?**
  - It is an electronc circuit that performs AND operation
---

* **Where Is It Used?**
  *The and gate will be used in:*
  
  - Security System
  - Door Bell
  - Alaram System
  - Computer And Digital Circuit
  - Traffic Signal Control System
  - 
---

### **3. Interface & Pins**
* **Block Diagram:**
  The *AND GATE* block diagram:

![AND Gate](Image/and-gates.png)

* **Inputs and Outputs:**
  | Signal Name | Direction | Bit-Width | Domain |
  | :--- | :--- | :--- | :--- |
  | `A` | Input | 1-bit | Data / Control |
  | `B` | Input | 1-bit | Data / Control |
  | `Y` | Output | 1-bit | Data Output |

* **Function of Inputs and Outputs:**
  

---

### **4. Mathematical Logic**
* **Truth Table:**
| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

The symbol of 'AND' gate [*]

* **Boolean Equation:**
  The mathematical function of the circuit is represented as:


---
### **5. Waveform / Timing Diagram:**
  The ideal functional timing diagram demonstrates how changes on the input pins propagate through to the output:

  ![AND Gate Timing Waveform](./images/and_waveform.png)

