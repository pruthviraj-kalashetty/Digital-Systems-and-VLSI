# **RTL in ASIC and FPGA**

- **Overview**

RTL (Register Transfer Level) is a hardware description level used to describe the behavior and structure of digital circuits using registers, combinational logic, clocks, and data transfers. The same RTL concepts can be used for both ASIC and FPGA designs, but the implementation flow after RTL is different.

---

- **Definition**

**RTL in ASIC and FPGA** refers to designing digital hardware using HDL such as Verilog or SystemVerilog and then implementing that RTL either as a custom fabricated ASIC or on a programmable FPGA device.

```text
                 RTL Design
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
        ASIC                   FPGA
          │                     │
   Synthesis + STA       Synthesis + Implementation
          │                     │
   Physical Design        Bitstream Generation
          │                     │
      Tapeout             Program FPGA
          │                     │
     Fabrication          Hardware Testing
```

---

- **Why is RTL Needed?**

RTL provides a practical way to describe digital hardware before it is physically implemented.

Instead of designing every transistor manually, an RTL designer describes:

- Registers
- Combinational logic
- State machines
- Counters
- Data paths
- Control logic
- Interfaces
- Memories
- Arithmetic operations

The RTL is then converted into hardware structures by synthesis and implementation tools.

---

- **RTL Design Example**

A simple counter can be described using Verilog:

```verilog
module counter (
    input  clk,
    input  reset,
    output reg [3:0] count
);

always @(posedge clk)
begin
    if (reset)
        count <= 4'b0000;
    else
        count <= count + 1'b1;
end

endmodule
```

Conceptually:

```text
             ┌───────────────┐
      clk ──►│               │
             │   4-bit       │
reset ──────►│   Counter     │
             │               │
             └───────┬───────┘
                     │
                     ▼
                   count
```

The RTL describes the required hardware behavior. The target technology determines how that behavior is physically implemented.

---

- **RTL in ASIC**

In an ASIC flow, RTL is converted into a technology-specific gate-level implementation and eventually fabricated into a chip.

### **ASIC RTL Flow**

```text
System Specification
        ↓
Architecture
        ↓
RTL Design
        ↓
Functional Verification
        ↓
Logic Synthesis
        ↓
Gate-Level Netlist
        ↓
Static Timing Analysis
        ↓
Physical Design
        ↓
Physical Verification
        ↓
Tapeout
        ↓
Fabrication
        ↓
Packaging & Testing
```

### **ASIC RTL Implementation**

The synthesis tool maps RTL into cells from a target technology library.

```text
RTL
 │
 ↓
Synthesis
 │
 ↓
Technology Library
 │
 ↓
Gate-Level Netlist
 │
 ├── Flip-Flops
 ├── Logic Gates
 ├── Buffers
 └── Other Standard Cells
```

The design then goes through physical implementation and is ultimately manufactured.

---

- **RTL in FPGA**

In an FPGA flow, RTL is synthesized and mapped to the programmable resources available inside the FPGA.

### **FPGA RTL Flow**

```text
System Specification
        ↓
Architecture
        ↓
RTL Design
        ↓
Functional Simulation
        ↓
Synthesis
        ↓
Technology Mapping
        ↓
Placement
        ↓
Routing
        ↓
Timing Analysis
        ↓
Bitstream Generation
        ↓
FPGA Programming
        ↓
Hardware Testing
```

### **FPGA RTL Implementation**

RTL can be mapped to resources such as:

- LUTs
- Flip-flops
- Block RAM
- DSP blocks
- Carry logic
- Programmable interconnect
- I/O resources

```text
RTL
 │
 ↓
Synthesis
 │
 ↓
FPGA Mapping
 │
 ├── LUTs
 ├── Flip-Flops
 ├── BRAM
 ├── DSP
 └── Routing
 │
 ↓
Bitstream
 │
 ↓
FPGA
```

---

- **ASIC vs FPGA RTL Flow**

| Stage | ASIC | FPGA |
|---|---|---|
| RTL Design | Verilog/SystemVerilog | Verilog/SystemVerilog |
| Functional Simulation | Required | Required |
| Synthesis | Technology-specific synthesis | FPGA synthesis |
| Mapping | Standard cells/macros | LUTs, FFs, BRAM, DSP, etc. |
| Timing Analysis | STA | FPGA timing analysis |
| Physical Implementation | Placement & routing | Placement & routing |
| Final Output | Fabrication data/tapeout | Bitstream |
| Hardware | Fabricated chip | Programmable FPGA |
| Reconfiguration | Normally not possible | Possible |
| Design Update | Usually new chip revision | Reprogram FPGA |

---

- **Same RTL, Different Hardware**

The same basic RTL concept can target both ASIC and FPGA.

For example:

```text
                 Counter RTL
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
        ASIC                   FPGA
          ↓                     ↓
 Standard Cells          LUTs + Flip-Flops
          ↓                     ↓
 Fabricated Chip          Programmable FPGA
```

However, the resulting physical hardware is not necessarily identical.

The implementation tools optimize the RTL according to the target technology.

---

- **RTL Synthesis**

Synthesis converts synthesizable RTL into a hardware representation suitable for the target technology.

```text
Verilog RTL
     ↓
Synthesis
     ↓
Hardware Structure
```

For ASIC:

```text
RTL → Standard Cells → Gate-Level Netlist
```

For FPGA:

```text
RTL → LUTs/FFs/BRAM/DSP → FPGA Implementation
```

Simulation and synthesis are different processes.

**Simulation** checks behavior.

**Synthesis** converts synthesizable RTL into hardware structures.

---

- **Combinational RTL**

Combinational logic produces outputs based on current inputs.

Example:

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

This type of RTL can generally be implemented in both ASIC and FPGA technologies.

---

- **Sequential RTL**

Sequential RTL describes clocked storage elements.

Example:

```verilog
always @(posedge clk)
begin
    if (reset)
        q <= 1'b0;
    else
        q <= d;
end
```

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

In ASIC, this can be implemented using a standard-cell flip-flop.

In FPGA, it is normally implemented using a flip-flop associated with the FPGA's programmable logic resources.

---

- **RTL Coding Considerations**

Good RTL should be:

### **1. Synthesizable**

The RTL should describe hardware that the target technology can implement.

### **2. Functionally Correct**

The RTL must correctly implement the required specification.

### **3. Timing-Aware**

The designer should understand:

- Clock frequency
- Setup time
- Hold time
- Clock-to-Q delay
- Propagation delay
- Clock skew
- Timing slack

### **4. Resource-Aware**

The RTL should avoid unnecessary hardware.

For FPGA, resource usage may include:

- LUTs
- Flip-flops
- BRAM
- DSP blocks

For ASIC, important considerations include:

- Standard-cell area
- Memory area
- Power
- Timing
- Interconnect

### **5. Verification-Friendly**

The RTL should be structured so that it can be effectively verified through simulation and other verification techniques.

---

- **ASIC RTL Considerations**

When targeting ASICs, RTL design can strongly influence:

```text
              RTL
               │
       ┌───────┼───────┐
       ↓       ↓       ↓
     Area    Power   Timing
       │       │       │
       └───────┼───────┘
               ↓
              PPA
```

PPA means:

**Power, Performance, and Area**

Examples of RTL-level considerations include:

- Avoiding unnecessary logic
- Efficient FSM design
- Proper pipelining
- Clock-enable strategies
- Efficient arithmetic
- Avoiding unintended latches
- Understanding synthesis behavior

---

- **FPGA RTL Considerations**

FPGA RTL design must consider the architecture of the target FPGA.

Important resources include:

```text
FPGA
 │
 ├── LUTs
 ├── Flip-Flops
 ├── Block RAM
 ├── DSP Blocks
 ├── I/O Blocks
 └── Programmable Routing
```

RTL can influence:

- LUT utilization
- Flip-flop utilization
- BRAM usage
- DSP usage
- Routing complexity
- Maximum clock frequency
- Power consumption

---

- **RTL Portability**

Well-written RTL can often be reused across ASIC and FPGA projects.

For example:

```text
UART RTL
   │
   ├────────► FPGA Implementation
   │
   └────────► ASIC Implementation
```

However, complete portability is not always guaranteed.

Technology-specific constructs, FPGA primitives, vendor-specific IP, memories, clocking resources, and physical constraints can make RTL target-specific.

Therefore:

**Portable RTL → More reusable**

**Technology-specific RTL → More optimized for a particular target**

---

- **ASIC-Specific and FPGA-Specific RTL**

### **ASIC-Oriented RTL**

May be designed around:

- Standard-cell libraries
- ASIC memories
- Clock-tree considerations
- Low-power techniques
- Technology-specific constraints
- ASIC synthesis rules

### **FPGA-Oriented RTL**

May use:

- FPGA vendor primitives
- Block RAM
- DSP blocks
- PLL/MMCM or similar clocking resources
- FPGA-specific constraints
- Device-specific resources

For learning, it is useful to first develop clean, synthesizable RTL and then understand target-specific optimization.

---

- **RTL Verification**

Before implementation, RTL is normally simulated to check functionality.

```text
RTL
 │
 ├────────► Testbench
 │
 ↓
Simulation
 │
 ↓
Waveform
 │
 ↓
Expected vs Actual
```

For example:

```text
Clock:   _|‾|_|‾|_|‾|_|‾|_

Reset:   ‾‾‾\________/‾‾‾

Count:   0   0   1   2   3
```

Simulation allows functional errors to be found before hardware implementation.

---

- **RTL to Hardware Relationship**

A very important concept for an RTL Design Engineer is:

```text
Specification
      ↓
Architecture
      ↓
RTL
      ↓
Simulation
      ↓
Synthesis
      ↓
Hardware Structure
      ↓
Implementation
      ↓
Physical Hardware
```

RTL is therefore not software code running on a processor.

RTL describes **hardware that can be created from the RTL description**.

---

- **Applications**

RTL design is used for:

- CPU datapaths
- Control units
- FSMs
- UART
- SPI
- I2C
- FIFOs
- DMA controllers
- Memory controllers
- Timers
- Interrupt controllers
- Network interfaces
- DSP blocks
- AI accelerators
- SoC peripherals
- FPGA-based systems
- ASIC-based systems

---

- **Advantages of RTL-Based Design**

* Hardware can be described at a high abstraction level.
* RTL is easier to modify than transistor-level design.
* The same design concepts can target ASIC and FPGA.
* Simulation can be performed before hardware implementation.
* Synthesis tools automate conversion into hardware structures.
* Complex digital systems can be developed systematically.
* RTL modules can be reused across projects.

---

- **Limitations of RTL-Based Design**

* RTL does not directly describe the final physical layout.
* Actual timing depends on implementation and technology.
* Resource usage depends on the target architecture.
* Some RTL constructs are not synthesizable.
* Poor RTL can produce inefficient hardware.
* Technology-specific optimization may reduce portability.

---

- **Real-World Example**

Consider a UART controller.

```text
UART Specification
        ↓
UART Architecture
        ↓
UART RTL
        ↓
Functional Verification
        ↓
       ┌───────────────┐
       ↓               ↓
     ASIC             FPGA
       ↓               ↓
Standard Cells      LUTs + FFs
       ↓               ↓
Fabricated IC       Bitstream
```

The UART functionality can remain conceptually the same, while the implementation technology is different.

---

- **Key Points**

* RTL describes digital hardware at the Register Transfer Level.
* Verilog and SystemVerilog are commonly used to describe RTL.
* RTL can target both ASIC and FPGA implementations.
* ASIC synthesis maps RTL toward standard-cell and technology-specific hardware.
* FPGA synthesis maps RTL toward programmable FPGA resources.
* ASIC designs eventually go through tapeout and fabrication.
* FPGA designs eventually generate a bitstream used to configure the device.
* Functional simulation is important for both ASIC and FPGA.
* Timing and resource usage depend on the target technology.
* Good RTL should be synthesizable, correct, timing-aware, and verification-friendly.
* Portable RTL can be reused, while technology-specific RTL can provide target-specific optimization.

---

- **Interview Questions**

**1. What is RTL?**  
RTL stands for **Register Transfer Level**. It describes how data moves between registers and how combinational logic processes that data.

**2. Can the same RTL be used for ASIC and FPGA?**  
Yes. Many synthesizable RTL designs can target both, although the downstream implementation and technology-specific optimizations are different.

**3. What happens to RTL in an ASIC flow?**  
RTL is verified, synthesized into a technology-specific gate-level netlist, followed by timing analysis, physical implementation, verification, tapeout, and fabrication.

**4. What happens to RTL in an FPGA flow?**  
RTL is verified, synthesized, mapped to FPGA resources, placed and routed, timing-analyzed, and converted into a bitstream.

**5. What is the major difference between ASIC and FPGA implementation of RTL?**  
ASIC RTL is ultimately implemented as fabricated hardware, while FPGA RTL is mapped to programmable hardware resources.

**6. Is RTL software?**  
No. RTL is a hardware description. Although it is written using HDL syntax, synthesis interprets it as hardware structures.

**7. What is synthesis?**  
Synthesis converts synthesizable RTL into a hardware representation suitable for the target technology.

**8. What is a bitstream?**  
A bitstream is configuration data used to program an FPGA's programmable resources.

**9. Why is RTL verification important?**  
It helps identify functional problems before the design is implemented in hardware.

**10. What does PPA mean in ASIC design?**  
PPA means **Power, Performance, and Area**.

**11. Why can RTL resource usage differ between ASIC and FPGA?**  
Because ASICs and FPGAs use different underlying hardware architectures. The same RTL can therefore map to different physical resources.

---

- **Quick Revision**

```text
RTL
 │
 ├── Registers
 ├── Combinational Logic
 ├── FSMs
 ├── Datapaths
 └── Control Logic
 │
 ├──────────────────────┐
 ↓                      ↓
ASIC                   FPGA
 ↓                      ↓
Synthesis              Synthesis
 ↓                      ↓
Standard Cells         LUTs + FFs
 ↓                      ↓
Physical Design        Place & Route
 ↓                      ↓
Tapeout                Bitstream
 ↓                      ↓
Fabrication            FPGA Hardware
```

---

- **Summary**

RTL is the central design description used to develop digital hardware before physical implementation. The same fundamental RTL concepts can be used for both ASIC and FPGA designs. In an ASIC flow, RTL eventually becomes a fabricated chip through synthesis, physical design, verification, tapeout, and manufacturing. In an FPGA flow, RTL is synthesized, mapped to programmable resources, placed and routed, and converted into a bitstream. Understanding both flows is important for an RTL Design Engineer because it connects HDL coding with the actual hardware that the RTL produces.

---

- **References**

* Neso Academy — Digital Electronics, Verilog and VLSI
* All About Electronics — Digital Electronics and VLSI Fundamentals
* Digital Design and Computer Architecture — David Harris and Sarah Harris
* CMOS VLSI Design — Neil H. E. Weste and David Harris
* FPGA Prototyping by Verilog Examples — Pong P. Chu
