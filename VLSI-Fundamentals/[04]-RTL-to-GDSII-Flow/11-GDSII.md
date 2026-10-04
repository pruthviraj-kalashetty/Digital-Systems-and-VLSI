# **GDSII**

* **Overview:**

GDSII is a file format used to represent the **physical layout of an integrated circuit**. It contains geometric information such as shapes, layers, cells, and physical structures required to describe the layout of an IC.

GDSII is commonly associated with the final physical design database that is prepared for **physical verification, signoff, and tapeout**.

The simplified flow is:

```text
RTL
  |
  v
Synthesis
  |
  v
Floor Planning
  |
  v
Placement
  |
  v
CTS
  |
  v
Routing
  |
  v
Physical Verification
  |
  v
Signoff
  |
  v
GDSII
  |
  v
Tapeout
```

---

* **Definition:**

GDSII, commonly referred to as **GDS** or **GDSII stream format**, is a binary file format used to store the physical layout representation of an integrated circuit.

It represents physical geometry using information such as:

- Layout layers
- Polygons
- Rectangles
- Paths
- Cell structures
- Cell hierarchy
- Coordinates
- Text/labels
- Geometrical relationships

GDSII describes the **physical layout**, not the RTL behavior of the design.

---

* **Why is GDSII needed?**

An ASIC ultimately needs to be manufactured according to a physical layout.

RTL describes functionality:

```text
RTL
 |
 v
What the circuit does
```

GDSII represents physical geometry:

```text
GDSII
 |
 v
Where physical structures are located
and how they are represented in layout
```

GDSII is needed to:

- Represent the final physical layout
- Transfer layout information between tools
- Support physical verification
- Support foundry tapeout
- Preserve layout geometry and hierarchy
- Represent metal, vias, cells, and other physical structures
- Provide a standard layout-data exchange format

---

* **GDSII in the ASIC Flow:**

A simplified ASIC implementation flow is:

```text
Specification
      |
      v
Architecture
      |
      v
RTL Design
      |
      v
Functional Verification
      |
      v
Logic Synthesis
      |
      v
Gate-Level Netlist
      |
      v
Floor Planning
      |
      v
Placement
      |
      v
Clock Tree Synthesis
      |
      v
Routing
      |
      v
Parasitic Extraction
      |
      v
STA / Power Analysis
      |
      v
Physical Verification
      |
      v
Signoff
      |
      v
GDSII
      |
      v
Tapeout
```

The exact ordering and database handling can vary between implementation flows.

---

* **Working Principle:**

During physical implementation, the design is gradually converted from logical information into physical information.

```text
Logical Design
      |
      v
Gate-Level Netlist
      |
      v
Physical Placement
      |
      v
Physical Routing
      |
      v
Physical Layout
      |
      v
GDSII
```

The physical implementation tools create and maintain a physical database containing information about:

- Cells
- Instances
- Coordinates
- Layers
- Wires
- Vias
- Shapes
- Hierarchy
- Physical boundaries

The final physical representation can then be written into GDSII format for downstream use.

---

* **Physical Layout Representation:**

A simplified IC layout can be represented as:

```text
+---------------------------------------+
|                                       |
|   +---------+       +---------+       |
|   |  Cell A |=======|  Cell B |       |
|   +---------+       +---------+       |
|        |                  |            |
|        |      Metal       |            |
|        +==================+            |
|                                       |
|              +---------+              |
|              |  Cell C |              |
|              +---------+              |
|                                       |
+---------------------------------------+
```

GDSII stores the geometric representation required to describe such physical structures.

---

* **GDSII Layers:**

An IC layout contains multiple physical layers.

Examples can include:

```text
Metal 1
Metal 2
Metal 3
Metal 4
...
Via layers
Poly
Diffusion
Well
Contact
Other technology-specific layers
```

GDSII stores geometry associated with these layers.

A simplified representation:

```text
GDSII
 |
 +---- Layer 1 → Geometry
 |
 +---- Layer 2 → Geometry
 |
 +---- Layer 3 → Geometry
 |
 +---- Via Layer → Geometry
 |
 +---- Other Layers → Geometry
```

The actual layer definitions and meanings are technology-specific.

---

* **GDSII Geometry:**

GDSII can represent physical geometry using different geometric objects.

Common examples include:

- Boundaries/polygons
- Paths
- Boxes/rectangles
- Text
- References
- Cell structures

Simplified example:

```text
Rectangle:

+----------------+
|                |
|                |
|                |
+----------------+

Polygon:

      +------+
     /       |
    /        |
   +---------+
```

These shapes are associated with specific layout layers.

---

* **GDSII Coordinates:**

Physical layout objects require coordinate information.

For example:

```text
              Y
              ^
              |
       (10,20)|------+
              |      |
              | Cell |
              |      |
              +------+
                    |
                    +------------> X
```

The coordinates define the physical position of layout geometry.

The coordinate units and precision are determined by the GDSII data representation and technology/design setup.

---

* **Cells and Hierarchy:**

Large IC designs contain many repeated structures.

Instead of storing every repeated structure independently, layout data can use hierarchical cells.

Example:

```text
Top Chip
   |
   +---- CPU
   |      |
   |      +---- ALU
   |      +---- Register File
   |
   +---- Memory Controller
   |
   +---- Peripheral
          |
          +---- UART
          +---- SPI
```

GDSII can represent hierarchical relationships between cells.

This allows repeated structures to be represented efficiently.

---

* **Hierarchy in GDSII:**

A simplified hierarchy can look like:

```text
TOP
 |
 +---- BLOCK_A
 |       |
 |       +---- CELL_1
 |       +---- CELL_2
 |
 +---- BLOCK_B
         |
         +---- CELL_3
         +---- CELL_4
```

Hierarchy is useful for:

- Large designs
- Repeated blocks
- IP integration
- Design organization
- Efficient data representation

---

* **GDSII and Standard Cells:**

Standard-cell based ASICs contain many instances of predefined cells.

Examples:

```text
INV
BUF
NAND
NOR
AND
OR
XOR
MUX
DFF
```

The physical layouts of these cells are provided by the technology/library flow.

The final design contains instances of these cells positioned and connected according to the implementation.

Simplified:

```text
             TOP DESIGN
                  |
       +----------+----------+
       |          |          |
      INV        NAND       DFF
       |          |          |
       +----------+----------+
                  |
              Physical
               Layout
```

---

* **GDSII and Routing:**

Routing creates physical metal and via structures.

These structures become part of the physical layout represented in GDSII.

```text
Placed Cells
     |
     v
Routing
     |
     +---- Metal
     |
     +---- Vias
     |
     +---- Interconnect Geometry
     |
     v
Physical Layout
     |
     v
GDSII
```

Therefore, GDSII contains the physical representation of the routed design.

---

* **GDSII and Vias:**

Vias connect different metal layers.

For example:

```text
Metal 3
====================

        |
       VIA

        |

Metal 2
====================
```

The physical representation of these structures is included in the layout data.

---

* **GDSII and Physical Verification:**

GDSII can be used as an input to physical verification tools.

A simplified relationship is:

```text
Physical Layout
      |
      v
GDSII
      |
      v
Physical Verification
      |
      +----> DRC
      |
      +----> LVS
      |
      +----> Other Checks
```

Physical verification checks whether the physical representation satisfies the required rules and connectivity requirements.

Depending on the implementation flow, physical verification may operate directly on the implementation database and/or exported layout formats such as GDSII.

---

* **GDSII and DRC:**

DRC checks the physical geometry represented in the layout.

For example:

```text
GDSII Layout
     |
     v
Metal Geometry
     |
     v
Spacing / Width / Via Rules
     |
     v
DRC
```

A DRC violation must be fixed in the physical implementation and the verification process repeated.

---

* **GDSII and LVS:**

LVS compares the circuit connectivity represented by the physical layout with the intended circuit representation.

Simplified:

```text
Gate-Level Netlist
       |
       |
       v
      LVS
       ^
       |
       |
GDSII / Extracted Layout
```

The physical layout is extracted into a connectivity representation, which is then compared with the intended netlist.

---

* **GDSII and Signoff:**

GDSII is associated with the final physical design database used around the signoff/tapeout stage.

A simplified signoff flow is:

```text
Final Routed Design
        |
        v
Physical Verification
        |
        v
Timing / Power Signoff
        |
        v
Final Layout Database
        |
        v
GDSII
        |
        v
Tapeout
```

The exact signoff flow and database formats vary by organization, technology, and foundry.

---

* **GDSII and Tapeout:**

Tapeout is the process of releasing the final design data to the semiconductor foundry for manufacturing.

GDSII has historically been one of the important layout formats used for this purpose.

Simplified:

```text
Final Design
     |
     v
Signoff
     |
     v
Layout Data
     |
     v
GDSII
     |
     v
Tapeout
     |
     v
Foundry
     |
     v
Fabrication
```

Important distinction:

```text
GDSII ≠ Tapeout

GDSII = Physical layout data format

Tapeout = Release of final design data for manufacturing
```

---

* **GDSII vs RTL:**

| RTL | GDSII |
|---|---|
| Describes hardware behavior/structure | Describes physical layout geometry |
| Written in HDL | Stored as layout data |
| Used in front-end design | Used mainly in physical implementation/tapeout |
| Contains registers, logic, control, datapath | Contains layers, shapes, coordinates, cells, geometry |
| Used for simulation and synthesis | Used for physical verification and manufacturing data flow |
| Technology-independent at a high level | Strongly associated with physical technology/layout |

---

* **GDSII vs Gate-Level Netlist:**

| Gate-Level Netlist | GDSII |
|---|---|
| Describes logical connectivity | Describes physical layout |
| Contains cells and nets | Contains physical geometry and hierarchy |
| Used by physical implementation tools | Used for layout exchange/verification/tapeout workflows |
| Does not define exact physical locations | Contains physical locations and geometry |
| Focuses on logical structure | Focuses on physical implementation |

---

* **GDSII vs Physical Design Database:**

A physical design tool generally maintains a richer internal implementation database than simply a GDSII file.

```text
Physical Design Database
        |
        +---- Placement
        +---- Routing
        +---- Constraints
        +---- Physical Properties
        +---- Analysis Data
        +---- Other Implementation Information
        |
        v
      GDSII
```

GDSII is primarily a **layout geometry exchange format**, not a complete replacement for every piece of implementation information stored by modern physical design tools.

This distinction is important.

---

* **GDSII and Modern Layout Formats:**

GDSII remains widely recognized and used, but modern semiconductor flows can also use other layout/database formats.

One important example is:

**OASIS (Open Artwork System Interchange Standard)**.

OASIS was developed to provide a more compact and efficient representation for very large layout data.

A simplified comparison:

| GDSII | OASIS |
|---|---|
| Long-established layout format | Newer layout format |
| Widely supported | Widely used in modern advanced flows |
| Can produce large files for very large designs | Designed for more efficient data representation |
| Commonly used for layout exchange | Increasingly important in advanced technologies |

The exact format used for tapeout depends on the foundry and design flow.

---

* **GDSII File Characteristics:**

GDSII is a binary format.

It can contain information related to:

- Library structures
- Cell structures
- Cell references
- Layer numbers
- Data types
- Geometrical boundaries
- Paths
- Text
- Coordinates
- Transformations
- Hierarchical relationships

It is not intended to be manually edited like a normal text file.

---

* **GDSII File Hierarchy:**

A simplified conceptual structure is:

```text
GDSII Library
      |
      +---- Cell A
      |       |
      |       +---- Geometry
      |       +---- References
      |
      +---- Cell B
      |       |
      |       +---- Geometry
      |
      +---- TOP
              |
              +---- Cell A
              +---- Cell B
```

The exact internal record structure is defined by the GDSII specification.

---

* **GDSII Generation:**

A simplified generation flow is:

```text
Gate-Level Netlist
       |
       v
Floor Planning
       |
       v
Placement
       |
       v
CTS
       |
       v
Routing
       |
       v
Physical Optimization
       |
       v
Final Physical Database
       |
       v
GDSII Export
```

The GDSII is generated from the physical implementation rather than directly from RTL.

---

* **GDSII and Physical Design Iterations:**

GDSII is normally not generated once and immediately considered final.

A design may go through several iterations:

```text
Physical Implementation
        |
        v
GDSII / Layout Data
        |
        v
Verification
        |
        v
Violation
        |
        v
Physical Fix
        |
        v
Re-generate Layout Data
        |
        v
Verification Again
```

This continues until the required signoff criteria are satisfied.

---

* **GDSII and Manufacturing:**

GDSII represents layout geometry, but it is not itself the complete manufacturing process.

The foundry uses the final design data along with technology-specific manufacturing processes to create the physical semiconductor.

Simplified:

```text
GDSII / Final Layout Data
          |
          v
Foundry Processing
          |
          v
Mask / Manufacturing Data Preparation
          |
          v
Wafer Fabrication
          |
          v
Die
```

Additional manufacturing data preparation steps may occur between final layout data and wafer fabrication.

---

* **RTL Relevance:**

GDSII is far downstream from RTL, but an RTL Design Engineer should understand its role in the complete ASIC flow.

```text
RTL
 |
 v
Synthesis
 |
 v
Gate-Level Netlist
 |
 v
Physical Design
 |
 v
Placement + CTS + Routing
 |
 v
Physical Layout
 |
 v
Physical Verification
 |
 v
GDSII
 |
 v
Tapeout
```

This helps an RTL engineer understand the complete path from **hardware description to manufacturable physical layout**.

RTL decisions can indirectly influence:

- Cell count
- Logic complexity
- Routing demand
- Timing
- Power
- Area
- Physical implementation difficulty

Therefore:

```text
Good RTL
   |
   v
Better Implementation Potential
   |
   v
Better PPA / Physical Closure
   |
   v
Cleaner Final Layout
```

---

* **Common Mistakes:**

1. Thinking GDSII contains RTL code.
2. Thinking GDSII is the same as a gate-level netlist.
3. Thinking GDSII is the same as tapeout.
4. Assuming GDSII alone contains every piece of implementation information.
5. Assuming DRC-clean automatically means the design is functionally correct.
6. Assuming LVS-clean automatically means timing is correct.
7. Ignoring technology-specific layer definitions.
8. Treating GDSII as a normal editable text file.
9. Assuming every foundry uses exactly the same final data format.
10. Ignoring the difference between layout data and manufacturing data preparation.

---

* **Best Practices:**

- Generate final layout data only from a properly signed-off physical implementation.
- Run required physical verification before final release.
- Verify DRC and LVS results.
- Check timing and power signoff requirements.
- Ensure correct technology and layer information.
- Maintain proper hierarchy and cell references.
- Use the required foundry-approved data format.
- Preserve version control and release information for final design data.
- Follow the foundry's tapeout requirements.
- Do not treat GDSII as a replacement for the complete implementation database.

---

* **Applications:**

GDSII and related layout-data formats are used in:

- ASIC design
- SoC design
- CPU design
- GPU design
- Microcontroller design
- DSP processors
- AI accelerators
- Memory designs
- Standard-cell based ICs
- Custom ICs
- Mixed-signal ICs
- Physical design
- Physical verification
- Layout data exchange
- Tapeout preparation

---

* **Advantages:**

- Widely recognized layout representation.
- Represents physical IC geometry.
- Supports hierarchical layout representation.
- Can represent multiple physical layers.
- Supports layout data exchange between tools.
- Useful for physical verification workflows.
- Can represent complex large-scale IC layouts.
- Has long-standing support across semiconductor design ecosystems.

---

* **Limitations:**

- GDSII is primarily a layout geometry format, not a complete implementation database.
- Large advanced designs can produce very large files.
- It does not describe RTL functionality.
- It does not by itself contain complete timing or power analysis information.
- It does not replace physical verification.
- It does not represent the entire semiconductor manufacturing process.
- Modern advanced flows may use more efficient formats such as OASIS.

---

* **Real-World Example:**

Consider a simple processor subsystem:

```text
+--------------------------------------+
|          Processor Subsystem         |
|                                      |
|  +-------+    +-------+              |
|  |  CPU  |----| Cache |              |
|  +-------+    +-------+              |
|      |             |                 |
|      +------+------+                 |
|             |                        |
|       Memory Controller              |
|             |                        |
+--------------------------------------+
```

After RTL design and functional verification:

```text
RTL
 |
 v
Synthesis
 |
 v
Gate-Level Netlist
 |
 v
Floor Planning
 |
 v
Placement
 |
 v
CTS
 |
 v
Routing
 |
 v
Physical Verification
 |
 v
Signoff
 |
 v
GDSII
```

The resulting GDSII contains the physical layout representation of the processor subsystem, including the geometry associated with the implemented cells, routing, layers, and hierarchical structures.

The final approved design data can then be released according to the foundry's tapeout requirements.

---

* **Key Points:**

- GDSII is a physical IC layout data format.
- It represents physical geometry rather than RTL behavior.
- It can contain layers, shapes, coordinates, cells, references, and hierarchy.
- Routing contributes metal and via geometry to the final layout.
- GDSII is generated from the physical implementation database.
- Physical verification can operate on exported layout data such as GDSII.
- DRC checks physical manufacturing rules.
- LVS checks physical connectivity against the intended circuit.
- GDSII is closely associated with the final layout/tapeout stage.
- GDSII is not the same as the gate-level netlist.
- GDSII is not the same as tapeout.
- GDSII is not a complete replacement for the internal physical design database.
- OASIS is another important layout data format used in modern semiconductor flows.
- The exact final data format and tapeout requirements depend on the foundry and technology.
- GDSII is far downstream from RTL but is part of the complete ASIC implementation journey.

---

* **Interview Questions:**

### 1. What is GDSII?

GDSII is a binary file format used to represent the physical layout geometry of an integrated circuit.

### 2. What does GDSII contain?

It can contain physical layout information such as layers, polygons, paths, coordinates, cells, references, text, and hierarchical structures.

### 3. Does GDSII contain RTL?

No. GDSII represents physical layout information, not RTL code.

### 4. Does GDSII contain the gate-level netlist?

GDSII primarily represents physical layout geometry. It should not be considered a direct replacement for the gate-level netlist.

### 5. Where does GDSII appear in the ASIC flow?

It is associated with the final physical implementation and layout-data release around signoff and tapeout.

### 6. What is the relationship between routing and GDSII?

Routing creates physical metal and via structures, and these physical geometries are represented in the final layout data such as GDSII.

### 7. What is the relationship between GDSII and DRC?

DRC analyzes physical layout geometry against technology-specific manufacturing rules. GDSII can be one of the layout-data inputs used for such analysis.

### 8. What is the relationship between GDSII and LVS?

LVS extracts connectivity from physical layout data and compares it with the intended circuit representation.

### 9. Is GDSII the same as tapeout?

No.

```text
GDSII → Physical Layout Data Format

Tapeout → Release of final design data for manufacturing
```

### 10. What is the difference between GDSII and OASIS?

Both are layout-data formats. GDSII is a long-established format, while OASIS provides a more compact and efficient representation that is particularly useful for very large modern designs.

### 11. Is GDSII the complete physical design database?

No. Modern physical design tools maintain richer implementation databases containing information beyond the layout geometry represented in GDSII.

### 12. Why is hierarchy important in GDSII?

Hierarchy allows large designs and repeated blocks to be represented efficiently through cells and references.

### 13. Can GDSII be directly generated from RTL?

Normally, no. RTL must first go through synthesis and physical implementation before the physical layout data can be generated.

### 14. What is stored in a GDSII layer?

A layer contains physical geometry associated with a particular layout layer definition. The exact meaning of the layer depends on the technology.

### 15. What happens after GDSII generation?

The final layout data is checked according to the required signoff methodology and then released according to the foundry's tapeout requirements.

### 16. Does GDSII guarantee that a chip will work?

No. GDSII is a layout representation. Functional verification, timing analysis, physical verification, power analysis, and other signoff checks are also required.

### 17. Why should an RTL Design Engineer understand GDSII?

Understanding GDSII helps an RTL engineer understand the complete ASIC flow from RTL through synthesis and physical implementation to final manufacturable layout data.

---

* **Quick Revision:**

```text
RTL
 ↓
Synthesis
 ↓
Gate-Level Netlist
 ↓
Floor Planning
 ↓
Placement
 ↓
CTS
 ↓
Routing
 ↓
Physical Layout
 ↓
Physical Verification
 ↓
Signoff
 ↓
GDSII
 ↓
Tapeout
 ↓
Foundry
```

### Remember:

```text
RTL
→ Describes hardware behavior/structure

Netlist
→ Describes logical connectivity

Physical Layout
→ Describes physical implementation

GDSII
→ Represents physical layout geometry

Tapeout
→ Releases final design data for manufacturing
```

---

* **Summary:**

GDSII is a widely recognized physical layout data format used to represent the geometry and hierarchy of an integrated circuit. It is generated from the physical implementation of the design after stages such as floor planning, placement, clock-tree synthesis, and routing.

GDSII can contain information about physical layers, shapes, coordinates, cells, references, and hierarchy. It can be used in physical verification workflows and is closely associated with the final layout and tapeout process.

The most important distinction is:

```text
RTL      → What the hardware does

Netlist  → How the logical gates are connected

Layout   → Where physical structures are placed and connected

GDSII    → Layout geometry representation

Tapeout  → Release of final design data for manufacturing
```

For an RTL Design Engineer, GDSII represents the far end of the ASIC implementation journey and helps connect **RTL design decisions to the final physical chip layout**.

---

* **References:**

1. Neso Academy — VLSI / Physical Design concepts  
2. All About Electronics — Digital Electronics and VLSI concepts  
3. Neil H. E. Weste and David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*  
4. Jan M. Rabaey, Anantha Chandrakasan, and Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*  
5. GDSII Stream Format — layout data format concepts  
6. OASIS — Open Artwork System Interchange Standard concepts
