# **README: Mano Basic Computer Implementation in Verilog & Proteus**

## **Project Overview**
This project implements **Mano's Basic Computer**—a simplified computer architecture model—using **Verilog HDL** for digital design and **Proteus** for simulation. The goal is to demonstrate fundamental computer operations such as instruction fetch, decode, execute cycles, memory access, and ALU operations.

---

## **Project Structure**
```
Mano_Basic_Computer/
│
├── verilog/               # Verilog source files
│   ├── Memory.v           # 4096x16-bit memory module
│   ├── ALU.v              # Arithmetic Logic Unit
│   ├── ControlUnit.v      # Finite State Machine for instruction execution
│   ├── Registers.v        # PC, IR, AC, and other registers
│   └── ManoComputer.v     # Top-level module
│
├── proteus/               # Proteus simulation files
│   ├── Mano_Computer.DSN  # Schematic design
│   └── Simulation Results # Logs & waveform captures
│
├── test_programs/         # Sample assembly programs (machine code)
│   └── example_program.hex
│
└── README.md              # This file
```

---

## **Features**
✔ **16-bit Instruction Set** (4-bit opcode + 12-bit address)  
✔ **4096x16-bit Memory** (stores instructions & data)  
✔ **Basic ALU Operations** (ADD, SUB, AND, OR)  
✔ **Control Unit** (Fetch-Decode-Execute cycle)  
✔ **Register File** (PC, IR, AC, etc.)  
✔ **Proteus Simulation** (Visual verification of operations)  

---

## **Prerequisites**
- **Verilog Simulator** (e.g., **Icarus Verilog**, **ModelSim**, or **Xilinx Vivado**)
- **Proteus Design Suite** (for schematic & simulation)
- **Basic knowledge of computer architecture**

---

## **How to Run**
### **1. Verilog Simulation**
#### Using **Icarus Verilog**:
```bash
iverilog -o mano_computer ManoComputer.v ALU.v Memory.v ControlUnit.v
vvp mano_computer
```
#### Using **GTKWave** (for waveform viewing):
```bash
gtkwave dump.vcd
```

### **2. Proteus Simulation**
1. Open `Mano_Computer.DSN` in Proteus.
2. Load the test program (`example_program.hex`) into memory.
3. Run the simulation and observe the control signals, register changes, and memory operations.

---

## **Sample Test Program**
A simple program to **add two numbers** and store the result in memory:
```assembly
LDA 0x100    // Load value from address 0x100 into AC
ADD 0x101    // Add value from address 0x101 to AC
STA 0x102    // Store result in address 0x102
HLT          // Halt execution
```
(Convert to machine code and store in `example_program.hex`.)

---

## **Expected Output**
- **Waveform View (Proteus/GTKWave):**  
  - Control signals (`fetch`, `decode`, `execute`)  
  - Register updates (`PC`, `IR`, `AC`)  
  - Memory read/write operations  

- **Console Output (if using a testbench):**  
  ```
  [INFO] Instruction FETCH: PC = 0x000
  [INFO] Instruction DECODE: OPCODE = LDA
  [INFO] EXECUTE: AC = 0x00FF
  [INFO] Instruction FETCH: PC = 0x001
  ...
  ```

---

## **Future Improvements**
- Add more **ALU operations** (MUL, DIV, SHIFT).  
- Implement **interrupt handling**.  
- Port to **FPGA** (using Xilinx or Altera tools).  
- Develop an **assembler** to convert assembly code to machine code.  

---

## **References**
- M. Morris Mano, *"Computer System Architecture"*  
- Verilog HDL IEEE Standard  
- Proteus Simulation Guide  

---

## **License**
This project is open-source under the **MIT License**.

---

## **Contact**
For questions or contributions, please contact:  
📧 [Your Email]  
🔗 [GitHub Repository Link]  

🚀 **Happy Learning!** 🚀
