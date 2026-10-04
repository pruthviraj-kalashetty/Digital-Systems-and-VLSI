

# ⚡ DIGITAL DESIGN & VLSI FUNDAMENTALS

### Digital Electronics • Semiconductor Fundamentals • CMOS • Timing Analysis • Digital VLSI • RTL Design Foundation

<p>
  <img src="https://img.shields.io/badge/%E2%9A%A1%20DOMAIN-VLSI%20ENGINEERING-0F172A?style=for-the-badge&labelColor=020617&color=2563EB"/>
  <img src="https://img.shields.io/badge/%E2%9C%A6%20FOCUS-DIGITAL%20DESIGN-0F172A?style=for-the-badge&labelColor=020617&color=06B6D4"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20LOGIC-COMBINATIONAL%20%26%20SEQUENTIAL-0F172A?style=for-the-badge&labelColor=020617&color=10B981"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20FSM-FINITE%20STATE%20MACHINES-0F172A?style=for-the-badge&labelColor=020617&color=8B5CF6"/>
</p>

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TIMING-TIMING%20ANALYSIS-0F172A?style=for-the-badge&labelColor=020617&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20CMOS-SEMICONDUCTOR-0F172A?style=for-the-badge&labelColor=020617&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STA-STATIC%20TIMING%20ANALYSIS-0F172A?style=for-the-badge&labelColor=020617&color=F59E0B"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20PURPOSE-RTL%20DESIGN%20FOUNDATION-0F172A?style=for-the-badge&labelColor=020617&color=F97316"/>
</p>

--- 

## 🛠️ Tools Used
  <p>
  <img src="https://skillicons.dev/icons?i=github,git,vscode,linux"/>
  </p>

</div>



## 📌 About This Repository

This repository serves as a core theoretical foundation for **RTL Design** and **ASIC/FPGA Front-End Engineering**. It systematically documents essential hardware concepts required prior to writing synthesizable Verilog code.

### 🎯 Key Knowledge Domains
* **Digital Logic Architecture:** Combinational logic, state machines, and register transfer principles.
* **Semiconductor Physics & CMOS:** Device operation, layout characteristics, and power dynamics.
* **ASIC/VLSI Flow:** RTL-to-GDSII methodology, PPA trade-offs, and physical limitations.
* **Static Timing Analysis (STA):** Setup/hold timing closures, clock domains, and skew analysis.

---

## 📚 Syllabus & Roadmap

<details open>
<summary><b>1️⃣ Digital Electronics</b></summary>

* **Digital Fundamentals:** Number Systems, Conversions, Binary Arithmetic, Binary Codes (BCD, Gray, Excess-3).
* **Combinational Logic:** Boolean Algebra, De Morgan's Theorems, Karnaugh Maps (K-Maps), Don't-Care Conditions.
* **Combinational Circuits:** Adders/Subtractors, Multiplexers/Demultiplexers, Encoders/Decoders, Digital Comparators.
* **Sequential Logic:** SR, D, JK, T Flip-Flops, Shift Registers (SISO, SIPO, PISO, PIPO).
* **Counters & FSMs:** Synchronous & Asynchronous Counters, Ring/Johnson Counters, Mealy vs. Moore State Machines, Sequence Detectors.
</details>

<details open>
<summary><b>2️⃣ Semiconductor Fundamentals</b></summary>

* **Physics & Materials:** Intrinsic & Extrinsic Semiconductors, Doping Dynamics, PN Junction Characteristics.
* **Manufacturing & Fabrication:** Wafer Fabrication, Cleanroom Standards, Photolithography, EUV Lithography.
* **Industry Ecosystem:** Chip Packaging Technologies, Wafer Testing, Semiconductor Supply Chain.
</details>

<details open>
<summary><b>3️⃣ MOS & CMOS Technology</b></summary>

* **MOSFET Devices:** NMOS, PMOS Structures, Channel Formation, Threshold Voltage ($V_{th}$).
* **CMOS Logic:** CMOS Inverter, Complementary Pull-Up (PUN) / Pull-Down (PDN) Networks, NAND/NOR Gates.
* **Design Metrics:** Noise Margins, Dynamic & Static Power Dissipation, Leakage Currents, Fan-in / Fan-out Limits.
</details>

<details open>
<summary><b>4️⃣ VLSI Engineering Principles</b></summary>

* **Design Methodologies:** ASIC vs. FPGA Architectures, Front-End vs. Back-End Workflows.
* **RTL-to-GDSII Flow:** Synthesis, Floorplanning, Placement, Clock Tree Synthesis (CTS), Routing, Physical Verification.
* **Optimization Parameters:** PPA (Power, Performance, Area) Trade-offs, Parasitic RC Delays, Logical Effort.
</details>

<details open>
<summary><b>5️⃣ Timing & Static Timing Analysis (STA)</b></summary>

* **Clock & Delay Metrics:** Clock Skew, Jitter, Propagation Delay, Contamination Delay, Rise/Fall Times.
* **Timing Constraints:** Setup Time ($t_{setup}$), Hold Time ($t_{hold}$), Data Arrival Time, Data Required Time.
* **STA & Verification:** Critical Path Analysis, Setup/Hold Violations, Slack Computation, False Paths, Multicycle Paths.
</details>

---

# 🏗️ Directory Structure

```text
**Repository - 01**
├──Digital-Systems-and-VLSI
│   ├── [01]-Digital-Basics
│   │   ├── 01-Digital-vs-Analog.md
│   │   └── 02-Digital-System-Overview.md
│   │   
│   ├── [02]-Number-Systems
│   │   ├── 01-Binary-System.md
│   │   ├── 02-Decimal-System.md
│   │   ├── 03-Octal-System.md
│   │   ├── 04-Hexadecimal-System.md
│   │   └── 05-Number-System-Conversion.md
│   │
│   ├── [03]-Binary-Arithmetic
│   │   ├── 01-Binary-Addition.md
│   │   ├── 02-Binary-Subtraction.md
│   │   ├── 03-Binary-Multiplication.md
│   │   └── 04-Binary-Division.md
│   │
│   ├── [04]-Binary-Codes
│   │   ├── 01-BCD-Code.md
│   │   ├── 02-Gray-Code.md
│   │   ├── 03-ASCII-Code.md
│   │   ├── 04-Excess-3-Code.md
│   │   ├── 05-Binary-to-Gray.md
│   │   ├── 06-Gray-to-Binary.md
│   │   ├── 07-BCD-to-Excess-3.md
│   │   └── 08-Excess-3-to-BCD.md
│   │
│   ├── [05]-Boolean-Algebra
│   │   ├── 01-Boolean-Basics.md
│   │   ├── 02-Boolean-Laws.md
│   │   ├── 03-DeMorgan-Theorem.md
│   │   └── 04-Boolean-Expression.md
│   │
│   ├── [06]-Logic-Gates
│   │   ├── 01-AND-Gate.md
│   │   ├── 02-OR-Gate.md
│   │   ├── 03-NOT-Gate.md
│   │   ├── 04-NAND-Gate.md
│   │   ├── 05-NOR-Gate.md
│   │   ├── 06-XOR-Gate.md
│   │   └── 07-XNOR-Gate.md
│   │
│   ├── [07]-Combinational-Logic
│   │   ├── 01-Introduction.md
│   │   ├── 02-Truth-Tables.md
│   │   ├── 03-Minterms-Maxterms.md
│   │   └── 04-Combinational-vs-Sequential.md
│   │
│   ├── [08]-Karnaugh-Map
│   │   ├── 01-KMap-3-Variable.md
│   │   ├── 02-KMap-4-Variable.md
│   │   └── 03-Dont-Care-Conditions.md
│   │
│   ├── [09]-Combinational-Circuits
│   │   ├── [01]-Adders
│   │   │   ├── 01-Half-Adder.md
│   │   │   ├── 02-Full-Adder.md
│   │   │   └── 03-Full-Adder-Using-Two-Half-Adder.md
│   │   ├── [02]-Subctractor
│   │   │   ├── 01-Half-Subctractor.md
│   │   │   ├── 02-Full-Subctractor.md
│   │   │   └── 03-Full-Subctractor-Using-Two-Half-Subctractor.md
│   │   ├── [03]-Multiplexer
│   │   │   ├── 01-2x1.md
│   │   │   ├── 02-4x1.md
│   │   │   └── 03-8x1.md
│   │   ├── [04]-Demultiplexer
│   │   │   ├── 01-1x2.md
│   │   │   ├── 02-1x4.md
│   │   │   └── 03-1x8.md
│   │   ├── [05]-Decoder
│   │   │   ├── 01-2x4.md
│   │   │   └── 02-3x8.md
│   │   ├── [06]-Encoder
│   │   │   ├── 01-4x2.md
│   │   │   ├── 02-8x3.md
│   │   │   └── 03-Priority-Encoder.md
│   │   └── [07]-Comparator
│   │   │   ├── 1-bit.md
│   │   │   ├── 2-bit.md
│   │   │   └── 3-bit.md
│   │   └── [08]Ripple-Carry-Adder.md
│   │
│   ├── [10]-Flip-Flops
│   │   ├── SR-FlipFlop.md
│   │   ├── D-FlipFlop.md
│   │   ├── JK-FlipFlop.md
│   │   ├── T-FlipFlop.md
│   │   ├── Characteristic-Table.md
│   │   └── Excitation-Table.md
│   │
│   ├── [11]-Registers
│   │   ├── 01-Register-Basics.md
│   │   ├── 02-Shift-Registers.md
│   │   ├── 03-SISO-Register.md
│   │   ├── 04-SIPO-Register.md
│   │   ├── 05-PISO-Register.md
│   │   └── 06-PIPO-Register.md
│   │
│   ├── [12]-Counters
│   │   ├── Asynchronous-Counters
│   │   │   ├── 3-Bit-Asynchoronous-Down-Counter.md
│   │   │   ├── 3-Bit-Asynchoronous-Up,Down-Counter.md
│   │   │   ├── 3-Bit-Asynchoronous-Up-Counter.md
│   │   │   ├── 4-Bit-Asynchoronous-Down-Counter.md
│   │   │   ├── 4-Bit-Asynchoronous-Up,Down-Counter.md
│   │   │   └── 4-Bit-Asynchoronous-Up-Counter.md
│   │   ├── Synchronous-Counters
│   │   │   ├── 3-Bit-Synchoronous-Down-Counter.md
│   │   │   ├── 3-Bit-Synchoronous-Up,Down-Counter.md
│   │   │   ├── 3-Bit-Synchoronous-Up-Counter.md
│   │   │   ├── 4-Bit-Synchoronous-Down-Counter.md
│   │   │   ├── 4-Bit-Synchoronous-Up,Down-Counter.md
│   │   │   └── 4-Bit-Synchoronous-Up-Counter.md
│   │   └── Special-Counters
│   │       └── Ring-Counter.md
│   │
│   └── [13]-Finite-State-Machines
│       ├── 01-FSM-Introduction.md
│       ├── 02-State-Diagram.md
│       ├── 03-State-Table.md
│       ├── 04-Moore-Machine.md
│       ├── 05-Mealy-Machine.md
│       └── 06-Sequence-Detector.md
│
├── Semiconductor-and-CMOS
│   │
│   ├── [01]-Semiconductor-Basics
│   │   ├── 01-Semiconductor-Types.md 
│   │   ├── 02-Intrinsic-Semiconductor.md 
│   │   ├── 03-Extrinsic-Semiconductor.md 
│   │   ├── 04-Doping.md 
│   │   ├── 05-N-Type-Semiconductor.md 
│   │   ├── 06-P-Type-Semiconductor.md 
│   │   ├── 07-Semiconductor Manufacturing Process
│   │   ├── 08-From Sand to Silicon
│   │   ├── 09-Silicon Wafer Manufacturing
│   │   ├── 10-Semiconductor Fabrication Plant
│   │   ├── 11-Clean Room Technology
│   │   ├── 12-Photolithography
│   │   ├── 13-EUV Lithography
│   │   ├── 14-Wafer Testing
│   │   ├── 15-Chip Packaging
│   │   └── 16-Semiconductor Ecosystem
│   │   
│   ├── [02]-MOS-Devices
│   │   ├── 01-What is MOSFET.md
│   │   ├── 02-NMOS.md
│   │   ├── 03-PMOS.md
│   │   ├── 04-MOS-Operation.md
│   │   └── 05-Threshold-Voltage.md
│   │
│   └── [03]-CMOS Introduction
│          ├── [01]-CMOS-Basics
│          │   ├── 01-What is CMOS?
│          │   ├── 02-Complementary NMOS + PMOS
│          │   ├── 03-CMOS Inverter
│          │   ├── 04-CMOS Logic Operation
│          │   └── 05-Pull-up and Pull-down Networks
│          │   
│          ├── [02]-CMOS Logic Gates
│          │   ├── 01-CMOS NOT (Inverter)
│          │   ├── 02-CMOS AND
│          │   ├── 03-CMOS NAND
│          │   ├── 04-CMOS OR
│          │   ├── 05-CMOS NOR
│          │   └── 06-CMOS XOR / XNOR (basic understanding)
│          │   
│          ├── [03]-CMOS Characteristics
│          │   ├── 01-Noise Margin
│          │   ├── 02-Propagation Delay
│          │   ├── 03-Rise Time
│          │   └── 04-Fall Time
│          │     
│          └── [04]-CMOS Design Concepts
│              ├── 01-Fan-in
│              ├── 02-Fan-out
│              └── 03-Load Capacitance
│
├── VLSI-Fundamentals
│   ├── [01]-Introduction-to-VLSI
│   │   ├── 01-What-is-VLSI
│   │   ├── 02-VLSI-Levels-of-Integration
│   │   ├── 03-VLSI-Design-Types
│   │   ├── 04-Digital-vs-Analog-IC
│   │   └── 05-VLSI-Applications
│   │  
│   ├── [02]-ASIC-vs-FPGA
│   │    ├── 01-ASIC
│   │    ├── 02-FPGA
│   │    ├── 03-ASIC-vs-FPGA
│   │    ├── 04-Advantages-and-Disadvantages
│   │    └── 05-RTL-in-ASIC-and-FPGA
│   │
│   ├── [03]-Front-End-vs-Back-End
│   │    ├── 01-Front-End-Design
│   │    ├── 02-RTL-Design
│   │    ├── 03-Functional-Verification
│   │    ├── 04-Logic-Synthesis
│   │    ├── 05-Back-End-Design
│   │    └── 06-Physical-Design
│   │  
│   ├── [04]-RTL-to-GDSII-Flow
│   │   ├── 01-Specification
│   │   ├── 02-RTL-Coding
│   │   ├── 03-Functional-Verification
│   │   ├── 04-Logic-Synthesis
│   │   ├── 05-Floor-planning
│   │   ├── 06-Placement
│   │   ├── 07-Clock-Tree-Synthesis
│   │   ├── 08-Routing
│   │   ├── 09-STA
│   │   ├── 10-Physical-Verification
│   │   └── 11-GDSII
│   │   
│   ├── [05]-PPA
│   │   ├── 01-Power
│   │   ├── 02-Performance
│   │   ├── 03-Area
│   │   ├── PPA-Tradeoffs
│   │   └── RTL-Level-PPA-Optimization
│   │  
│   ├── [06]-Parasitic-RC-Basics
│   │   ├── Resistance
│   │   ├── Capacitance
│   │   ├── Interconnect
│   │   ├── RC-Delay
│   │   └── Impact-on-Timing
│   │
│   └── [07]-Logical-Effort-Basics
│         ├── Gate-Delay
│         ├── Logical-Effort
│         ├── Electrical-Effort
│         ├── Parasitic-Delay
│         └── Path-Optimization
│
└── Timing-and-STA
    ├── 01-Timing-Fundamentals
    │   ├── 01-Introduction-to-Digital-Timing.md
    │   ├── 02-Clock-Concepts.md
    │   ├── 03-Clock-Frequency-and-Period.md
    │   ├── 04-Duty-Cycle.md
    │   ├── 05-Propagation-Delay.md
    │   ├── 06-Contamination-Delay.md
    │   ├── 07-Clock-to-Q-Delay.md
    │   ├── 08-Rise-Time.md
    │   └── 09-Fall-Time.md
    │
    ├── 02-Setup-Hold-and-Clock-Effects
    │   ├── 01-Setup-Time.md
    │   ├── 02-Hold-Time.md
    │   ├── 03-Setup-and-Hold-Requirements.md
    │   ├── 04-Clock-Skew.md
    │   ├── 05-Clock-Jitter.md
    │   └── 06-Clock-Uncertainty.md
    │
    ├── 03-Timing-Paths
    │   ├── 01-Timing-Path-Introduction.md
    │   ├── 02-Launch-and-Capture-Elements.md
    │   ├── 03-Data-Path.md
    │   ├── 04-Clock-Path.md
    │   ├── 05-Register-to-Register-Path.md
    │   ├── 06-Input-to-Register-Path.md
    │   ├── 07-Register-to-Output-Path.md
    │   └── 08-Input-to-Output-Path.md
    │
    └── 04-Static-Timing-Analysis
        ├── 01-Introduction-to-STA.md
        ├── 02-STA-vs-Simulation.md
        ├── 03-Timing-Graph-and-Paths.md
        ├── 04-Setup-Analysis.md
        ├── 05-Hold-Analysis.md
        ├── 06-Arrival-Time.md
        ├── 07-Required-Time.md
        ├── 08-Slack-Analysis.md
        └── 09-Timing-Violations.md
       

```
---


---

# 🎯 Skills Developed✔ 

- Digital Circuit Analysis
- Boolean Logic Simplification
- Combinational Circuit Design
- Sequential Circuit Fundamentals
- CMOS Logic Understanding
- Semiconductor Fundamentals
- VLSI Design Flow Understanding
- Timing Analysis Fundamentals
- Static Timing Analysis (STA) Basics
- RTL Design Foundation
- Hardware Design Thinking
- ASIC Interview Preparation

---

# 🔗 Next Learning Stage

This repository builds the foundation for:

➡ Verilog RTL Design  
➡ SystemVerilog Verification  
➡ FPGA Implementation  
➡ ASIC Design Flow

