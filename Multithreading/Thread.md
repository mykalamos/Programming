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

## Summary
| Scenario                  | API / Example                            | Use Case                            | Thread Source         | Async / Parallel | Key Features                                                  |
|---------------------------|------------------------------------------|--------------------------------------|------------------------|------------------|---------------------------------------------------------------|
| Manual Thread             | `new Thread(() => { })`                 | Low-level thread control             | OS Thread              | ❌                | Full control, expensive, manual lifecycle                      |
| ThreadPool                | `ThreadPool.QueueUserWorkItem(...)`     | Short background work                | ThreadPool             | ❌                | No return values, managed by .NET                             |
| Task (simple)             | `Task.Run(() => { })`                   | General-purpose async work           | ThreadPool             | ✅                | High-level, returns `Task`, integrates with async/await       |
| Task (advanced)           | `Task.Factory.StartNew(...)`            | Advanced customization of tasks      | Customizable           | ✅                | Full control over options, scheduler, child tasks             |
| Async/Await               | `await SomeAsyncMethod()`               | I/O-bound async operations           | ThreadPool + state machine | ✅           | Non-blocking, efficient for I/O, async all the way up         |
| Parallel Loop             | `Parallel.For(...)`                     | CPU-bound data parallelism           | ThreadPool             | ✅                | Automatic loop partitioning, great for multi-core CPUs        |
| BackgroundWorker (legacy) | `BackgroundWorker`                      | Legacy UI-safe background work       | ThreadPool             | ✅                | Supports progress & cancel, used in WinForms/WPF              |
| Timer Callback            | `System.Timers.Timer`                   | Periodic lightweight background tasks| ThreadPool             | ❌                | Event-based, not for heavy logic                              |
| Dispatcher (UI)           | `Dispatcher.Invoke(...)`                | UI thread marshalling                | UI Thread              | ❌                | For thread-safe UI access in WPF                              |
| HostedService             | `IHostedService`                        | Long-running background service      | ThreadPool             | ✅                | Lifecycle managed by ASP.NET Core host                        |
| BackgroundService         | `BackgroundService.ExecuteAsync(...)`   | Simplified hosted background service | ThreadPool             | ✅                | Recommended for .NET worker services, integrated cancellation |
                        |
