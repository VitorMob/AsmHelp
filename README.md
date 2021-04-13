# 💻 About the project
AsmHelp a simple basic help for those who are starting in assembly 
I am a simple student of assembly and I want to share my knowledge for 
those who have doubts or want to start.
We're covering here in this project just the `Intel Assembly x86`.
Feel free to have a look at [Assembly x86_64](https://www.cs.uaf.edu/2017/fall/cs301/reference/x86_64.html)

# Index
   - [Basic Syntax](#basic-syntax)
   - [Sections](#basic-sections)
   - [Registers](#registers)
   - [Syscalls](#syscalls)
   - [Types](#types)
   - [Memory Allocation](#memory-allocation)
 
# Basic Syntax
Basically a assembly instruction is made by a `mnemonic register1, register2`, and we just keep putting and taking out values form these registers.
That `mnemonic` is a assembly instruction that will make some operation between (usually) two registers.

```asm
mov eax, ebx ; Will move the value from ebx to eax
```

There you know two basics registers, `eax` and `ebx` also that the `;` can be used to create comments

# Basic Sections
[`"Roughly, a section is a range of addresses, with no gaps; all data "in" those addresses is treated the same for some particular purpose."`](https://ftp.gnu.org/old-gnu/Manuals/gas-2.9.1/html_chapter/as_4.html).
Keeping it simple, basic are memory spaces that you can separate your instructions. Below we have some basics sections that must have in you code.
We define them using the keyword `section <name>`.


| Sections | Description |
| --- | --- |
| .data | .data - section is used for declaring initialized data or constants. This data does change at runtime You can declare various constant values, file names, or buffer size, etc., in this section. |
| .bss | .bss  - section is used for declaring variables |
| .text | .text - section is used for keeping the actual code This section must begin with the declaration global _start, which tells the kernel where the program execution begins. |

Note: Use  `nasm -f elf_i386 <file>` to assemble and `ld <file.o> -o <output>` to link

I made a script where you can assemble and link quickly
You dont need to use, but is there anyway. Just do the following `_nasm file.asm file 32`
