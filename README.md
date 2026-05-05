# 💻 MIPS Instruction Visualizer

[![Tech: Web-Based](https://img.shields.io/badge/Tech-JavaScript/HTML5-orange.svg)]()
[![Field: Computer Architecture](https://img.shields.io/badge/Field-Computer--Architecture-blue.svg)]()
[![Usage: Educational](https://img.shields.io/badge/Usage-Teaching--Tool-green.svg)]()

A high-fidelity, web-based MIPS simulator designed to bridge the gap between abstract assembly code and physical hardware execution. This tool provides a real-time visualization of the CPU pipeline, register states, and memory mapping.

## 🎯 Educational Purpose
This simulator was developed to help students visualize the **Fetch-Decode-Execute** cycle. It eliminates the "black box" of computer architecture by providing transparency into how instructions like `LW`, `SW`, `ADD`, and `BEQ` manipulate hardware state.

## ✨ Key Features
*   **Real-Time Pipeline Visualization:** Watch instructions move through the data path.
*   **Interactive Register File:** Monitor changes to `$t0-$t9`, `$s0-$s7`, etc., as code executes.
*   **Memory Mapping:** Visual representation of the Data and Text segments.
*   **Instruction Support:** Comprehensive support for R-type, I-type, and J-type MIPS instructions.

## 🛠 Technical Implementation
The simulator emulates the MIPS 32-bit architecture logic:
*   **ALU Logic:** Pure [Language, e.g., JavaScript] implementation of arithmetic and logical operations.
*   **Control Unit:** Decodes OpCodes and Funct codes to set control signals (RegWrite, MemRead, etc.).
*   **State Persistence:** Maintains a virtualized memory space and register set during execution.



## 🚀 How to Use
1. **Load Code:** Paste your MIPS assembly code into the editor.
2. **Step Execution:** Use the "Step" button to execute one clock cycle at a time.
3. **Analyze:** Observe the highlighted data paths and updated register values.

## 📂 Project Structure
*   `/src/emulator`: The core logic for instruction decoding and execution.
*   `/src/ui`: The visualization engine and interactive hardware components.
*   `/examples`: Sample MIPS scripts (e.g., Fibonacci, Array Sorting).

---
*Developed by Khaled Walid for the next generation of Computer Architects.*
