# Two-Pass Assembler Implementation

## Aim  
To implement a **Two-Pass Assembler** that takes a **machine operation code file** and an **assembly-level instruction file** as input. After execution, the assembler generates:  
- The **binary code** for each instruction in the **machine code file**.  
- **Label information** in the **symbol table file**.  

## Theory  

### Introduction  
An **assembler** is a program that converts **low-level assembly code** into **relocatable machine code**, generating necessary metadata for the **loader**. It serves as a bridge between **assembly language** (a human-readable abstraction) and **binary machine code**, which the **CPU** can process.  

A **Two-Pass Assembler** is used to efficiently process assembly code and generate the corresponding machine code.  

### Single-Pass Assembler  
A **single-pass assembler** directly generates **object code** in memory for immediate execution. It scans the **source code** once, evaluates **mnemonics** in the operation field, and resolves **symbols and literals** to produce machine code. However, it cannot handle **forward references** (symbols used before they are defined).  

### Two-Pass Assembler  
A **Two-Pass Assembler** overcomes the limitations of single-pass assemblers by processing the code in two stages:  

#### Pass 1  
- Defines **symbols** and **literals**, storing them in the **symbol table** and **literal table**, respectively.  
- Keeps track of the **location counter**.  
- Processes **pseudo-operations**.  

#### Pass 2  
- Converts **symbolic opcodes** into their **numeric representations**.  
- Resolves **literal values**.  
- Generates the final **object code**.  

By separating **symbol resolution** and **code generation**, a **Two-Pass Assembler** eliminates confusion caused by **forward references** and ensures a structured conversion process.  

## Input  
- **Assembly Code** – The source code written in assembly language.  
- **Opcode Instruction File** – Contains the **binary representation** of opcodes present in the assembly code.  

## Output  
- **Symbol Table** – A table storing **symbol definitions** and their addresses, created in **Pass 1**.  
- **Intermediate Code** – A structured representation of the source code after **Pass 1**, containing **opcodes and operands**.  
- **Final Assembly Code** – The fully processed assembly code after completing both passes.  

---


