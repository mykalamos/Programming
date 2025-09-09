# Concurrency

## Core concepts

| Concept        | Description                                                                 | Scope                        | Key Characteristics                                                  | Use Case Example                           |
|----------------|-----------------------------------------------------------------------------|------------------------------|------------------------------------------------------------------------|--------------------------------------------|
| **Multithreading** | Running multiple threads (smaller units of a process) in parallel within a single process | **Within a single process**  | Shares memory, faster context switch, thread-safe code required        | A web server handling multiple requests     |
| **Multitasking**   | Running multiple tasks (processes) seemingly at the same time             | **System-wide (multiple processes)** | Isolated memory, higher overhead, managed by OS scheduler              | Running a browser and an IDE simultaneously |
| **Concurrency**    | Structuring a program to handle multiple tasks, not necessarily in parallel | **Conceptual/programming model** | Tasks **may or may not** run in parallel (e.g., interleaving on single core) | Handling UI events while downloading a file |

# TL;DR

| Term               | Scope             | Description                                                  | Generalized Under            |
|--------------------|------------------|--------------------------------------------------------------|------------------------------|
| **Multitasking**   | OS-level         | Running multiple processes seemingly at the same time        | **Concurrent Computing**     |
| **Multithreading** | App-level        | Running multiple threads within a single process             | **Concurrent Computing**     |
| **Concurrency**    | Design-level     | Structuring programs to handle multiple tasks independently  | **Concurrent Computing**     |
| **Parallelism**    | Execution-level  | Actually running tasks simultaneously (multi-core/CPU)       | Subset of **Concurrency**    |

# Hierarchy
```
Concurrent Computing (broad concept)
├── Concurrency (design approach)
│   ├── Multitasking (OS-level)
│   ├── Multithreading (App-level)
│   ├── Asynchronous programming
│   └── Parallelism (when tasks truly run simultaneously)
```