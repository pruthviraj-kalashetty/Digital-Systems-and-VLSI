


# ◈ 2-Input AND Gate (`and_gate`)

### Fundamental Logic Gate • Combinational RTL • Dataflow Modeling

---

## 📌 Module Description

The **2-Input AND Gate** is a basic combinational circuit where the output `Y` goes **HIGH (`1`)** if and only if both inputs `A` and `B` are **HIGH (`1`)**. Implemented using continuous assignment (`assign`) in dataflow abstraction.

---

## 💻 Verilog RTL Code

```verilog
module and_gate (
    input  wire A,
    input  wire B,
    output wire Y
);

    // Continuous assignment using bitwise AND operator
    assign Y = A & B;

endmodule
