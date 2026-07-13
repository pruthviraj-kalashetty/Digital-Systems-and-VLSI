# Number System Conversion

[![Digital Design](https://img.shields.io/badge/Stage-A--Digital--Design-blue.svg)](#)
[![Topics](https://img.shields.io/badge/Topics-Number--Systems-orange.svg)](#)

A number system is a structured method for representing, naming, and ordering numerical values using specific symbols and rules, fundamentally based on a base or radix. This module covers the theoretical foundations and procedural steps for switching between various base representations used in digital systems.

---

## 📂 Module Contents

This directory contains detailed breakdowns of the core number systems used in digital logic and computing:

*   **[Number System Conversion](./1)-Number-System-Conversion.md)** — Comprehensive guide on converting values between different bases (Decimal, Binary, Octal, Hexadecimal).
*   **[Binary System](./Binary-System.md)** — Core base-2 concepts, bits, bytes, and their foundational role in digital circuits.
*   **[Hexadecimal System](./Hexadecimal-System.md)** — Base-16 representation, compact formatting for binary data, and addressing structures.
*   **[Octal System](./Octal-System.md)** — Base-8 representation and its historical/practical applications in computing.

---

## 🎯 Core Topics Covered

### 1. Representation & Radix
Understanding the weight and positional value of digits based on the system's radix ($r$):
*   **Binary ($r = 2$):** $\{0, 1\}$
*   **Octal ($r = 8$):** $\{0, 1, 2, 3, 4, 5, 6, 7\}$
*   **Hexadecimal ($r = 16$):** $\{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F\}$

### 2. Conversion Algorithms
*   **Any Base to Decimal:** Polynomial expansion using positional weights.
*   **Decimal to Any Base:** Successive division (for integers) and successive multiplication (for fractions).
*   **Binary $\leftrightarrow$ Octal / Hexadecimal:** Grouping bits ($3$-bit groups for Octal, $4$-bit groups for Hexadecimal) for fast inspection-based conversion.

---

## 🗺️ Part of the VLSI Learning Journey

This module is part of **`[1]-STAGE-(A)-DIGITAL-DESIGN`**. To explore adjacent concepts, navigate through the roadmap:

*   ⏮️ Previous: **`[01]-Digital-Basics`**
*   ⏭️ Next: **`[03]-Binary-Arithmetic`**
