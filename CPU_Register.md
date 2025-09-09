# CPU Registers

Ultra-fast, small memory units inside the CPU that store data, addresses, or instructions needed for immediate processing.

# Overview

| Register Type         | Description                                                | Common Names (x86/x64)     |
|------------------------|------------------------------------------------------------|-----------------------------|
| **General-purpose**     | Store operands, variables, or intermediate results         | `EAX`, `EBX`, `ECX`, `EDX` (32-bit) / `RAX`, `RBX`, etc. (64-bit) |
| **Instruction Pointer**| Points to the next instruction to execute                  | `IP`, `EIP`, `RIP`          |
| **Stack Pointer**       | Points to the top of the call stack                       | `SP`, `ESP`, `RSP`          |
| **Base Pointer**        | Points to the base of the current stack frame             | `BP`, `EBP`, `RBP`          |
| **Flags Register**      | Stores status flags after operations (zero, carry, etc.)  | `FLAGS`, `EFLAGS`, `RFLAGS` |
| **Index Registers**     | Used for looping or memory indexing                       | `SI`, `DI`, `ESI`, `EDI`, `RSI`, `RDI` |
| **Segment Registers**   | Used in segmented memory models (mostly legacy)           | `CS`, `DS`, `SS`, `ES`, `FS`, `GS` |
| **Control Registers**   | Used by the CPU to manage operating modes and memory      | `CR0`–`CR4`, `CR8`          |

