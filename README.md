# BCD Adder using Verilog

## Overview

This project implements a **BCD Adder** using Verilog HDL.

A BCD adder adds two decimal digits represented in BCD format. Since normal binary addition can produce invalid BCD values (1010 to 1111), a correction value of `0110` is added whenever the result exceeds decimal 9.

## BCD Addition Algorithm

1. Add two BCD numbers using binary addition.
2. Check if the result is greater than 9.
3. Add 6 (`0110`) correction.
4. Generate carry output.

## Inputs

- `A[3:0]` - First BCD digit
- `B[3:0]` - Second BCD digit
- `Cin` - Carry input

## Outputs

- `Sum[3:0]` - BCD sum digit
- `Cout` - Carry output

## Truth Examples

| A | B | Result |
|-|-|-|
|0101 + 0011|1000|
|1000 + 0111|0001 with carry|
|1001 + 1001|1000 with carry|

## Project Structure

```
bcd-adder-verilog/
├── src/
├── tb/
├── sim/
├── images/
└── README.md
```

## Simulation

Compile:

```bash
iverilog -o bcd src/bcd_adder.v tb/bcd_adder_tb.v
```

Run:

```bash
vvp bcd
```

Open waveform:

```bash
gtkwave bcd_adder.vcd
```

## Applications

- Digital calculators
- Digital clocks
- Decimal arithmetic processors
- Embedded systems
- FPGA designs

## License

MIT License