# Signaling

http://www.albahari.com/threading/part2.aspx#_Signaling_with_Event_Wait_Handles

## Event Handles
- Signaling is when one thread waits until its is notified by another
  - AutoResetEvent - ``` WaitOne()``` blocks until ```Set()``` is called
  - ManualResetEvent - ```Reset()``` must be called to put handle into non-signalled mode.
  - CountdownEvent - ```Wait()``` blocks until ```Signal()``` as been called ```n``` times.
