## About CPU
The CPU reads and executes instructions from memory one by one. 
Assembly language gives direct instructions to the CPU.

Registers are tiny storage boxes inside the CPU that hold a single number, accessible much faster than RAM.

The Program Counter (PC) is a special register that holds the memory address of the next instruction to execute.    
It automatically advances after each instruction.

Key CPU facts:
  1.  Executes one instruction at a time.
  2.  Only understands numbers (instructions, data, and addresses are all numbers)
  3.  Has no memory of its own except registers — everything else is stored in RAM
  4.  Modern CPUs execute billions of instructions per second
  
## About Computer Memory
> [!NOTE]
> Memory (RAM) is a grid of numbered slots. Each slot has a unique address and holds one byte (0–255).

| **Fact**     | **Explanation** |
| -----------|------------|
| Every byte has an address | Addresses start at 0 and go up to millions or billions |
| Memory is volatile	| RAM contents are lost when the computer is turned off |
| Reading is non-destructive | Reading an address leaves the data intact |
| Writing overwrites | Writing to an address permanently replaces the old data |

> [!NOTE]
> Registers are accessed by ***name*** i.e. (rax, rbx…) while Memory is accessed via ***Addresses*** (1000, msg…)
> The CPU cannot work directly with data in memory — data must be loaded into registers first.

## Computer Instructions 
The assembler converts human-readable code (e.g. mov rax, 5) into an instruction code the CPU understands.


Fetch-Execute Cycle (cycle that repeats FOREVERRRR):     
FETCH — read instruction at address in PC   
EXECUTE — perform that instruction    
ADVANCE — move PC to next instruction (PC + instruction size)  

------
Instruction structure:

Opcode — what to do (e.g. mov, add, cmp)
Operands — what to do it to (e.g. rax, 5, [result])

***Basically***
```
Instruction = opcode + operands
```

## The x86-64 Architecture
x86-64 = x86 family (from Intel 8086 lineage) + 64-bit registers.    
Each register holds 64 bits; memory addresses are 64 bits wide.   
Register names differ by architecture:    
| **Architecture** | **Registers** | **Exp** |
|------------|--------------|-------------|
| x86-64 | rax, rbx, rcx...	| mov rax, 5 |
| ARM | x0, x1, x2...  | mov x0, #5 |
| RISC-V | a0, a1, a2... | li a0, 5 |
