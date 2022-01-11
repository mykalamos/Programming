- Ability of an operations to execute different parts of programs (threads) simultaneously on same processor.

# Multitasking
- Execution of multiple tasks simultaneously (as opposed to multithreading)

What is a Thread ?
- An independent unit of execution.

Did VB6 support multi-threading ? - No
Can we have multiple threads in one App domain ? - Yes
Which namespace has threading ? - System.Threading
Can you explain in brief how can we implement threading ?
How can we change priority and what the levels of priority are provided by
.NET ?
How can you reference current thread of the method ?
What's Thread.Sleep() in threading ?
How can we make a thread sleep for infinite period ?
What is Suspend and Resume in Threading ?
What the way to stop a long running thread ?
How do i debug thread ?

What's Thread.Join() in threading ?
- Blocks the calling thread until a thread terminates

What are Daemon thread's and how can a thread be created as Daemon?
When working with shared data in threading how do you implement
synchronization ?
Can we use events with threading ?
How can we know a state of a thread?
what is a monitor object?
what are wait handles ?(Twist :- What is a mutex object ?)
what is ManualResetEvent and AutoResetEvent ?

What is ReaderWriter Locks ?
- System.Threading.ReaderWriterLock support a single writer and many
readers.

How can you avoid deadlock in threading ?
- Less lock granularity.
- Access resources in the same order.

Asnychronous calls
------------------
1. Create a delegate with the same signature as method to call e.g. private
delegate void AutomationDelegate();
2. Create AsyncCallback passing name of callback into constructor.
3. Create instance of delegate passing in name of method to call.
4. invoke with delgate.BeginInvoke(callback, null);

Multi-threading
---------------
- new Thread( new ThreadStart(this.function));
- thread.Start(); thread.IsAlive();

What’s difference between thread and process?
Process
- virtual memory space
- code
- data
- system resources.
- primary thread

Thread
- Code that is to be serially executed within a process.
- A processor executes threads, not processes
- Threads executing the same block of code maintain separate stacks -
invocations are kept separate.
- Each thread in a process shares that process?s global variables and
resources.
