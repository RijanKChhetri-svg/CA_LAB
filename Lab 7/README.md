# Lab 7: VHDL Modeling of Sequential Circuits – Flip-Flops

## Objective

- To implement **SR, D, JK, and T flip-flops** using VHDL.
- To verify the behavior of sequential circuits using a clock signal.
- To simulate and analyze the operation of each flip-flop in GTKWave.

---

## Theory

A **flip-flop** is a sequential storage element that can hold one bit of binary information. Unlike combinational logic, the output of a flip-flop depends on both the present inputs and its previously stored value. In this experiment, all flip-flops are **positive-edge triggered**, meaning they respond only on the rising edge of the clock.

### SR Flip-Flop

The **SR (Set-Reset) flip-flop** contains two control inputs: **S** and **R**. It can set, reset, or hold its current state. If both inputs become HIGH at the same time, the output enters an undefined state.

| S | R | Next Q |
|:-:|:-:|:------:|
| 0 | 0 | Hold |
| 0 | 1 | 0 (Reset) |
| 1 | 0 | 1 (Set) |
| 1 | 1 | Invalid |

### D Flip-Flop

The **D (Data) flip-flop** stores the value applied to the **D** input whenever the clock transitions from LOW to HIGH. This design avoids the invalid condition present in the SR flip-flop.

**Q(next) = D**

### JK Flip-Flop

The **JK flip-flop** improves the SR flip-flop by replacing the invalid state with a toggle operation. When **J = K = 1**, the output changes to its opposite state.

**Q(next) = JQ' + K'Q**

| J | K | Next Q |
|:-:|:-:|:------:|
| 0 | 0 | Hold |
| 0 | 1 | Reset |
| 1 | 0 | Set |
| 1 | 1 | Toggle |

### T Flip-Flop

The **T (Toggle) flip-flop** changes its output on each rising clock edge whenever **T = 1**. If **T = 0**, the output remains unchanged.

**Q(next) = T ⊕ Q**

| T | Next Q |
|:-:|:------:|
| 0 | Hold |
| 1 | Toggle |

---

## Simulation Output

The VHDL designs were simulated successfully, and the generated waveform was examined using **GTKWave**. All input and output signals, along with the clock, were displayed to observe the behavior of each flip-flop.

### Observation

The waveform verified the expected operation of all four flip-flops. The SR flip-flop correctly performed the set, reset, and hold operations for valid inputs. The D flip-flop captured the input value on every positive clock edge. The JK flip-flop toggled correctly when both J and K were HIGH, while the T flip-flop alternated its output whenever T was HIGH. In every case, **QB** remained the complement of **Q**, confirming correct functionality.

---

## Conclusion

This experiment demonstrated the implementation and simulation of **SR, D, JK, and T flip-flops** using Behavioral VHDL. Each circuit responded correctly to the rising edge of the clock, and the generated waveforms matched the expected truth tables. A common testbench was used to validate all designs, making it easier to compare their behavior. The experiment provided practical knowledge of sequential logic, which is widely used in digital systems such as **registers, counters, shift registers, and finite state machines**.

---

## Output

<p align="center">
  <img src="Flipflopp.png" alt="GTKWave Waveform" width="900">
</p>

<p align="center">
<b>Figure 7.1:</b> Simulation waveform of SR, D, JK, and T flip-flops observed in GTKWave.
</p>