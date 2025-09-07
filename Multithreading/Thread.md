# Thread

- Smallest unit of execution that can be scheduled by the operating system.
- Runs within a process `p`
- Shares `p`'s
    - Memory
    - Resources e.g. file handles
- Has own
    - Stack
    - Instruction pointer - special CPU register that holds the memory address of the next instruction to be executed.
        - aka Program Counter (PC)
        - x86 = EIP
        - x64 = RIP
    - CPU registers
- Managed OS Scheduler