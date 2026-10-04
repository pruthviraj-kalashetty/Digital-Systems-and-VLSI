# **Physical Design**

* **Overview**

Physical Design is the process of converting a synthesized gate-level netlist into a physical layout of an integrated circuit. It determines the physical locations of cells and blocks, creates clock and signal connections, and verifies that the design meets **timing, power, area, and manufacturing requirements**.

---

* **Definition**

Physical Design is the stage of VLSI design in which the logical gate-level representation of a circuit is transformed into its physical implementation using **floorplanning, placement, clock tree synthesis, routing, extraction, timing analysis, and physical verification**.

---

* **Why is it needed?**

RTL and synthesis describe the logical structure of a circuit, but they do not determine where the hardware will physically exist on the silicon.

Physical Design is needed to:

- Place standard cells and macros on the chip.
- Create physical clock distribution.
- Connect cells using metal layers.
- Meet timing requirements.
- Control power consumption.
- Optimize chip area.
- Reduce routing congestion.
- Satisfy manufacturing design rules.
- Prepare the final design for fabrication.

Without Physical Design, the synthesized logic cannot become a manufacturable chip.

---

* **Working Principle**

The simplified Physical Design flow is:

```text id="pdflow01"
Synthesized Gate-Level Netlist
              │
              ▼
        Floorplanning
              │
              ▼
          Placement
              │
              ▼
   Clock Tree Synthesis (CTS)
              │
              ▼
           Routing
              │
              ▼
    Parasitic Extraction
              │
              ▼
 Timing / Power / Physical Analysis
              │
              ▼
      Physical Verification
              │
              ▼
           Signoff
              │
              ▼
           Tapeout
```

The flow is iterative. If timing, congestion, power, or physical verification fails, the design may return to an earlier stage for optimization.

---

* **Floorplanning**

Floorplanning is the first major physical implementation step.

It determines the overall physical organization of the chip.

Important decisions include:

- Core size
- Die size
- Aspect ratio
- Macro locations
- I/O locations
- Standard-cell regions
- Power distribution planning
- Routing resources

Simplified example:

```text id="pdflow02"
+--------------------------------------+
|                CHIP                  |
|                                      |
|   +---------+       +---------+      |
|   | Memory  |       | Memory  |      |
|   |  Macro  |       |  Macro  |      |
|   +---------+       +---------+      |
|                                      |
|        Standard Cell Region           |
|                                      |
|   +------------------------------+   |
|   |          Logic Area          |   |
|   +------------------------------+   |
|                                      |
+--------------------------------------+
```

A poor floorplan can cause routing congestion and timing problems later.

---

* **Placement**

Placement determines the physical locations of standard cells.

For example:

```text id="pdflow03"
+--------------------------------+
|                                |
|  FF1    AND1    OR1     FF2    |
|                                |
|  FF3    MUX1    ADDER   FF4    |
|                                |
|  BUF1   BUF2    BUF3           |
|                                |
+--------------------------------+
```

The placement process attempts to optimize:

- Timing
- Wirelength
- Congestion
- Area
- Power

Cells that communicate heavily may need to be placed appropriately to reduce excessive interconnect delay.

---

* **Clock Tree Synthesis**

Clock Tree Synthesis, or **CTS**, creates the physical clock network connecting the clock source to sequential elements.

Simplified structure:

```text id="pdflow04"
                 Clock Source
                      │
                  ┌───┴───┐
                  │       │
                Buffer   Buffer
                  │       │
             ┌────┴─┐   ┌─┴────┐
             │      │   │      │
            FF1    FF2 FF3    FF4
```

CTS attempts to control:

- Clock skew
- Clock latency
- Clock transition
- Clock insertion delay
- Clock power

Clock distribution is critical because a large digital chip may contain millions of sequential elements.

---

* **Routing**

Routing creates physical connections between cells using metal layers and vias.

There are generally two major stages:

**Global Routing**

Determines approximate routing paths and available routing resources.

**Detailed Routing**

Creates the final physical metal and via connections while following design rules.

Simplified example:

```text id="pdflow05"
+------+                    +------+
| FF1  |====================| AND1 |
+------+      Metal Wire   +------+
                               |
                               |
                               | Metal
                               |
                           +-------+
                           |  FF2  |
                           +-------+
```

Routing must consider:

- Connectivity
- Wirelength
- Timing
- Congestion
- Signal integrity
- Design rules
- Available metal resources

---

* **Parasitic Extraction**

Physical wires are not ideal.

They introduce:

- Resistance
- Capacitance

These unwanted electrical effects are called **parasitics**.

```text id="pdflow06"
          Physical Wire
               │
        ┌──────┴──────┐
        │             │
    Resistance    Capacitance
        │             │
        └──────┬──────┘
               ▼
          Delay / Power
```

Parasitic extraction generates information about these physical effects.

This information is then used for more accurate timing and power analysis.

---

* **Static Timing Analysis**

After physical implementation, timing is analyzed using the physical design and extracted parasitic information.

A simplified timing path is:

```text id="pdflow07"
Launch FF
    │
    ▼
Combinational Logic
    │
    ▼
Physical Interconnect
    │
    ▼
Capture FF
```

Important parameters include:

- Clock-to-Q delay
- Combinational delay
- Setup time
- Hold time
- Clock skew
- Clock latency
- Slack
- Critical path

A simplified setup relationship is:

```text id="pdflow08"
Clock Period ≥
Clock-to-Q Delay
+ Combinational Delay
+ Setup Time
+ Timing Margin
```

If the required timing is not achieved, the design requires optimization.

---

* **Timing Closure**

Timing closure means achieving the required timing constraints across the relevant timing scenarios.

Two important checks are:

**Setup Timing**

Checks whether data arrives early enough before the capture clock edge.

**Hold Timing**

Checks whether data remains stable for the required time after the capture clock edge.

Simplified:

```text id="pdflow09"
Setup:
Data --------------------->| Capture Edge
                    must arrive early enough

Hold:
Capture Edge |--------------------> Data must
              remain stable
```

Timing closure may require:

- Cell resizing
- Buffer insertion
- Logic restructuring
- Placement optimization
- Routing optimization
- Clock optimization

---

* **Power Analysis**

Physical Design also affects power consumption.

Major components are:

```text id="pdflow10"
Total Power
     │
     ├── Dynamic Power
     ├── Short-Circuit Power
     └── Leakage Power
```

Physical factors such as:

- Wire capacitance
- Clock network
- Cell selection
- Switching activity
- Buffering

can influence power.

---

* **Area Optimization**

Physical Design attempts to fit the design into the required silicon area.

Area depends on:

- Number of cells
- Cell sizes
- Memory macros
- Routing resources
- Power structures
- Design margins

Reducing area is useful, but excessive area optimization can negatively affect timing or routing.

Therefore, Physical Design is a trade-off between **Power, Performance, and Area (PPA)**.

---

* **Congestion**

Congestion occurs when too many signals need to use limited routing resources in a physical region.

Example:

```text id="pdflow11"
        Many Connections
        ↓  ↓  ↓  ↓  ↓
+-------------------------+
| || || || || || || || | |
| || || || || || || || | |
| || || || || || || || | |
+-------------------------+
       Limited Routing
          Resources
```

High congestion can cause:

- Routing failures
- Longer wires
- Timing problems
- Increased power
- Design-rule violations

Good floorplanning and placement help reduce congestion.

---

* **Physical Verification**

Physical verification checks whether the final layout is physically and logically correct.

### **DRC — Design Rule Check**

DRC verifies that the layout follows manufacturing rules.

Examples:

- Minimum metal width
- Minimum spacing
- Via rules
- Metal enclosure rules
- Layer-specific restrictions

### **LVS — Layout Versus Schematic**

LVS verifies whether the physical layout has the intended connectivity.

Simplified concept:

```text
Gate-Level Netlist
        │
        │ Compare
        ▼
Physical Layout
```

The goal is to ensure that the layout represents the intended circuit.

---

* **Signoff**

Signoff is the final verification stage before tapeout.

Important signoff areas can include:

- Timing
- Power
- Physical verification
- Signal integrity
- Reliability
- Design-rule compliance
- Manufacturability

The exact signoff requirements depend on the technology and project.

Once the design successfully passes the required signoff checks, it can proceed toward **tapeout**.

---

* **Tapeout**

Tapeout is the point at which the finalized physical design database is released for semiconductor manufacturing.

Simplified:

```text id="pdflow12"
RTL
 │
 ▼
Synthesis
 │
 ▼
Gate-Level Netlist
 │
 ▼
Physical Design
 │
 ▼
Signoff
 │
 ▼
Tapeout
 │
 ▼
Fabrication
 │
 ▼
Wafer
 │
 ▼
Packaging & Testing
```

Tapeout does not mean the physical chip has already been manufactured. It means the final design data has been released for manufacturing.

---

* **Physical Design vs RTL Design**

| RTL Design | Physical Design |
|---|---|
| Describes hardware behavior and structure | Implements hardware physically |
| Uses HDL such as Verilog | Uses physical implementation tools |
| Works mainly with RTL | Works mainly with gate-level netlist and physical data |
| Defines registers and combinational logic | Places cells and creates physical connections |
| Creates synthesizable RTL | Creates physical layout |
| Functional correctness is a major concern | Timing, power, area, and physical correctness are major concerns |
| Simulation is commonly used | Placement, routing, extraction, and signoff tools are commonly used |

The relationship is:

```text id="pdflow13"
Specification
     │
     ▼
Architecture
     │
     ▼
RTL Design
     │
     ▼
Functional Verification
     │
     ▼
Logic Synthesis
     │
     ▼
Gate-Level Netlist
     │
     ▼
Physical Design
     │
     ▼
Physical Layout
```

---

* **Back-End Design vs Physical Design**

The terms **Back-End Design** and **Physical Design** are often used very closely and can overlap.

A useful practical understanding is:

```text id="pdflow14"
Front-End Design
    │
    ├── Architecture
    ├── RTL Design
    ├── Functional Verification
    └── Synthesis
              │
              ▼
       Gate-Level Netlist
              │
              ▼
Back-End / Physical Design
    │
    ├── Floorplanning
    ├── Placement
    ├── CTS
    ├── Routing
    ├── Extraction
    ├── Timing / Power Analysis
    └── Physical Verification
```

In many industry contexts, **Physical Design is a major part of the Back-End Design flow**, and the two terms may be used almost interchangeably depending on the organization.

---

* **Input & Output Description**

| Input | Description |
|---|---|
| Gate-level netlist | Synthesized logical representation |
| Technology libraries | Cell timing, power, and physical information |
| Timing constraints | Clock and timing requirements |
| Physical constraints | Area, floorplan, macro and placement requirements |
| Power constraints | Power-related requirements |
| Design rules | Manufacturing constraints |

| Output | Description |
|---|---|
| Placed design | Physical cell locations |
| Clock tree | Physical clock distribution |
| Routed design | Physical signal connections |
| Extracted parasitics | Physical resistance and capacitance information |
| Timing reports | Timing analysis results |
| Power reports | Power analysis results |
| DRC/LVS reports | Physical verification results |
| Final physical database | Data used for tapeout |

---

* **Working Example**

Suppose synthesis produces the following logical structure:

```text id="pdflow15"
FF1
 │
 ▼
AND Gate
 │
 ▼
MUX
 │
 ▼
FF2
```

Physical Design converts this logical structure into something like:

```text id="pdflow16"
+---------------------------------------+
|                                       |
|  FF1        AND        MUX       FF2  |
|  [ ] ====== [ ] ====== [ ] ====== [ ]|
|                                       |
|          Physical Metal               |
|                                       |
+---------------------------------------+
```

The Physical Design process determines:

1. Where FF1 is placed.
2. Where the AND gate is placed.
3. Where the MUX is placed.
4. Where FF2 is placed.
5. How the clock reaches FF1 and FF2.
6. Which metal layers carry the signals.
7. How much delay the physical wires introduce.
8. Whether setup and hold timing are satisfied.
9. Whether routing follows manufacturing rules.

Therefore:

> **Synthesis determines the logical hardware structure; Physical Design determines its physical implementation.**

---

* **Applications**

Physical Design is required for the implementation of:

- CPUs
- GPUs
- Microprocessors
- Microcontrollers
- SoCs
- AI accelerators
- DSP processors
- Network processors
- Memory controllers
- Communication ICs
- Automotive ICs
- High-performance computing chips
- Custom ASICs

---

* **Advantages**

- Converts logical hardware into physical implementation.
- Enables timing optimization.
- Helps optimize power and area.
- Creates manufacturable chip layouts.
- Identifies routing and congestion problems.
- Enables physical verification.
- Supports timing and power signoff.
- Prepares the final design for tapeout.

---

* **Limitations**

- Highly complex for large modern chips.
- Requires accurate technology information.
- Timing closure can require multiple iterations.
- Routing congestion can become difficult.
- Physical implementation can be computationally expensive.
- Late-stage changes can require significant rework.
- Power, timing, area, and routing objectives can conflict.

---

* **Real-World Example**

Consider a modern smartphone SoC containing:

```text id="pdflow17"
CPU Cores
GPU
Cache
Memory Controller
Interconnect
AI Accelerator
I/O Controllers
```

The RTL and verification teams ensure that these blocks function correctly.

After synthesis, Physical Design implements the resulting logic physically.

The Physical Design team determines:

- Where major blocks are located.
- Where standard cells are placed.
- How clocks are distributed.
- How signals are routed.
- Whether timing is achieved.
- Whether power targets are met.
- Whether the layout follows manufacturing rules.

After successful signoff, the design proceeds to tapeout and fabrication.

---

* **Key Points**

1. Physical Design converts a synthesized netlist into a physical chip layout.
2. It is a major part of the VLSI Back-End flow.
3. Major stages include **floorplanning, placement, CTS, routing, extraction, analysis, and physical verification**.
4. Floorplanning determines the overall physical organization.
5. Placement determines standard-cell locations.
6. CTS creates the physical clock network.
7. Routing creates physical metal connections.
8. Parasitic extraction captures resistance and capacitance effects.
9. Timing closure ensures required timing constraints are met.
10. DRC checks physical manufacturing rules.
11. LVS checks logical connectivity against the physical layout.
12. PPA means **Power, Performance, and Area**.
13. Physical Design is highly iterative.
14. Successful signoff leads toward tapeout.
15. RTL designers should understand Physical Design because RTL decisions can affect physical **timing, power, area, and congestion**.

---

* **Interview Questions**

**1. What is Physical Design?**

Physical Design is the process of converting a synthesized gate-level netlist into a physically implementable chip layout.

**2. What are the main stages of Physical Design?**

Floorplanning, placement, clock tree synthesis, routing, parasitic extraction, timing/power analysis, physical verification, and signoff.

**3. What is floorplanning?**

Floorplanning determines the physical organization of the chip, including core area, macros, I/O regions, and major block locations.

**4. What is placement?**

Placement determines the physical locations of standard cells.

**5. What is CTS?**

Clock Tree Synthesis creates the physical clock distribution network connecting the clock source to sequential elements.

**6. Why is clock skew important?**

Clock skew is the difference in clock arrival time between sequential elements. Excessive skew can cause setup or hold timing problems.

**7. What is routing?**

Routing creates the physical metal and via connections between placed cells and blocks.

**8. What are parasitics?**

Parasitics are unwanted resistance and capacitance associated with physical interconnections.

**9. What is congestion?**

Congestion occurs when the demand for routing resources exceeds the available routing capacity in a physical region.

**10. What is DRC?**

DRC stands for Design Rule Check. It verifies that the layout follows manufacturing design rules.

**11. What is LVS?**

LVS stands for Layout Versus Schematic. It checks whether the physical layout has the intended connectivity.

**12. What is timing closure?**

Timing closure is the process of achieving all required timing constraints for the design.

**13. What is the difference between synthesis and Physical Design?**

Synthesis converts RTL into a gate-level representation. Physical Design places and connects those gates physically and creates the chip layout.

**14. Why are parasitics important?**

Physical wires have resistance and capacitance that affect delay, power, and signal behavior. Therefore, extracted parasitics are important for accurate post-layout analysis.

**15. Why should an RTL Design Engineer understand Physical Design?**

Because RTL coding decisions can influence synthesized hardware, timing, area, power, routing complexity, and ultimately the physical implementation.

---

* **Quick Revision**

```text id="pdflow18"
Physical Design
      │
      ▼
Floorplanning
      │
      ▼
Placement
      │
      ▼
CTS
      │
      ▼
Routing
      │
      ▼
Parasitic Extraction
      │
      ▼
Timing / Power Analysis
      │
      ▼
DRC / LVS
      │
      ▼
Signoff
      │
      ▼
Tapeout
```

**Remember:**

> **RTL Design → Describes the hardware**

> **Synthesis → Converts RTL into gates**

> **Physical Design → Places and connects those gates physically**

> **Signoff → Confirms the implementation is ready for tapeout**

---

* **Summary**

Physical Design is the process of transforming a synthesized gate-level netlist into a physical, manufacturable chip layout. It includes **floorplanning, placement, clock tree synthesis, routing, parasitic extraction, timing and power analysis, physical verification, and signoff**.

For an RTL Design Engineer, Physical Design is important because RTL is not isolated from the physical chip. RTL architecture and coding choices can ultimately affect **timing, power, area, routing, and physical implementation quality**.

---

* **References**

- Neso Academy — VLSI Design and Physical Design concepts
- All About Electronics — VLSI and Digital Electronics concepts
- Neil H. E. Weste & David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Jan M. Rabaey, Anantha Chandrakasan & Borivoje Nikolić — *Digital Integrated Circuits*
