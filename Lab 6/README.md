# Lab 6: Design and Simulation of VHDL Code Converters

---

## Objective

This laboratory exercise focuses on implementing combinational code converters in VHDL. The objectives are:

- Create a **BCD to Excess-3 Converter** using VHDL.
- Implement a **Binary to Gray Code Converter**.
- Simulate both circuits and verify their outputs.

---

## Introduction

### BCD to Excess-3 Code

Excess-3 (XS-3) is a decimal coding scheme formed by adding the binary value **0011 (decimal 3)** to each valid BCD digit. It belongs to the class of **non-weighted codes** and is widely used because of its self-complementing characteristic, which simplifies certain arithmetic operations.

#### Conversion Table

| Decimal Digit | BCD Code | Excess-3 Code |
|--------------:|:--------:|:-------------:|
| 0 | 0000 | 0011 |
| 1 | 0001 | 0100 |
| 2 | 0010 | 0101 |
| 3 | 0011 | 0110 |
| 4 | 0100 | 0111 |
| 5 | 0101 | 1000 |
| 6 | 0110 | 1001 |
| 7 | 0111 | 1010 |
| 8 | 1000 | 1011 |
| 9 | 1001 | 1100 |

**Note:** Inputs from `1010` to `1111` do not represent valid BCD numbers and are not considered in this implementation.

---

### Binary to Gray Code

Gray code is a binary numbering system where only one bit changes between consecutive values. This minimizes transition errors and makes Gray code suitable for applications such as digital encoders and position sensors.

#### Gray Code Formula

```
Gray[3] = Binary[3]
Gray[2] = Binary[3] XOR Binary[2]
Gray[1] = Binary[2] XOR Binary[1]
Gray[0] = Binary[1] XOR Binary[0]
```

---

## Simulation Results

### BCD to Excess-3 Output

![BCD to Excess-3](bcd-ex3.png)

### Binary to Gray Output

![Binary to Gray](gray.png)

---

## Discussion

### BCD to Excess-3 Converter

- The converter produces the correct Excess-3 code for every valid BCD input.
- Output values begin at **0011** for decimal 0 and end at **1100** for decimal 9.
- Invalid BCD inputs are ignored in this implementation but could be handled by additional logic.

### Binary to Gray Converter

- Gray code is generated using XOR operations between adjacent binary bits.
- Successive Gray code values differ by only one bit, reducing the possibility of switching errors.
- Simulation confirms that the generated outputs match the expected Gray code sequence.

---

## Outcome

The experiment successfully demonstrates the implementation of two combinational logic circuits in VHDL.

- The **BCD to Excess-3 converter** correctly converts decimal digits represented in BCD to XS-3 code.
- The **Binary to Gray converter** accurately generates Gray code from binary inputs.
- Functional simulation verifies that both circuits operate according to their respective conversion rules.

---

## Summary

This experiment illustrates the practical implementation of code conversion techniques using VHDL. Both converters were designed, simulated, and verified successfully. The exercise highlights the importance of combinational logic in digital systems and provides hands-on experience in modeling and testing digital circuits using VHDL.