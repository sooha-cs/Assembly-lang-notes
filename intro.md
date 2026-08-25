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

### Common data types
Data type sizes vary based on architecture.   

1. Bit is one binary digit. Can be 0 or 1.    
2. Nibble is 4 bits.    
3. Byte is 8 bits.    
4. Word is 2 bytes.     
5. Double Word (DWORD) is 4 bytes. Twice the size of a word.    
6. Quad Word (QWORD) is 8 bytes. Four times the size of a word.

 Signed numbers can be positive or negative.   
 Unsigned numbers can only be positive.     

      
 *The names come from how they work.    
 Signed numbers need a sign bit to distinguish whether or not they're negative, similar to how we use the + and - signs. 🤔*


 ## About Assembly
 The end goal of a compiler is to translate high-level code into a language the CPU can understand. *This language is Assembly.*  

 ### Da Registers ✨✨
 - Have its' own storage in CPUs and are extremely fast.
 - If the data is too large to fit in a register, a register will hold a pointer to the data so it can be accessed.

GPR: General purpose registers (literally what the name suggests)
Types:
RAX - Known as the accumulator register. Often used to store the return value of a function.        
RBX - Sometimes known as the base register, not to be confused with the base pointer. Sometimes used as a base pointer for memory access.       
RDX - Sometimes known as the data register.      
RCX - Sometimes known as the counter register. Used as a loop counter.       
RSI - Known as the source index. Used as the source pointer in string operations.       
RDI - Known as the destination index. Used as the destination pointer in string operations.      
RSP - The stack pointer. Holds the address of the top of the stack.       
RBP - The base pointer. Holds the address of the base (bottom) of the stack       
