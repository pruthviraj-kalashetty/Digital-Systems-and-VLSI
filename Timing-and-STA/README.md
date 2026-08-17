<div align="center">

# ⚡ DIGITAL DESIGN & VLSI FUNDAMENTALS

### Digital Electronics • Semiconductor Physics • CMOS • Static Timing Analysis • RTL Foundation

<p align="center">
  <img src="https://img.shields.io/badge/DOMAIN-VLSI_ENGINEERING-0F172A?style=for-the-badge&logo=microchip&logoColor=020617&color=2563EB" alt="Domain"/>
  <img src="https://img.shields.io/badge/FOCUS-DIGITAL_DESIGN-0F172A?style=for-the-badge&logo=cpu&logoColor=020617&color=06B6D4" alt="Focus"/>
  <img src="https://img.shields.io/badge/LOGIC-COMBINATIONAL_%26_SEQUENTIAL-0F172A?style=for-the-badge&color=10B981" alt="Logic"/>
  <img src="https://img.shields.io/badge/FSM-FINITE_STATE_MACHINES-0F172A?style=for-the-badge&color=8B5CF6" alt="FSM"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/TIMING-STA_%26_TIMING_ANALYSIS-0F172A?style=for-the-badge&color=3B82F6" alt="Timing"/>
  <img src="https://img.shields.io/badge/CMOS-SEMICONDUCTOR_PHYSICS-0F172A?style=for-the-badge&color=14B8A6" alt="CMOS"/>
  <img src="https://img.shields.io/badge/PURPOSE-RTL_DESIGN_FOUNDATION-0F172A?style=for-the-badge&color=F97316" alt="Purpose"/>
</p>

</div>

---

## 📌 About This Repository

This repository serves as a core theoretical foundation for **RTL Design** and **ASIC/FPGA Front-End Engineering**. It systematically documents essential hardware concepts required prior to writing synthesizable Verilog code.

### 🎯 Key Knowledge Domains
* **Digital Logic Architecture:** Combinational logic, state machines, and register transfer principles.
* **Semiconductor Physics & CMOS:** Device operation, layout characteristics, and power dynamics.
* **ASIC/VLSI Flow:** RTL-to-GDSII methodology, PPA trade-offs, and physical limitations.
* **Static Timing Analysis (STA):** Setup/hold timing closures, clock domains, and skew analysis.

---

## 🛠️ Tools & Environment

<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=linux,vscode,git,github" alt="Development Tools" />
  </a>
</p>

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

<details>
<summary><b>2️⃣ Semiconductor Fundamentals</b></summary>

* **Physics & Materials:** Intrinsic & Extrinsic Semiconductors, Doping Dynamics, PN Junction Characteristics.
* **Manufacturing & Fabrication:** Wafer Fabrication, Cleanroom Standards, Photolithography, EUV Lithography.
* **Industry Ecosystem:** Chip Packaging Technologies, Wafer Testing, Semiconductor Supply Chain.
</details>

<details>
<summary><b>3️⃣ MOS & CMOS Technology</b></summary>

* **MOSFET Devices:** NMOS, PMOS Structures, Channel Formation, Threshold Voltage ($V_{th}$).
* **CMOS Logic:** CMOS Inverter, Complementary Pull-Up (PUN) / Pull-Down (PDN) Networks, NAND/NOR Gates.
* **Design Metrics:** Noise Margins, Dynamic & Static Power Dissipation, Leakage Currents, Fan-in / Fan-out Limits.
</details>

<details>
<summary><b>4️⃣ VLSI Engineering Principles</b></summary>

* **Design Methodologies:** ASIC vs. FPGA Architectures, Front-End vs. Back-End Workflows.
* **RTL-to-GDSII Flow:** Synthesis, Floorplanning, Placement, Clock Tree Synthesis (CTS), Routing, Physical Verification.
* **Optimization Parameters:** PPA (Power, Performance, Area) Trade-offs, Parasitic RC Delays, Logical Effort.
</details>

<details>
<summary><b>5️⃣ Timing & Static Timing Analysis (STA)</b></summary>

* **Clock & Delay Metrics:** Clock Skew, Jitter, Propagation Delay, Contamination Delay, Rise/Fall Times.
* **Timing Constraints:** Setup Time ($t_{setup}$), Hold Time ($t_{hold}$), Data Arrival Time, Data Required Time.
* **STA & Verification:** Critical Path Analysis, Setup/Hold Violations, Slack Computation, False Paths, Multicycle Paths.
</details>

---

## 🏗️ Directory Structure

```text
.
├── Digital-Electronics/
│   ├── [01]-Digital-Basics/
│   │   ├── Digital-vs-Analog.md
│   │   └── Digital-System-Overview.md
│   ├── [02]-Number-Systems/
│   ├── [03]-Binary-Arithmetic/
│   ├── [04]-Binary-Codes/
│   ├── [05]-Boolean-Algebra/
│   ├── [06]-Logic-Gates/
│   ├── [07]-Combinational-Logic/
│   ├── [08]-Karnaugh-Map/
│   ├── [09]-Combinational-Circuits/
│   │   ├── Adders/
│   │   ├── Subtractors/
│   │   ├── Multiplexers/
│   │   ├── Demultiplexers/
│   │   ├── Decoders/
│   │   ├── Encoders/
│   │   └── Comparators/
│   ├── [10]-Flip-Flops/
│   ├── [11]-Registers/
│   ├── [12]-Counters/
│   └── [13]-Finite-State-Machines/
├── Semiconductor-and-CMOS/
│   ├── [01]-Semiconductor-Basics/
│   ├── [02]-MOS-Devices/
│   └── [03]-CMOS-Fundamentals/
│       ├── [01]-CMOS-Basics/
│       ├── [02]-CMOS-Logic-Gates/
│       ├── [03]-CMOS-Characteristics/
│       ├── [04]-CMOS-Power/
│       └── [05]-Digital-Design-Concepts/
├── VLSI-Fundamentals/
│   ├── [01]-Introduction-to-VLSI/
│   ├── [02]-ASIC-vs-FPGA/
│   ├── [03]-Front-End-vs-Back-End/
│   ├── [04]-RTL-to-GDSII-Flow/
│   ├── [05]-PPA-Optimization/
│   ├── [06]-Parasitic-RC/
│   └── [07]-Logical-Effort/
├── Timing-Concepts/
│   ├── 01-Clock-Concepts.md
│   ├── 02-Propagation-Delay.md
│   ├── 03-Setup-and-Hold-Time.md
│   └── 04-Clock-Skew-and-Jitter.md
└── STA-Basics/
    ├── 01-Introduction-to-STA.md
    ├── 02-Timing-Paths.md
    ├── 03-Setup-and-Hold-Analysis.md
    ├── 04-Slack-Computation.md
    └── 05-Timing-Exceptions.md
