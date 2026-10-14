# Single-Cycle MIPS Datapath in MyHDL

A Google Colab notebook (`CA.ipynb`) that models a simplified single-cycle MIPS processor datapath in Python using [MyHDL](https://www.myhdl.org/), simulates it for 20 clock cycles, and plots the signal waveforms with `myhdlpeek`. Built for a Computer Architecture course.

## What Is Implemented

Each datapath component is a MyHDL block:

| Block | Role |
| :--- | :--- |
| `pc` | Program counter, updated on the rising clock edge |
| `add1` | PC + 1 |
| `insmemory` | Instruction memory, loaded from `instructions2.txt` (first 22 lines) |
| `decode` | Splits the 32-bit instruction into opcode, rs, rt, rd, immediate and funct fields |
| `Control` | Main control unit producing RegDst, RegWrite, ALUSrc, ALUOp, MemWrite, MemRead, MemToReg, Branch |
| `registers` | 32-entry register file, initial values loaded from `registerfile.txt` |
| `signextend`, `shift` | Immediate pass-through and shift-left-by-2 for branch offsets |
| `ALU` | ADD, SUB, AND, OR, XOR |
| `add2` | Branch target adder |
| `mux1`–`mux4` | Write-register, ALU-source, next-PC and write-back multiplexers |
| `datamemory` | 100-word data memory |

Instructions decoded by the control unit (codes as written in the notebook):

- R-type (opcode 0): ADD (funct 32), SUB (34), AND (54), OR (55), XOR (56)
- I-type: ADDI (opcode 8), SUBI (36), LW (35), SW (43), BEQ (4)

A testbench toggles the clock 20 times, runs the simulation and attaches a `Peeker` to all 30 signals to draw a waveform plot (saved as an image in the notebook output).

## Known Limitations

- Register write-back does not update the stored register array, and the ALU `zero` flag is assigned outside the combinational logic, so register writes and taken branches are not fully functional.
- The input files are read from Google Drive (`/content/gdrive/MyDrive/`) and are **not included** in this repository.

## Tech Stack

- Python 3 on Google Colab
- MyHDL 0.11, myhdlpeek 0.0.10

## How to Run

1. Open `CA.ipynb` in Google Colab.
2. Upload to your Google Drive (`MyDrive/`):
   - `instructions2.txt` – one 32-bit binary instruction per line (22 lines are read),
   - `registerfile.txt` – 32 lines, one initial integer value per register.
3. Run all cells; the drive mount cell will ask for authorization. The last cell runs the simulation and shows the waveforms.

---

*Developed by Khaled Walid*
