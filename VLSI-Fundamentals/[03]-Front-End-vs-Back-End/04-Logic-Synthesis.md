# **Logic Synthesis**

- **Overview**

Logic Synthesis is the process of converting synthesizable RTL into a gate-level hardware representation that can be implemented in a target technology. It connects RTL design with actual hardware implementation and is a major stage of the VLSI front-end design flow.

---

- **Definition**

**Logic Synthesis** is the automated process of transforming synthesizable HDL/RTL into a gate-level netlist using a target technology library or device architecture while attempting to satisfy functional, timing, area, and power requirements.

```text
RTL
 ↓
Logic Synthesis
 ↓
Gate-Level Netlist
```

For ASIC:

```text
RTL
 ↓
ASIC Synthesis
 ↓
Technology-Mapped Gate Netlist
```

For FPGA:

```text
RTL
 ↓
FPGA Synthesis
 ↓
Technology-Specific Logic Representation
```

---

- **Why is Logic Synthesis Needed?**

RTL is a behavioral and structural description of digital hardware. It is not normally the final physical representation used to manufacture or configure the target device.

For example:

```verilog
always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

A synthesis tool can recognize this as hardware containing a flip-flop and associated control logic.

The overall concept is:

```text
Human-Readable RTL
        ↓
     Synthesis
        ↓
Hardware Structures
```

Logic synthesis therefore bridges the gap between **RTL description** and **implementation-oriented hardware**.

---

- **Basic Synthesis Flow**

A simplified synthesis flow is:

```text
RTL
 │
 ↓
RTL Elaboration
 │
 ↓
Logic Optimization
 │
 ↓
Technology Mapping
 │
 ↓
Gate-Level Netlist
```

The exact sequence depends on the synthesis tool and technology.

---

- **1. RTL Input**

The synthesis tool receives synthesizable HDL source files.

Example:

```verilog
module and_gate (
    input  a,
    input  b,
    output y
);

assign y = a & b;

endmodule
```

The RTL describes the required logic function.

---

- **2. Elaboration**

During elaboration, the synthesis tool builds an internal representation of the complete design.

It resolves things such as:

- Module hierarchy
- Parameters
- Generate constructs
- Port connections
- Signal widths
- Design instances

Example:

```text
Top Module
    │
    ├── Controller
    │
    ├── Datapath
    │
    └── Memory Interface
```

The tool must understand how all these modules connect before synthesis proceeds.

---

- **3. RTL Optimization**

The synthesis tool analyzes the RTL representation and attempts to simplify or optimize the hardware while preserving the required functionality.

Conceptually:

```text
RTL Hardware
      ↓
Optimization
      ↓
Equivalent but Better Hardware
```

Possible goals include reducing:

- Logic area
- Delay
- Power
- Unnecessary logic

For example:

```text
A AND 1
```

can be simplified to:

```text
A
```

The actual optimization performed depends on the synthesis tool and constraints.

---

- **4. Technology Mapping**

After logic optimization, the design is mapped to resources available in the target technology.

### **ASIC**

The design can be mapped to cells from a standard-cell library.

```text
Optimized Logic
      ↓
ASIC Technology Library
      ↓
Standard Cells
```

Examples:

- AND
- OR
- NAND
- NOR
- XOR
- Multiplexer
- Flip-flop
- Buffer

### **FPGA**

The logic is mapped toward the programmable resources of the target FPGA.

Examples include:

- LUTs
- Flip-flops
- BRAM
- DSP resources
- Carry logic

```text
RTL
 ↓
FPGA Synthesis
 ↓
FPGA Resources
```

---

- **5. Gate-Level Netlist**

The final synthesis result for a typical ASIC flow is a gate-level netlist.

A netlist describes:

- Cells
- Instances
- Nets
- Connections

Example:

```text
RTL:
Y = (A & B) | C
```

Conceptually:

```text
A ──┐
    ├── AND ──┐
B ──┘         │
              ├── OR ──► Y
C ────────────┘
```

The netlist represents the hardware required to implement the function.

---

- **RTL vs Gate-Level Netlist**

| RTL | Gate-Level Netlist |
|---|---|
| Higher-level hardware description | Lower-level implementation representation |
| Written using HDL | Describes cells and connections |
| Easier for designers to modify | More implementation-oriented |
| Technology-independent in many cases | Technology-dependent for ASIC |
| Describes intended hardware behavior | Describes mapped hardware structure |
| Input to synthesis | Output of synthesis |

Simplified:

```text
RTL
 ↓
Synthesis
 ↓
Gate-Level Netlist
```

---

- **Logic Synthesis Example**

Consider a simple 2-to-1 multiplexer.

RTL:

```verilog
module mux2to1 (
    input  a,
    input  b,
    input  sel,
    output reg y
);

always @(*)
begin
    if (sel)
        y = b;
    else
        y = a;
end

endmodule
```

The synthesis tool recognizes the required multiplexer behavior.

Conceptually:

```text
        a ─────┐
               │
               ├──► MUX ───► y
               │
        b ─────┘
                ▲
                │
               sel
```

The exact physical implementation depends on the target technology.

---

- **Sequential Logic Synthesis**

Consider:

```verilog
always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

Synthesis recognizes storage behavior.

Conceptually:

```text
        d
        │
        ▼
   ┌──────────┐
   │ Flip-Flop│
   └────┬─────┘
        │
        ▼
        q
        ▲
        │
       clk
```

For an ASIC, this may map to a standard-cell flip-flop.

For an FPGA, it normally maps to a flip-flop associated with programmable logic resources.

---

- **Synthesis Constraints**

Synthesis needs design constraints to optimize the hardware toward required operating conditions.

Important constraints can include:

- Clock definitions
- Input delays
- Output delays
- Timing requirements
- Design rules
- Area limits
- Operating conditions

A simplified example:

```text
Clock Frequency = 100 MHz

Clock Period = 1 / Frequency

             = 1 / 100 MHz

             = 10 ns
```

The synthesis tool can use this timing requirement when optimizing the design.

---

- **Timing During Synthesis**

A simplified timing path is:

```text
Launch Flip-Flop
       │
       ↓
Combinational Logic
       │
       ↓
Capture Flip-Flop
```

The synthesis tool attempts to optimize the logic so that timing requirements can be satisfied.

Important concepts include:

- Clock period
- Clock-to-Q delay
- Combinational delay
- Setup time
- Hold time
- Timing slack

Simplified setup relationship:

```text
Clock Period
   ≥
Clock-to-Q
+
Combinational Delay
+
Setup Time
+
Timing Margin
```

The exact timing equations used in implementation depend on the timing model and constraints.

---

- **Synthesis and PPA**

Synthesis is strongly connected to:

**PPA = Power, Performance, and Area**

```text
                 Synthesis
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
      Power      Performance     Area
```

### **Power**

The synthesis tool may optimize logic to reduce unnecessary switching and power.

### **Performance**

The tool attempts to reduce critical-path delay and meet timing constraints.

### **Area**

The tool attempts to implement the required functionality using an efficient amount of hardware.

There are often trade-offs between these objectives.

---

- **Critical Path**

The critical path is generally the timing path with the most restrictive timing requirement or the path with the worst timing slack.

Example:

```text
FF1
 │
 ↓
Logic 1
 │
 ↓
Logic 2
 │
 ↓
Logic 3
 │
 ↓
FF2
```

If this path takes too long:

```text
Required Time < Actual Arrival Time
```

the design can have a timing violation.

A simplified timing goal is:

```text
Timing Slack ≥ 0
```

for the relevant constrained path.

---

- **Timing Slack**

Slack indicates the amount of timing margin available.

Conceptually:

```text
Slack = Required Time - Arrival Time
```

For a setup check:

```text
Positive Slack → Timing Requirement Met
Zero Slack     → No Timing Margin
Negative Slack → Timing Violation
```

Synthesis uses timing constraints to help optimize problematic paths.

---

- **Synthesis Optimization**

Synthesis tools can perform different optimization techniques, depending on the tool and target technology.

Examples include:

- Logic simplification
- Constant propagation
- Boolean optimization
- Redundant logic removal
- Resource sharing
- Buffer optimization
- Logic restructuring
- Register optimization
- Technology mapping

The objective is to preserve functionality while improving implementation characteristics.

---

- **Synthesis and Verification**

Synthesis itself does not replace functional verification.

```text
RTL
 │
 ├──────────────► Functional Verification
 │                       ↓
 │                  Check Function
 │
 └──────────────► Synthesis
                         ↓
                  Create Hardware
```

A design should be functionally verified before relying on the synthesized implementation.

Post-synthesis or gate-level simulation may also be performed when required by the project.

---

- **RTL Simulation vs Gate-Level Simulation**

### **RTL Simulation**

```text
RTL + Testbench
      ↓
Simulation
```

Used primarily to verify functional behavior at the RTL level.

### **Gate-Level Simulation**

```text
Gate-Level Netlist
        +
   Testbench
        ↓
    Simulation
```

Used when the project requires verification of the synthesized implementation, potentially including timing information.

RTL simulation is generally faster and is the primary functional-debugging environment.

---

- **ASIC Synthesis Flow**

A simplified ASIC synthesis flow is:

```text
RTL
 ↓
Elaboration
 ↓
Constraints
 ↓
Logic Optimization
 ↓
Technology Mapping
 ↓
Gate-Level Netlist
 ↓
Timing / Area / Power Analysis
 ↓
Physical Design
```

The netlist is then passed to downstream physical-design stages.

---

- **FPGA Synthesis Flow**

A simplified FPGA flow is:

```text
RTL
 ↓
Elaboration
 ↓
Synthesis
 ↓
Technology Mapping
 ↓
Optimization
 ↓
Placement
 ↓
Routing
 ↓
Timing Analysis
 ↓
Bitstream
```

The exact tool flow varies by FPGA vendor.

---

- **ASIC vs FPGA Synthesis**

| Feature | ASIC Synthesis | FPGA Synthesis |
|---|---|---|
| Target | ASIC technology | FPGA device |
| Mapping | Standard cells/macros | LUTs, FFs, BRAM, DSP, etc. |
| Output | Technology-mapped netlist | FPGA implementation data |
| Optimization | PPA and technology constraints | Device resources and timing |
| Physical implementation | Separate downstream stage | Usually integrated with FPGA implementation flow |
| Final hardware | Fabricated IC | Programmable device |

The same RTL can sometimes be synthesized for both targets, but the resulting implementation is different.

---

- **Synthesis and RTL Coding Style**

RTL coding style can affect the synthesized hardware.

For example:

```verilog
if (sel)
    y = b;
else
    y = a;
```

can represent a multiplexer.

Poor or incomplete combinational RTL may unintentionally infer storage.

Example:

```verilog
always @(*)
begin
    if (enable)
        y = a;
end
```

If `enable` is false, `y` has no assigned value in this block, which can lead to latch inference.

A safer complete combinational description is:

```verilog
always @(*)
begin
    y = 1'b0;

    if (enable)
        y = a;
end
```

Therefore, an RTL designer must understand how coding constructs are interpreted by synthesis tools.

---

- **Synthesizable RTL**

Common synthesizable constructs include:

- `always @(*)`
- `always @(posedge clk)`
- `if`
- `case`
- Appropriate `for` loops
- Arithmetic operators
- Comparisons
- Registers
- Combinational logic
- Parameters

The exact synthesizability depends on the construct, tool, and target technology.

Some HDL constructs are primarily for simulation and do not represent hardware that can be synthesized.

---

- **Logic Synthesis and RTL Design**

RTL Design and Logic Synthesis are closely connected.

```text
RTL Designer
      ↓
Synthesizable RTL
      ↓
Synthesis Tool
      ↓
Hardware Representation
      ↓
Timing / Area / Power Analysis
```

An RTL designer should therefore write RTL with synthesis behavior in mind.

The goal is not merely:

```text
"Make the code compile."
```

The goal is:

```text
"Describe the correct and efficient hardware."
```

---

- **Applications**

Logic synthesis is used in the development of:

- CPUs
- GPUs
- Microcontrollers
- SoCs
- AI accelerators
- DSP processors
- UART
- SPI
- I2C
- FIFOs
- DMA controllers
- Memory controllers
- Network processors
- FPGA designs
- ASIC designs

---

- **Advantages**

* Automates conversion of RTL into implementation-oriented hardware.
* Allows complex digital hardware to be designed at a higher abstraction level.
* Performs logic optimization automatically.
* Can optimize toward timing, area, and power goals.
* Supports technology mapping.
* Reduces the need for manual gate-level design.
* Enables systematic transition from RTL to implementation.

---

- **Limitations**

* Synthesis does not guarantee functional correctness.
* Poor RTL can result in inefficient hardware.
* Timing results depend on constraints and target technology.
* Area and power optimization involve trade-offs.
* Synthesis cannot solve every architectural problem automatically.
* Technology-specific implementation can reduce portability.
* The synthesized result still requires downstream implementation and analysis.

---

- **Real-World Example**

Consider a UART controller written in RTL.

```text
UART RTL
   ↓
Logic Synthesis
   ↓
 ┌─────────────────────┐
 │                     │
 ↓                     ↓
ASIC                  FPGA
 ↓                     ↓
Standard Cells        LUTs + FFs
 ↓                     ↓
Gate-Level Netlist    FPGA Resources
```

The RTL describes the UART behavior, while synthesis determines how that behavior is represented using the resources available in the target technology.

---

- **Key Points**

* Logic Synthesis converts synthesizable RTL into an implementation-oriented hardware representation.
* It is a major stage between RTL design and physical implementation.
* Synthesis includes elaboration, optimization, and technology mapping.
* ASIC synthesis maps logic to cells from a target technology library.
* FPGA synthesis maps logic toward FPGA-specific resources.
* Synthesis uses constraints to optimize timing and other design objectives.
* PPA means Power, Performance, and Area.
* RTL coding style directly influences synthesized hardware.
* Synthesis does not replace functional verification.
* Timing, area, and power results depend on the design, constraints, technology, and tool.
* Understanding synthesis is essential for an RTL Design Engineer.

---

- **Interview Questions**

**1. What is Logic Synthesis?**  
Logic Synthesis is the process of converting synthesizable RTL into a gate-level or target-specific hardware representation while attempting to satisfy design constraints.

**2. Why is synthesis required?**  
RTL describes the intended hardware at a higher abstraction level. Synthesis converts it into hardware structures that can be implemented in the target technology.

**3. What is the output of ASIC synthesis?**  
Typically, a technology-mapped gate-level netlist containing cells from the target technology library.

**4. What is technology mapping?**  
Technology mapping is the process of mapping optimized logic into resources available in the target technology.

**5. What is the difference between RTL and a netlist?**  
RTL is a higher-level HDL description of the design, while a netlist describes hardware cells and their connections.

**6. What is PPA?**  
PPA stands for **Power, Performance, and Area**.

**7. What is synthesis optimization?**  
It is the process of transforming the design into an equivalent implementation that better satisfies objectives such as timing, area, and power.

**8. Does synthesis verify functionality?**  
No. Synthesis converts RTL into hardware. Functional verification checks whether the design behaves correctly.

**9. What is a critical path?**  
A critical path is a timing path that limits the ability of the design to meet its required timing constraints.

**10. What is timing slack?**  
Slack is the difference between the required arrival time and the actual arrival time. Negative slack indicates a timing violation for the relevant check.

**11. Can the same RTL produce different hardware for ASIC and FPGA?**  
Yes. ASICs and FPGAs have different underlying resources and architectures, so the same RTL can map to different hardware structures.

**12. How does RTL coding style affect synthesis?**  
Different RTL constructs can infer different hardware. Incomplete combinational assignments, for example, can infer latches, while properly written clocked logic can infer flip-flops.

**13. Does synthesis automatically produce the final chip?**  
No. For ASICs, synthesis produces a netlist that goes through physical design, signoff, tapeout, fabrication, and testing. For FPGAs, the design continues through device-specific implementation and bitstream generation.

---

- **Quick Revision**

```text
LOGIC SYNTHESIS
       │
       ↓
      RTL
       ↓
  Elaboration
       ↓
 Optimization
       ↓
Technology Mapping
       ↓
Gate-Level / Target-Specific
Hardware Representation
       ↓
Timing / Area / Power Analysis
```

### **ASIC**

```text
RTL
 ↓
Synthesis
 ↓
Standard Cells
 ↓
Gate-Level Netlist
 ↓
Physical Design
 ↓
Tapeout
 ↓
Fabrication
```

### **FPGA**

```text
RTL
 ↓
Synthesis
 ↓
LUTs + FFs + BRAM + DSP
 ↓
Placement & Routing
 ↓
Timing Analysis
 ↓
Bitstream
```

### **Remember**

```text
RTL        → Describes hardware
Synthesis  → Converts RTL into hardware representation
Netlist    → Describes cells and connections
STA        → Checks timing
PPA        → Power + Performance + Area
```

---

- **Summary**

Logic Synthesis is the bridge between RTL design and hardware implementation. It takes synthesizable RTL, elaborates and optimizes the design, and maps it to resources available in the target technology. In ASICs, this typically results in a technology-mapped gate-level netlist using standard cells. In FPGAs, the design is mapped toward programmable resources such as LUTs, flip-flops, BRAM, and DSP blocks. Understanding synthesis is essential for an RTL Design Engineer because RTL coding decisions directly influence the hardware generated by the synthesis process.

---

- **References**

* Neso Academy — Digital Electronics, Verilog and VLSI
* All About Electronics — Digital Electronics and VLSI Fundamentals
* Digital Design and Computer Architecture — David Harris and Sarah Harris
* CMOS VLSI Design — Neil H. E. Weste and David Harris
* Digital Integrated Circuits — Jan M. Rabaey
