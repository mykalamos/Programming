# Interlocked
https://devblogs.microsoft.com/oldnewthing/20130913-00/?p=3243
http://www.albahari.com/threading/part4.aspx#_Interlocked

- Non-blocking atomic operations
- A statement is intrinsically atomic if it executes as a single indivisible instruction on the underlying processor.
- Strict atomicity precludes any possibility of preemption
- Statements that combine more than one read/write operation are never atomic

| Concept             | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| CPU fence           | A CPU instruction that enforces memory operation ordering    |
| Needed when?        | In concurrent code to prevent reordering & visibility issues |
| Provided in .NET by | `Thread.MemoryBarrier()`, `Volatile`, `Interlocked`          |
| Used by whom?       | Low-level concurrent code, lock-free algorithms, runtimes    |

## CPU Fence Instructions

## x86 / x64 Assembly

```asm
; Full memory fence (prevents all load/store reordering)
MFENCE

; Load fence (prevents load → load reordering)
LFENCE

; Store fence (prevents store → store reordering)
SFENCE

; Atomic instruction with implicit full fence
LOCK XADD [mem], reg
```
## 🧠 ARM / ARM64 Assembly
```asm
; Full memory barrier
DMB SY    ; Data Memory Barrier with full system scope

; Data Synchronization Barrier (waits for memory ops to complete)
DSB SY

; Instruction Synchronization Barrier (used after self-modifying code)
ISB
```
