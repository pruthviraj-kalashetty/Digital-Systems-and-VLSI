# Hardware Specification: *AND Gate*

### **1. Purpose & Definition**
* **What Problem Does It Solve?**
  In digital processing, we frequently need to test if *multiple conditions are true simultaneously* before triggering an event. Alternatively, we need a way to selectively disable or "mask" a data stream (forcing it to `0`). The AND gate solves this by acting as a hardware condition tester and data mask.
* **What is the Circuit?**
  An AND gate is a fundamental digital combinational circuit that outputs a logic high (`1`) if and only if all of its inputs are simultaneously at a logic high state. If any input is logic low (`0`), the output is forced low.

---

### **2. Applications**
* **Where Is It Used?**
  * **Clock Gating Units (CGUs):** Used to turn off the clock signal to idle modules inside a SoC to save dynamic power.
  * **ALU Masking:** Used to mask out specific bits in a data word (e.g., bitwise AND operations in a processor).
  * **Address Decoding:** Used in memory controllers to select a specific RAM bank only when all address lines match.
* **Why Is It Used?**
  It is the most structurally efficient way to implement logical intersection. In physical silicon, it provides a direct, highly noise-immune method to execute conditional control logic using a minimal footprint of CMOS transistors.

---

### **3. Interface & Pins**
* **Block Diagram:**
  The block diagram defines the black-box boundary of the device:

![AND Gate](./image/and-gates.png)

* **Inputs and Outputs:**
  | Signal Name | Direction | Bit-Width | Domain |
  | :--- | :--- | :--- | :--- |
  | `A` | Input | 1-bit | Data / Control |
  | `B` | Input | 1-bit | Data / Control |
  | `Y` | Output | 1-bit | Data Output |

* **Function of Inputs and Outputs:**
  * **`A` (Input):** Primary logic operand.
  * **`B` (Input):** Secondary logic operand. When used as a mask, holding `B=0` forces `Y=0` regardless of `A`. Holding `B=1` allows `A` to pass through to `Y` unchanged.
  * **`Y` (Output):** The logical product ($A \cdot B$). Driven to $V_{DD}$ for high or $0V$ for low.

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
  $$Y = A \cdot B$$

---

### **5. Schematic & Limitations**
* **Logic Gate Diagram & Transistor Schematic:**
  While drawn as a single symbol on logic sheets, a real CMOS AND gate is physically built by cascading a **NAND gate** into a **NOT gate (Inverter)**. This requires 6 transistors total (4 for NAND, 2 for Inverter).

  ![AND Gate CMOS Schematic](./images/and_schematic.png)

* **Waveform / Timing Diagram:**
  The ideal functional timing diagram demonstrates how changes on the input pins propagate through to the output:

  ![AND Gate Timing Waveform](./images/and_waveform.png)

* **The Hardware Limitations:**
  * **Propagation Delay ($t_{pd}$):** Because an AND gate is physically a NAND followed by an Inverter, the signal must pass through two successive transistor stages. This creates an internal propagation delay ($t_{NAND} + t_{INV}$).
  * **Glitch Propagation:** If inputs `A` and `B` switch states at slightly different times due to wire lengths (e.g., `A` goes $1 \rightarrow 0$ while `B` goes $0 \rightarrow 1$), the output `Y` can momentarily glitch to an incorrect state before settling.
