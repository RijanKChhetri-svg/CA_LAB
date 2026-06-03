Lab 1: Introduction to VHDL Programming and Open-Source Simulation Tools
1. Objective
To install and familiarize ourselves with the open-source VHDL development environment consisting of VS Code, GHDL, and GTKWave.
To understand the basic building blocks of a VHDL design, including Libraries, Entities, and Architectures.
To create, compile, simulate, and verify a simple digital circuit using VHDL.
2. Theory

VHDL (VHSIC Hardware Description Language) is a standardized hardware description language developed for modeling and designing digital systems. VHSIC stands for Very High-Speed Integrated Circuit. VHDL is widely used for describing hardware behavior, structure, and functionality before implementation on physical devices.

Unlike traditional programming languages such as C or Python that execute instructions sequentially, VHDL is designed to represent hardware operations that occur simultaneously. This makes it suitable for modeling digital circuits where multiple signals change and interact in parallel.

Main Components of a VHDL Design

A typical VHDL program contains three major sections:

Libraries and Packages – Provide predefined data types, operators, and functions.
Entity – Defines the external interface of the design, including inputs and outputs.
Architecture – Describes the internal operation and logic of the entity.
3. Core Structural Components
A. Libraries and Packages

Libraries contain reusable resources required during hardware design. Two commonly used libraries are:

STD Library: Included automatically and provides basic data types such as bit, boolean, integer, and character.
IEEE Library: Must be imported explicitly and contains standard logic types used in digital design.
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.NUMERIC_STD.ALL;
B. Entity

The entity specifies the circuit's external interface by defining its ports, directions, and data types.

Port directions include:

in – Input signal
out – Output signal
inout – Bidirectional signal
Example: 2-Input AND Gate
entity AND_GATE is
    port(
        A : in std_logic;
        B : in std_logic;
        Y : out std_logic
    );
end entity AND_GATE;
C. Architecture

The architecture describes the functionality of the entity. It contains declarations and statements that determine circuit behavior.

architecture Dataflow of AND_GATE is
begin
    Y <= A and B;
end architecture Dataflow;
4. VHDL Modeling Styles

VHDL provides different methods for describing the same hardware circuit.

1. Behavioral Modeling

Behavioral modeling focuses on describing how the circuit operates using sequential statements inside a process block.

architecture Behavioral of AND_GATE is
begin
    process(A, B)
    begin
        Y <= A and B;
    end process;
end architecture Behavioral;
2. Dataflow Modeling

Dataflow modeling represents the movement of data through continuous signal assignments and is commonly used for simple combinational circuits.

architecture Dataflow of AND_GATE is
begin
    Y <= A and B;
end architecture Dataflow;
3. Structural Modeling

Structural modeling builds larger circuits by connecting smaller sub-components together.

architecture Structural of AND_GATE is
    component AND2
        port(X, Z : in std_logic; W : out std_logic);
    end component;
begin
    U1 : AND2 port map(X => A, Z => B, W => Y);
end architecture Structural;
5. Data Types and Signals
std_logic

The std_logic data type supports multiple logic states, including:

'0' (Logic Low)
'1' (Logic High)
'Z' (High Impedance)
'U' (Uninitialized)

This makes it more realistic than the simple binary bit type.

std_logic_vector

A std_logic_vector represents a collection of logic bits, commonly used for buses and registers.

Example:

std_logic_vector(7 downto 0)

This declaration creates an 8-bit vector with bit 7 as the Most Significant Bit (MSB).

Signals

Signals act as internal connections within an architecture and are used to transfer values between different parts of a design.

architecture Example of MY_CIRCUIT is
    signal internal_wire : std_logic;
    signal data_bus : std_logic_vector(7 downto 0);
begin
end architecture Example;
6. VHDL Simulation Flow

Before implementing a design on hardware, it is tested through simulation using the following process:

Source Code (.vhd)
        |
        V
Analysis (ghdl -a)
        |
        V
Elaboration (ghdl -e)
        |
        V
Simulation (ghdl -r)
        |
        V
VCD Waveform File
        |
        V
GTKWave Visualization
Analysis

The source code is checked for syntax and semantic errors.

Elaboration

The design hierarchy is created, and entities are linked with their corresponding architectures.

Simulation

Input test cases are applied, and output responses are generated.

Waveform Visualization

GTKWave displays the generated waveform file, allowing users to inspect signal behavior over time.

7. Discussion

This experiment introduced the complete workflow of VHDL design and simulation using open-source tools. The combination of VS Code, GHDL, and GTKWave provided an efficient environment for hardware development and testing.

The simulation process highlighted one of the most important features of hardware description languages: concurrency. Unlike software programs that execute instructions sequentially, VHDL models hardware where multiple operations occur simultaneously. The waveforms generated in GTKWave clearly demonstrated how output signals responded immediately to input changes, accurately reflecting real digital circuit behavior.

8. Conclusion

The experiment successfully demonstrated the process of designing, compiling, simulating, and verifying a simple VHDL circuit using open-source software tools. Fundamental concepts such as libraries, entities, architectures, signals, and modeling styles were explored. The successful simulation and waveform analysis confirmed the correctness of the design and provided practical experience with the VHDL development workflow.