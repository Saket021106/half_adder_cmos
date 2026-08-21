# Half Adder Implementation Using CMOS

This repository contains design files, schematics, and simulation reports for a **Half Adder** circuit implemented using Complementary Metal-Oxide-Semiconductor (CMOS) technology.

## Table of Contents
- [Overview](#overview)
- [Circuit Description & Logic](#circuit-description--logic)
- [CMOS Implementation Details](#cmos-implementation-details)
- [Repository Structure](#repository-structure)
- [Simulation & Verification](#simulation--verification)
- [License](#license)

---

## Overview

A half adder is a fundamental combinational digital circuit that performs the addition of two single-bit binary numbers ($A$ and $B$). It produces two outputs:
1. **Sum ($S$)**: Represents the least significant bit of the addition.
2. **Carry ($C$ or $C_{out}$)**: Represents the overflow bit carried over to the next column.

### Truth Table

| Input A | Input B | Sum (S) | Carry (C) |
| :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

Boolean Expressions:
- $\text{Sum} = A \oplus B = \bar{A}B + A\bar{B}$
- $\text{Carry} = A \cdot B$

---

## Circuit Description & Logic

### 1. Carry Generation
The carry output requires a logical AND operation between inputs $A$ and $B$:
- $\text{Carry} = A \cdot B$
- In CMOS, this is typically implemented using a NAND gate followed by an inverter, or via a pass-transistor logic network.

### 2. Sum Generation
The sum output requires an exclusive-OR (XOR) operation:
- $\text{Sum} = A \oplus B$
- Constructing an XOR gate efficiently in CMOS requires careful transistor sizing and layout configuration to minimize propagation delay and maintain clean rail-to-rail voltage swings.

---

## CMOS Implementation Details

- **Pull-Up Network (PUN):** Consists of PMOS transistors connected to $V_{DD}$, responsible for driving the output high when the logic conditions are met.
- **Pull-Down Network (PDN):** Consists of NMOS transistors connected to Ground ($GND$), responsible for pulling the output low.
- **Transistor Sizing:** PMOS transistors are typically sized wider than NMOS transistors to compensate for lower hole mobility compared to electron mobility, ensuring balanced rise and fall times.

---

## Repository Structure

- `README.md`: Documentation and project overview.
- `half_adder.pdf`: Comprehensive schematic, circuit diagrams, and theoretical derivations.
- `half_adder_sim.pdf`: Pre-layout/post-layout simulation waveforms, transient response analysis, and performance metrics.

---

## Simulation & Verification

The circuit design is verified through SPICE-based transient simulations. Key parameters analyzed include:
- **Propagation Delay ($t_{p}$):** Measured from input transition points to $50\%$ output voltage levels.
- **Dynamic Power Dissipation:** Evaluated across different switching frequencies.
- **Static Power Dissipation:** Verified to ensure minimal leakage current during steady states.

Refer to `half_adder_sim.pdf` for detailed waveform plots and transient response curves.

---

## License

This project is open-source and available for educational and research purposes.
