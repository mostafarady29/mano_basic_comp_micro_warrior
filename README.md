# **Updated README with Full Instruction Set**

## **Mano Basic Computer Implementation in Verilog & Proteus**

## **Project Overview**
This project implements **Mano's Basic Computer**—a simplified computer architecture model—using **Verilog HDL** for digital design and **Proteus** for simulation. The implementation now includes the **complete instruction set** as defined in Mano's original design.

---

## **Complete Instruction Set**
The Mano Basic Computer supports the following instructions:

### **Memory Reference Instructions**
| Mnemonic | Opcode | Description                     |
|----------|--------|---------------------------------|
| `AND`    | `0x00` | Bitwise AND with AC             |
| `ADD`    | `0x01` | Add to AC                       |
| `LDA`    | `0x02` | Load into AC                    |
| `STA`    | `0x03` | Store from AC                   |
| `BUN`    | `0x04` | Branch Unconditionally          |
| `BSA`    | `0x05` | Branch and Save Return Address  |
| `ISZ`    | `0x06` | Increment and Skip if Zero      |

### **Register Reference Instructions**
| Mnemonic | Opcode   | Description                     |
|----------|----------|---------------------------------|
| `CLA`    | `0x7800` | Clear AC                        |
| `CLE`    | `0x7400` | Clear E (overflow bit)          |
| `CMA`    | `0x7200` | Complement AC                   |
| `CME`    | `0x7100` | Complement E                    |
| `CIR`    | `0x7080` | Circular Right Shift            |
| `CIL`    | `0x7040` | Circular Left Shift             |
| `INC`    | `0x7020` | Increment AC                    |
| `SPA`    | `0x7010` | Skip if AC Positive             |
| `SNA`    | `0x7008` | Skip if AC Negative             |
| `SZA`    | `0x7004` | Skip if AC Zero                 |
| `SZE`    | `0x7002` | Skip if E Zero                  |
| `HLT`    | `0x7001` | Halt Execution                  |

### **Input/Output Instructions**
| Mnemonic | Opcode   | Description                     |
|----------|----------|---------------------------------|
| `INP`    | `0xF800` | Input Character to AC           |
| `OUT`    | `0xF400` | Output Character from AC        |
| `SKI`    | `0xF200` | Skip if Input Flag Set          |
| `SKO`    | `0xF100` | Skip if Output Flag Set         |
| `ION`    | `0xF080` | Interrupt On                    |
| `IOF`    | `0xF040` | Interrupt Off                   |
| `PUSH`   | `0xF008` | Push AC to Stack                |
| `POP`    | `0xF004` | Pop from Stack to AC            |

---

## **Updated Project Structure**
```
Mano_Basic_Computer/
│
├── verilog/               # Verilog source files
│   ├── Memory.v           # 4096x16-bit memory
│   ├── ALU.v              # Extended ALU operations
│   ├── ControlUnit.v      # Enhanced FSM for full instruction set
│   ├── Registers.v        # Now includes E (overflow) flag
│   ├── IO_Module.v        # New: Handles input/output operations
│   └── ManoComputer.v     # Top-level module with all features
│
├── proteus/               # Proteus simulation files
│   ├── Mano_Computer.DSN  # Updated schematic
│   └── Simulation Results # New I/O test cases
│
├── test_programs/         # Extended test programs
│   ├── arithmetic_test.hex
│   ├── io_test.hex
│   └── stack_test.hex
│
└── README.md              # This updated file
```

---

## **New Features in This Version**
✅ **Complete 16-bit instruction set implementation**  
✅ **Enhanced ALU** with bitwise operations and shifts  
✅ **I/O module** for input/output operations  
✅ **Stack operations** (PUSH/POP)  
✅ **Interrupt handling** (ION/IOF)  
✅ **Conditional branching** (SPA/SNA/SZA/SZE)  

---

## **How to Test New Features**
### **1. Arithmetic & Logic Test**
```assembly
LDA 0x100    // Load value
ADD 0x101    // Add another value
CMA          // Complement AC
STA 0x102    // Store result
HLT          // Halt
```

### **2. I/O Test**
```assembly
INP         // Input character
OUT         // Output character
SKI         // Skip if input ready
SKO         // Skip if output ready
HLT
```

### **3. Stack Test**
```assembly
LDA 0x100   // Load value
PUSH        // Push to stack
POP         // Pop from stack
STA 0x101   // Store popped value
HLT
```

---

## **Simulation Results**
The enhanced design now shows:
- Correct execution of **register-reference instructions**
- Proper **I/O operations** in Proteus
- **Stack pointer behavior** in waveform views
- **Interrupt handling** simulation

---

## **Future Work**
- Add **floating-point operations**
- Implement **memory-mapped I/O**
- Create **assembler tool** for easier programming
- Port to **FPGA with physical I/O**

---
 
