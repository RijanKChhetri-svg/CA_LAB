# Lab 3: Implementation and Verification of Encoder and Decoder Circuits Using VHDL

## 1. Objective

* To design a 4-to-2 Priority Encoder using VHDL.
* To design a 2-to-4 Decoder using VHDL.
* To simulate both circuits and verify their outputs using waveform analysis.
* To understand the role of encoding and decoding circuits in digital systems.

---

## 2. Theory

### 4-to-2 Priority Encoder

An encoder is a combinational logic circuit that converts several input signals into a smaller binary code at the output. A 4-to-2 encoder accepts four input lines and generates a 2-bit binary output corresponding to the active input.

A priority encoder is a special type of encoder that assigns priority levels to its inputs. If multiple inputs become active at the same time, the encoder selects the input with the highest priority and ignores the others. In a 4-to-2 priority encoder, the priority sequence is:

**I3 > I2 > I1 > I0**

This feature prevents output ambiguity and ensures predictable circuit operation.

### Truth Table

| I3 | I2 | I1 | I0 | Y1 | Y0 |
| -- | -- | -- | -- | -- | -- |
| 0  | 0  | 0  | 1  | 0  | 0  |
| 0  | 0  | 1  | X  | 0  | 1  |
| 0  | 1  | X  | X  | 1  | 0  |
| 1  | X  | X  | X  | 1  | 1  |

---

### 2-to-4 Decoder

A decoder performs the reverse operation of an encoder. It accepts a binary input and activates one corresponding output line among several possible outputs.

The 2-to-4 decoder uses a 2-bit input and generates four output lines. Depending on the binary value applied at the input, only one output line becomes HIGH while the remaining outputs stay LOW.

This type of circuit is commonly used in memory selection, address decoding, and control systems.

### Truth Table

| A1 | A0 | Y3 | Y2 | Y1 | Y0 |
| -- | -- | -- | -- | -- | -- |
| 0  | 0  | 0  | 0  | 0  | 1  |
| 0  | 1  | 0  | 0  | 1  | 0  |
| 1  | 0  | 0  | 1  | 0  | 0  |
| 1  | 1  | 1  | 0  | 0  | 0  |

---

## 3. Results

### Encoder Simulation

*(Insert Encoder Waveform Screenshot Here)*

### Decoder Simulation

*(Insert Decoder Waveform Screenshot Here)*

The generated simulation waveforms demonstrated that both the encoder and decoder produced outputs consistent with their respective truth tables.

---

## 4. Discussion

This experiment focused on the implementation of encoding and decoding circuits using VHDL and the verification of their behavior through simulation.

The priority encoder successfully converted active input signals into their corresponding binary representations. When more than one input was active, the encoder correctly selected the highest-priority input, ensuring a unique and reliable output code.

The decoder performed the reverse process by translating a binary input into one active output line. For every input combination, only the appropriate output was asserted while all other outputs remained inactive.

Simulation waveforms generated using GHDL and analyzed in GTKWave confirmed the correct functionality of both circuits. The observed outputs matched the expected theoretical values for all test cases, demonstrating the accuracy of the VHDL implementations.

---

## 5. Conclusion

The 4-to-2 Priority Encoder and 2-to-4 Decoder were successfully designed, implemented, and simulated using VHDL. The simulation results verified that both circuits operated according to their respective truth tables. This experiment enhanced understanding of combinational logic design and illustrated the importance of encoders and decoders in digital communication, data processing, and control applications.
