# .NET Garbage Collection: Finalization Flow

- **Finalization Queue**
- **F-Reachable Queue**.

---

## Overview

- Objects with a finalizer (`~ClassName()`) are placed in the **Finalization Queue**.
- When the object becomes unreachable, it is moved to the **F-Reachable Queue**.
- The **Finalizer Thread** calls `Finalize()`.
- After finalization, the object is eligible for collection unless it is resurrected.

---

## Lifecycle

```mermaid
flowchart TD
    A[Object with Finalizer Allocated] --> B[Finalization Queue]
    B --> C[GC Marks Object Unreachable]
    C --> D[F-Reachable Queue]
    D --> E[Finalizer Thread Invokes Finalize]
    E --> F{Was Object Resurrected?}
    F -- Yes --> G[Object Lives Again on Heap]
    G --> H[GC Runs Again]
    H --> C
    F -- No --> I[Eligible for Collection in Next GC]
```
- NB: The `freachable queue` is part of the runtime’s root set — any object on it is considered alive by the GC until finalization completes.