


# ◈ 2-Input AND Gate (`and_gate`)

### Fundamental Logic Gate • Combinational RTL • Dataflow Modeling

<p align="center">
  <img src="https://img.shields.io/badge/Language-Verilog_2001-00599C?style=flat-square&logo=cpu" alt="Language"/>
  <img src="https://img.shields.io/badge/Simulator-Icarus_Verilog-2EA44F?style=flat-square&logo=linux" alt="Simulator"/>
  <img src="https://img.shields.io/badge/Waveform-GTKWave-8B5CF6?style=flat-square" alt="GTKWave"/>
  <img src="https://img.shields.io/badge/Verification-4%2F4_Passed-brightgreen?style=flat-square" alt="Status"/>
</p>

</div>

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
