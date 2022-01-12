# Locking
http://www.albahari.com/threading/part2.aspx#_Locking

## Exclusive
- Only one thread can enter a section of code at a time
  - Lock ``` Monitor.Enter(ref locktaken) ... if(lockTaken) Monitor.Exit ```
  - Mutex
## Non-Exclusive
  - Semaphore/Slim - Enforces a certain number of threads can access. Other are blocked until appropriate number of calls to ```Release()``` are made.
  - ReaderWriterLock/Slim

Lock around shared writable fields




