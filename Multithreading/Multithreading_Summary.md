
# What is a Thread
- An independent path/unit of execution.

# Multithreading
- Ability of an operations to execute different parts of programs (threads) simultaneously on same processor.

# Uses
- UI Responsiveness
- Efficient use of CPU when blocking occurs
- Parallel computing - cpu intensive calculations
- Speculative execution
- Simultaneous request processing

# Multitasking
- Execution of multiple tasks simultaneously (as opposed to multithreading)

## ReaderWriter Locks
- System.Threading.ReaderWriterLock support a single writer and many
readers.

## Avoiding deadlocks
- Less lock granularity.
- Access resources in the same order.

## Asnychronous calls
------------------
1. Create a delegate with the same signature as method to call e.g. private
delegate void AutomationDelegate();
2. Create AsyncCallback passing name of callback into constructor.
3. Create instance of delegate passing in name of method to call.
4. invoke with delgate.BeginInvoke(callback, null);

## Multi-threading example
-----------------------
- new Thread( new ThreadStart(this.function));
- thread.Start(); thread.IsAlive();

## Thread.Sleep
- Immediate reliquishing of time slice
- Thread.Yield - only to other threads on same processor
- Pre-empting is when execution is interrupted externally i.e. by time slicing

# Difference between thread and process?
| Process | Thread |
| --- | --- |
| Virtual memory space | Code that is to be serially executed within a process|
| Code | Threads executing the same block of code maintain separate stacks. Invocations are kept separate|
| Data | Each thread in a process shares that process?s global variables andresources|
| System resources | A processor executes threads, not processes|
| Primary thread | |

