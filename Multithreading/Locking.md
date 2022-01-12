# Locking
http://www.albahari.com/threading/part2.aspx#_Locking

## Exclusive
- Only one thread can enter a section of code at a time
  - Lock ``` Monitor.Enter(ref locktaken) ... if(lockTaken) Monitor.Exit ```
  - Mutex - Cross process synchronisation
## Non-Exclusive
  - Semaphore/Slim - Enforces a certain number of threads can access. Other are blocked until appropriate number of calls to ```Release()``` are made.
  - ReaderWriterLock/Slim - Multiple readers but a single writer

Lock around shared writable fields

## Thread-safety
- No indeterminacy in the face of any multithreading scenario. Achieved by 
  - Locking
  - Reducing the possibilities for thread interaction.
- Re-entrant
  - Can be preempted part way through its execution, and then called again on another thread without ill effect.




