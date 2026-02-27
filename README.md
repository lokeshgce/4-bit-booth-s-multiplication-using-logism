# 4-bit-booth-s-multiplication-using-logism
Designed a 4-bit signed Booth Multiplier in Logisim. The circuit implements Booth’s Algorithm using registers, an adder/subtractor, control logic, and arithmetic right shifts over four clock cycles, producing a 4-bit signed product output.

🔢 4-Bit Booth Multiplier (Sequential) – Logisim
📌 Project Overview

     This project implements a 4-bit sequential Booth multiplier using Logisim.
     The circuit multiplies two 4-bit signed numbers (two’s complement) and produces a 4-bit result after 4 clock cycles.

⚠️ Note:
Only the lower 4 bits of the product are taken as output.
Higher bits are discarded (overflow ignored).

🎯 Features

     ✔️ Signed multiplication using Booth algorithm

     ✔️ Two 4-bit inputs: Multiplicand (M) and Multiplier (Q)

     ✔️ Sequential operation with clock control

     ✔️ Completes in 4 clock cycles

     ✔️ Uses add/subtract + arithmetic shift

     ✔️ Outputs lower 4 bits of the product


🧠 Booth Algorithm Logic

The algorithm checks Q₀ and Q₋₁ at every clock cycle:


| Q₀ | Q₋₁ | Operation    |
| -- | --- | ------------ |
| 0  | 0   | No operation |
| 1  | 1   | No operation |
| 0  | 1   | A = A + M    |
| 1  | 0   | A = A − M    |

After the operation → perform Arithmetic Right Shift on:

[A, Q, Q₋₁]

Repeat for 4 cycles.

FLOW DIAGRAM:


<img width="327" height="429" alt="both multiplication" src="https://github.com/user-attachments/assets/3332f5f9-2384-456e-9d4a-9dfa34a28fc4" />


🏗️ Circuit Components

The Logisim circuit contains:

Registers

     M (Multiplicand Register) – 4 bit

     Q (Multiplier Register) – 4 bit

     A (Accumulator Register) – 4 bit

     Q₋1 register – 1 bit

     Arithmetic Unit

     4-bit Adder/Subtractor

     Controlled using Add/Sub signal

     Control Logic

     Comparator for Q₀ and Q₋₁

Operation decoder:
     Add
     Subtract
     No operation

Shifting Unit

Arithmetic Right Shift of:
     A
     Q
     Q₋₁

Clock

     One clock pulse = One Booth iteration

     Total cycles required = 4

Output

     Final output = Lower 4 bits of Q register after 4 cycles


⏱️ Timing of Operation

| Clock Cycle | Operation Performed           |
| ----------- | ----------------------------- |
| Cycle 1     | Booth check → Add/Sub → Shift |
| Cycle 2     | Booth check → Add/Sub → Shift |
| Cycle 3     | Booth check → Add/Sub → Shift |
| Cycle 4     | Booth check → Add/Sub → Shift |
| Final       | Q (lower 4 bits) = Output     |


🧮 Example Test Case
Input

     Multiplicand (M) = 0011 → +3
     Multiplier (Q) = 0010 → +2

     Expected Full Product

     3 × 2 = 6 → 00000110 (8-bit)

     Circuit Output (Lower 4 bits only)

     0110 → 6

     Signed Example

     Multiplicand (M) = 1101 → −3
     Multiplier (Q) = 0010 → +2

     Full product = −6 → 11111010
     Lower 4 bits = 1010 → −6 (4-bit two’s complement)

⚠️ Overflow Note

     Since only 4 output bits are used:

     Results outside range −8 to +7 will overflow

     Higher product bits are ignored

Example:
    4 × 4 = 16 → Actual: 00010000
    Output: 0000 (overflow)

▶️ How to Run (Logisim)

    Open the .circ file in Logisim

    Enter 4-bit values for:

    Multiplicand (M)

    Multiplier (Q)

    Reset the circuit

    Apply 4 clock pulses

    Read the 4-bit output from Q


Circuit Connection:

<img width="876" height="640" alt="Screenshot 2026-02-28 005021" src="https://github.com/user-attachments/assets/c2e7fe79-b01e-4fad-9bc0-f0160ba28e66" />



📚 Learning Outcomes

    Understanding Booth multiplication for signed numbers

    Designing sequential arithmetic circuits

    Implementing register transfer operations

    Working with clock-based digital systems in Logisim

👨‍💻 Author

Lokesh A

3rd Year ECE student Student

Electronics and Communication Engineering
