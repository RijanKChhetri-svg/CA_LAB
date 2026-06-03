Lab 2: Implementation and Simulation of Basic Logic Gates Using VHDL
1. Objective
To design and implement the seven fundamental digital logic gates (AND, OR, NOT, NAND, NOR, XOR, and XNOR) using VHDL.
To develop test benches for verifying the behavior of each logic gate.
To simulate the designs and analyze their waveforms using GTKWave.
To compare the simulation outputs with the expected Boolean logic results.
2. Theoretical Background

Logic gates are the fundamental building blocks of digital electronic systems. They perform logical operations on binary inputs and produce outputs based on Boolean algebra rules. Every digital circuit, from simple controllers to complex processors, is constructed using combinations of these gates.

VHDL provides built-in logical operators that directly represent hardware logic gates, making digital circuit design more straightforward and readable.

The AND gate generates a HIGH output only when all inputs are HIGH, whereas the OR gate produces a HIGH output when at least one input is HIGH. The NOT gate performs inversion by changing a logic 1 to 0 and vice versa.

NAND and NOR gates are known as universal gates because any digital logic function can be implemented using only one of these gate types. XOR and XNOR gates are widely used in arithmetic circuits, data comparison systems, error detection circuits, and parity generation.

By combining these logic functions, complex digital systems can be modeled and implemented efficiently.

3. Implementation

The logic gates were implemented using the Dataflow modeling style in VHDL. In this approach, output signals are assigned directly through concurrent statements, closely resembling actual hardware behavior.

Example VHDL structure:

library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity LOGIC_GATES is
    port (
        A : in std_logic;
        B : in std_logic;
        Y_AND  : out std_logic;
        Y_OR   : out std_logic;
        Y_NOT  : out std_logic;
        Y_NAND : out std_logic;
        Y_NOR  : out std_logic;
        Y_XOR  : out std_logic;
        Y_XNOR : out std_logic
    );
end entity LOGIC_GATES;

architecture Dataflow of LOGIC_GATES is
begin
    Y_AND  <= A and B;
    Y_OR   <= A or B;
    Y_NOT  <= not A;
    Y_NAND <= A nand B;
    Y_NOR  <= A nor B;
    Y_XOR  <= A xor B;
    Y_XNOR <= A xnor B;
end architecture Dataflow;

The design was compiled using GHDL and tested with a dedicated testbench that applied all possible input combinations to verify correct operation.

4. Discussion

The experiment demonstrated how Boolean logic operations can be translated directly into VHDL code using built-in logical operators. Unlike traditional software programs that execute instructions sequentially, VHDL models hardware behavior where multiple logic operations occur simultaneously.

During simulation, different combinations of input values were applied to the gates. The generated waveforms were analyzed using GTKWave to observe the relationship between input changes and output responses.

The results showed that each gate behaved according to its expected logical function. The AND gate produced a HIGH output only when both inputs were HIGH, while the OR gate responded whenever at least one input was active. The NOT gate successfully inverted the input signal.

Similarly, the NAND and NOR gates generated outputs opposite to those of the AND and OR gates, respectively. The XOR gate became active only when the input values differed, whereas the XNOR gate produced a HIGH output when both inputs were identical.

The waveform analysis confirmed that the outputs changed correctly and immediately in response to input transitions, accurately representing real digital hardware behavior.

5. Conclusion

The seven fundamental logic gates were successfully implemented and simulated using VHDL. The Dataflow modeling approach provided a simple and efficient method for describing logic operations. Simulation results obtained through GHDL and GTKWave matched the expected Boolean logic behavior for all input combinations.

This experiment strengthened the understanding of VHDL syntax, concurrent signal assignments, and digital logic fundamentals while providing practical experience with simulation and waveform analysis tools.