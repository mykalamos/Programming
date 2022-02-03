# Interlocked
https://devblogs.microsoft.com/oldnewthing/20130913-00/?p=3243
http://www.albahari.com/threading/part4.aspx#_Interlocked

- Non-blocking atomic operations
- A statement is intrinsically atomic if it executes as a single indivisible instruction on the underlying processor.
- Strict atomicity precludes any possibility of preemption
- Statements that combine more than one read/write operation are never atomic
