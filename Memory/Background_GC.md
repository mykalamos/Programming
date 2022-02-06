# Background GC
https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/background-gc

- In background garbage collection (bGC), ephemeral gens (0, 1) are collected as needed while gen2 GC is in progress
- bGC is performed on one or more dedicated threads
  - depending on whether it's workstation or server GC
- applies only to gen2 GC

- bGC = default
- ```gcConcurrent``` configuration setting in .NET Framework apps
- ```System.GC.Concurrent``` setting in .NET Core+

- GC of ephemeral gens (eGC) during bGC = foreground garbage collection (fGC)
- When fGC occurs, *all* managed threads are suspended.

- When bGC and gen0 full, the CLR performs ephmeral fGC.
- The dedicated bGC thread checks at frequent safe points to determine whether there is a request for fGC.
- If there is, the bGC suspends itself so that foreground garbage collection can occur
- After the fGC is completed, the dedicated bGC threads and user threads resume

- bGC removes allocation restrictions imposed by concurrent garbage collection
- eGC can occur during background garbage collection
- bGC can remove dead objects in ephemeral generations
- Can expand the heap if needed during a gen1 GC

## Background workstation vs. server GC

- net45
- bGC for server GC
- bGC = default mode for server GC (sGC).

- bwGC
  - one dedicated background garbage collection thread
- bsGC
  -  multiple threads
  -  Typically, one per for each logical processor
  -  GC threads do not time out

## Concurrent garbage collection
- Enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection
- This option affects only garbage collections in generation 2
- ephemeral gens are always non-concurrent because they finish fast.

- cGC enables interactive applications to be more responsive by minimizing pauses for a collection
- Managed threads can continue to run most of the time while the concurrent garbage collection thread is running
- Shorter pauses while a garbage collection is occurring.

- cGC is performed on a dedicated thread
- By default, the CLR runs wGC with concurrent garbage collection enabled

