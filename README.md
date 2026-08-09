<div align="center">

# ⚡ DIGITAL DESIGN & VLSI FUNDAMENTALS

### Digital Electronics • Semiconductor Fundamentals • CMOS • Timing Analysis • Digital VLSI • RTL Design Foundation



<p>
  <img src="https://img.shields.io/badge/%E2%9A%A1%20DOMAIN-VLSI%20ENGINEERING-0F172A?style=for-the-badge&labelColor=FFFFFFF2&color=2563EB"/>
  <img src="https://img.shields.io/badge/%E2%9C%A6%20FOCUS-DIGITAL%20DESIGN-0F172A?style=for-the-badge&labelColor=FFFFFF&color=06B6D4"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20LOGIC-COMBINATIONAL%20%26%20SEQUENTIAL-0F172A?style=for-the-badge&labelColor=FFFFFF&color=10B981"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20FSM-FINITE%20STATE%20MACHINES-0F172A?style=for-the-badge&labelColor=FFFFFF&color=8B5CF6"/>
</p>

<p>
  <img src="https://img.shields.io/badge/%E2%97%88%20TIMING-TIMING%20ANALYSIS-0F172A?style=for-the-badge&labelColor=FFFFFF&color=3B82F6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20CMOS-SEMICONDUCTOR-0F172A?style=for-the-badge&labelColor=FFFFFF&color=14B8A6"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20STA-STATIC%20TIMING%20ANALYSIS-0F172A?style=for-the-badge&labelColor=FFFFFF&color=F59E0B"/>
  <img src="https://img.shields.io/badge/%E2%97%88%20PURPOSE-RTL%20DESIGN%20FOUNDATION-0F172A?style=for-the-badge&labelColor=FFFFFF&color=F97316"/>
</p>

--- 

## 🛠️ Tools Used
  <p>
  <img src="https://skillicons.dev/icons?i=github,git,vscode,linux"/>
  </p>

</div>



## 📌 About This Repository

This repository contains structured notes, concepts, and design fundamentals required for **RTL Design and ASIC VLSI Engineering**.

It covers the journey from:

- Digital Electronics
- Semiconductor fundamentals
- MOSFET and CMOS Technology
- Timing Concepts
- Static Timing Analysis (STA)
- VLSI design fundamentals

The primary objective is to understand how digital hardware works internally before implementing hardware using Verilog RTL.

This repository is theory-focused and serves as the foundation for my Verilog RTL Design repository.

---

# 📚 Learning Goal

## 1️⃣ Digital Electronics
- Digital Basics
- Number Systems
- Binary Arithmetic
- Binary Codes
- Boolean Algebra
- Logic Gates
- Combinational Logic
- Karnaugh Maps
- Combinational Circuits
- Flip-Flops
- Registers
- Counters
- Finite State Machines (FSM)

---

## 2️⃣ Semiconductor Fundamentals *(Knowledge)*

- Semiconductor Basics
- Intrinsic & Extrinsic Semiconductor
- Doping
- PN Junction
- Semiconductor Manufacturing
- Wafer Fabrication
- Photolithography
- EUV Lithography
- Chip Packaging
- Semiconductor Ecosystem

---

## 3️⃣ MOS & CMOS *(Knowledge)*

### MOS Devices

- MOSFET
- NMOS
- PMOS
- MOS Operation
- Threshold Voltage

### CMOS Fundamentals

- CMOS Basics
- CMOS Inverter
- CMOS Logic Gates
- CMOS Characteristics
- CMOS Power
- CMOS Digital Design Concepts

---

## 4️⃣ VLSI Fundamentals *(Knowledge)*

- Introduction to VLSI
- ASIC vs FPGA
- Front-End vs Back-End
- RTL to GDSII Flow
- Power, Performance & Area (PPA)
- Parasitic RC
- Logical Effort

---

## 5️⃣ Timing Concepts *(Knowledge + Interview)*

- Clock Concepts
- Propagation Delay
- Contamination Delay
- Rise Time
- Fall Time
- Setup Time
- Hold Time
- Clock Skew
- Clock Jitter
- Arrival Time
- Required Time
- Timing Diagrams

---

## 6️⃣ Static Timing Analysis (STA) *(Knowledge + Interview)*

- Introduction to STA
- Timing Paths
- Setup Analysis
- Hold Analysis
- Timing Violations
- Slack Analysis
- Timing Constraints
- Critical Path
- Timing Reports
- Input & Output Delay
- False Path
- Multicycle Path
- Timing Closure


---

# 🏗️ Directory Structure

```text
**Repository - 01**

├──Digital-Systems-and-VLSI  
│   ├── [01]-Digital-Basics
│   │   ├── Digital-vs-Analog.md
│   │   └── Digital-System-Overview.md
│   │
│   ├── [02]-Number-Systems
│   │   ├── Binary-System.md
│   │   ├── Decimal-System.md
│   │   ├── Octal-System.md
│   │   ├── Hexadecimal-System.md
│   │   └── Number-System-Conversion.md
│   │
│   ├── [03]-Binary-Arithmetic
│   │   ├── Binary-Addition.md
│   │   ├── Binary-Subtraction.md
│   │   ├── Binary-Multiplication.md
│   │   └── Binary-Division.md
│   │
│   ├── [04]-Binary-Codes
│   │   ├── BCD-Code.md
│   │   ├── Gray-Code.md
│   │   ├── ASCII-Code.md
│   │   ├── Excess-3-Code.md
│   │   ├── Binary-to-Gray.md
│   │   ├── Gray-to-Binary.md
│   │   ├── BCD-to-Excess-3.md
│   │   └── Excess-3-to-BCD.md
│   │
│   ├── [05]-Boolean-Algebra
│   │   ├── Boolean-Basics.md
│   │   ├── Boolean-Laws.md
│   │   ├── DeMorgan-Theorem.md
│   │   └── Boolean-Expression.md
│   │
│   ├── [06]-Logic-Gates
│   │   ├── AND-Gate.md
│   │   ├── OR-Gate.md
│   │   ├── NOT-Gate.md
│   │   ├── NAND-Gate.md
│   │   ├── NOR-Gate.md
│   │   ├── XOR-Gate.md
│   │   └── XNOR-Gate.md
│   │
│   ├── [07]-Combinational-Logic
│   │   ├── Introduction.md
│   │   ├── Truth-Tables.md
│   │   ├── Minterms-Maxterms.md
│   │   └── Combinational-vs-Sequential.md
│   │
│   ├── [08]-Karnaugh-Map
│   │   ├── KMap-3-Variable.md
│   │   ├── KMap-4-Variable.md
│   │   └── Dont-Care-Conditions.md

│   ├── [09]-Combinational-Circuits
│   │   ├── Adders
│   │   │   ├── Half-Adder.md
│   │   │   ├── Full-Adder.md
│   │   │   └── Full-Adder-Using-Two-Half-Adder.md
│   │   ├── Subctractor
│   │   │   ├── Half-Subctractor.md
│   │   │   ├── Full-Subctractor.md
│   │   │   └── Full-Subctractor-Using-Two-Half-Subctractor.md
│   │   ├── Multiplexer
│   │   │   ├── 2x1.md
│   │   │   ├── 4x1.md
│   │   │   └── 8x1.md
│   │   ├── Demultiplexer
│   │   │   ├── 1x2.md
│   │   │   ├── 1x4.md
│   │   │   └── 1x8.md
│   │   ├── Decoder
│   │   │   ├── 2x4.md
│   │   │   └── 3x8.md
│   │   ├── Encoder
│   │   │   ├── 4x2.md
│   │   │   ├── 8x3.md
│   │   │   └── Priority-Encoder.md
│   │   └── Comparator
│   │   │   ├── 1-bit.md
│   │   │   ├── 2-bit.md
│   │   │   └── 3-bit.md
│   │   └── Ripple-Carry-Adder.md
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
│   │   ├── Register-Basics.md
│   │   ├── Shift-Registers.md
│   │   ├── SISO-Register.md
│   │   ├── SIPO-Register.md
│   │   ├── PISO-Register.md
│   │   └── PIPO-Register.md
│   │
│   ├── [12]-Counters
│   │   ├── Asynchronous-Counters
│   │   │   ├──3-Bit-Asynchoronous-Up-Counter.md
│   │   │   ├── 3-Bit-Asynchoronous-Down-Counter.md
│   │   │   ├── 4-Bit-Asynchoronous-Up-Counter.md
│   │   │   └── 4-Bit-Asynchoronous-Down-Counter.md
│   │   ├── Synchronous-Counters
│   │   │   ├── Up-Counter.md
│   │   │   ├── Down-Counter.md
│   │   │   ├── Up-Down-Counter.md
│   │   │   └── Mod-N-Counter.md
│   │   └── Special-Counters
│   │       ├── Ring-Counter.md
│   │       └── Johnson-Counter.md
│   │
│   └── [13]-Finite-State-Machines
│       ├── FSM-Introduction.md
│       ├── State-Diagram.md
│       ├── State-Table.md
│       ├── Moore-Machine.md
│       ├── Mealy-Machine.md
│       └── Sequence-Detector.md
│
├── Semiconductor-and-CMOS
│   │
│   ├── [01]-Semiconductor-Basics
│   │   ├── Semiconductor-Types.md 
│   │   ├── Intrinsic-Semiconductor.md 
│   │   ├── Extrinsic-Semiconductor.md 
│   │   ├── Doping.md 
│   │   ├── N-Type-Semiconductor.md 
│   │   ├── P-Type-Semiconductor.md 
│   │   ├── Semiconductor Manufacturing Process
│   │   ├── From Sand to Silicon
│   │   ├── Silicon Wafer Manufacturing
│   │   ├── Semiconductor Fabrication Plant
│   │   ├── Clean Room Technology
│   │   ├── Photolithography
│   │   ├── EUV Lithography
│   │   ├── Wafer Testing
│   │   ├── Chip Packaging
│   │   └──Semiconductor Ecosystem
│   │   
│   ├── [02]-MOS-Devices
│   │   ├── What is MOSFET.md
│   │   ├── NMOS.md
│   │   ├── PMOS.md
│   │   ├── MOS-Operation.md
│   │   └── Threshold-Voltage.md
│   │
│   └── [03]. CMOS Fundamentals
│        ├── [01]-CMOS-Basics
│         │ ├── What is CMOS?
│         │ ├── Complementary NMOS + PMOS
│         │ ├── CMOS Inverter
│         │    ├── CMOS Logic Operation
│         │    └── Pull-up and Pull-down Networks
│         │   
│         ├── [02]-CMOS Logic Gates
│          │   ├── CMOS NOT (Inverter)
│          │   ├── CMOS NAND
│          │   ├── CMOS NOR
│          │   ├── CMOS AND
│          │    ├── CMOS OR
│          │     └── CMOS XOR / XNOR (basic understanding)
│          │   
│          ├── [03]-CMOS Characteristics
│          │   ├── Logic 0 and Logic 1
│          │   ├── Voltage Levels
│          │   ├── Noise Margin
│          │   ├── Propagation Delay
│          │   ├── Rise Time
│          │     └── Fall Time
│          │     
│          ├── [04]-CMOS Power
│          │    ├── Dynamic Power
│          │    ├── Static Power
│          │    ├── Switching Activity
│          │    ├── Short-Circuit Power (basic)
│          │     └── Leakage Power (basic)
│          │     
│          └── [05]- CMOS Digital Design Concepts
│              ├── Fan-in
│              ├── Fan-out
│              ├── Load Capacitance
│              ├── Drive Strength (basic)
│              ├── PVT Variations (basic)
│               └── Process Technology Nodes (basic)
│
├── VLSI-Fundamentals
│   ├── [01]-Introduction-to-VLSI
│   │   ├── What-is-VLSI
│   │   ├── VLSI-Levels-of-Integration
│   │   ├── VLSI-Design-Types
│   │   ├── Digital-vs-Analog-IC
│   │   └── VLSI-Applications
│   │  
│   ├── [02]-ASIC-vs-FPGA
│   │    ├── ASIC
│   │    ├── FPGA
│   │    ├── ASIC-vs-FPGA
│   │    ├── Advantages-and-Disadvantages
│   │    └── RTL-in-ASIC-and-FPGA
│   │
│   ├── [03]-Front-End-vs-Back-End
│   │    ├── Front-End-Design
│   │    ├── RTL-Design
│   │    ├── Functional-Verification
│   │    ├── Logic-Synthesis
│   │    ├── Back-End-Design
│   │    └── Physical-Design
│   │  
│   ├── [04]-RTL-to-GDSII-Flow
│   │   ├── Specification
│   │   ├── RTL-Coding
│   │   ├── Functional-Verification
│   │   ├── Logic-Synthesis
│   │   ├── Floor-planning
│   │   ├── Placement
│   │   ├── Clock-Tree-Synthesis
│   │   ├── Routing
│   │   ├── STA
│   │   ├── Physical-Verification
│   │   └── GDSII
│   │   
│   ├── [05]-PPA
│   │   ├── Power
│   │   ├── Performance
│   │   ├── Area
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
├──Timing-Concepts
│ ├── 01-Clock-Concepts.md
│ ├── 02-Clock-Frequency-and-Period.md      
│ ├── 03-Propagation-Delay.md
│ ├── 04-Contamination-Delay.md             
│ ├── 05-Rise-Time.md
│ ├── 06-Fall-Time.md
│ ├── 07-Setup-Time.md
│ ├── 08-Hold-Time.md
│ ├── 09-Clock-Skew.md
│ ├── 10-Clock-Jitter.md
│ ├── 11-Arrival-Time.md                    
│ ├── 12-Required-Time.md                   
│ └── 13-Timing-Diagrams.md
│       
└── STA-Basics
  ├── 01-Introduction-to-STA.md             
  ├── 02-Timing-Paths.md
  ├── 03-Setup-Analysis.md
  ├── 04-Hold-Analysis.md
  ├── 05-Timing-Violations.md
  ├── 06-Slack-Analysis.md
  ├── 07-Timing-Constraints.md
  ├── 08-Critical-Path.md
  ├── 09-Timing-Reports.md
  ├── 10-Input-and-Output-Delay.md          
  ├── 11-False-Path-Basics.md               
  ├── 12-Multicycle-Path-Basics.md          
  └── 13-Timing-Closure-Basics.md               

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

# 🛠️ Tools Used

<p>
<img src="https://skillicons.dev/icons?i=github,git,vscode,linux"/>
</p>

---

# 🔗 Next Learning Stage

This repository builds the foundation for:

➡ Verilog RTL Design  
➡ SystemVerilog Verification  
➡ FPGA Implementation  
➡ ASIC Design Flow

