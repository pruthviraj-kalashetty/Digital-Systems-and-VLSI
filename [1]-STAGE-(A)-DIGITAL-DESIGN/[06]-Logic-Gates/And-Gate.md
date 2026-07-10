# Hardware Specification: *AND Gate*

### **1. Purpose & Definition**
* **What Problem Does It Solve?**
  
* **What is the Circuit?**
  
---

### **2. Applications**
* **Where Is It Used?**
 
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
  | Input A | Input B | Output Y |
  | :---: | :---: | :---: |
  | 0 | 0 | **0** |
  | 0 | 1 | **0** |
  | 1 | 0 | **0** |
  | 1 | 1 | **1** |

* **Boolean Equation:**
  The mathematical function of the circuit is represented as:


---
### **5. Waveform / Timing Diagram:**
  The ideal functional timing diagram demonstrates how changes on the input pins propagate through to the output:

  ![AND Gate Timing Waveform](./images/and_waveform.png)

