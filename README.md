
# CPU Simulator in C

A complete CPU simulator implemented in C as part of the LU2IN006 course (2024–2025). The project replicates several core components of a CPU: memory segmentation, pseudo-assembly parsing, stack handling, dynamic memory, and instruction execution.

## 📁 Project Structure

- `hash.h / hash.c` – Generic hash table (string key → pointer value)
- `memory.h / memory.c` – Memory handler for allocation/deallocation
- `parser.h / parser.c` – Parser for pseudo-assembly files (.DATA and .CODE)
- `cpu.h / cpu.c` – CPU simulation, instruction handling, and segment management
- `test_exo[1-8].c` – Test files for each feature/component
- `Makefile` – Compiles all modules and test cases

## 🚀 Features

### 1. Hash Table
- Linear probing with TOMBSTONE deletion
- Insert, get, remove, display

### 2. Dynamic Memory Management
- Manual memory segmentation
- Segment allocation, merging, deallocation

### 3. Pseudo-Assembler Parser
- Parses `.DATA` and `.CODE` sections
- Maps labels and variable memory addresses

### 4. CPU Memory Segments
- `DS`: Data segment for variable storage
- `CS`: Code segment for instruction execution
- `SS`: Stack segment for push/pop
- `ES`: Dynamic segment with alloc/free using various fit strategies

### 5. Addressing Modes (Regex-based)
- Immediate, Register, Direct, Indirect, Segment override

### 6. Instruction Execution
- Handles instructions like `MOV`, `ADD`, `JMP`
- Register updates and memory operations

### 7. Stack Operations
- Stack managed via SP/BP registers
- Implements PUSH and POP

### 8. Extra Segment
- Implements First Fit, Best Fit, and Worst Fit strategies
- Handles `[ES:REG]` explicit addressing

## 🧪 Running Tests

Compile with `make`, then run any `test_exo[1-8]` executable:
```bash
make
./test_exo1
```
Choose an option from the interactive menu to test specific functionality.

## 📚 Example Assembly File

Supports pseudo-assembly files structured like:
```asm
.DATA
var1 DW 10
var2 DB 42

.CODE
MOV AX, var1
ADD AX, var2
JMP END
END:
```

## 👨‍💻 Authors

- **Andre Bertok**
- **Olivier Huang**
