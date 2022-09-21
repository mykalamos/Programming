# CLR - automatic memory management

## Problem
- Forgetting to free up memory
- Trying to access memory after it has been freed
- Only the garbage collector deallocates memory. Simpler for the developer.

## Solution
- Garbage Collector
- Developer does not have to free memory
- Efficient allocation on heap
- Memory reclamation
- Memory safety - objects cant access allocation of another object

## Virtual Memory
- Each process has own virtual address space
- 3 states
  - Free
  - Reserved
  - Committed - assigned to physical storage

## Managed heap
- When a process is initialized, the runtime reserves a contiguous region of
unallocated address space - the managed heap.
- The heap also maintains a pointer which indicates where the next object is
to be allocated.
- Initially set to the base address of the heap.
- Memory allocated contiguously.

## Roots
- e.g. Globals, Statics, Locals, CPU Registers, Finalize queue
- Object graph constructed.
- Heap traversed linearly looking for contiguous blocks of collectable
objects.
- Memory shifted using memcpy. Roots need to be rewired following compaction.
- Compaction only occurs if significant unreachable objects found

## Large Object Heap
- Performance optimisation
- Usually not compacted for efficiency
  - 85000 bytes deemed cut-off point

## Managed Heap
- Divided into 3 generations 0,1 (Ephemeral) and ,2.
- Assumptions
  1. Faster to compact memory for a part of the heap rather than the whole
  2. Newer objects tend to
    - Have shorter lifetimes than older ones
    - Be related to each other and accessed at around the same time
- GC tends to run when Gen0 is full.
- Surviving objects are promoted to Gen1 and 2.

## Background garbage collection
- Replaces concurrent gc from net4 
- From net45 background gc available on server and workstation
- Foreground gc = 0,1. All threads suspended
- Background does not suspend all threads

## Finalization
- For resources that wrap unmanaged resources e.g. file, mutex
- Finalizable objects and their graphs get promoted to older generations.
- Allocation takes longer as pointers get put on finalization list/queue.
- During a GC, reclaimable objects moved from finalization list ➡️ freachable queue.
- Dedicated special high-priority CLR thread calls ```Finalize```
  - Avoids thread synchronisation issues
  - So avoid assumptions about the current thread in ```Finalize``` methods
- Freachable queue considered a root so objects can't be reclaimed.
- After finalizers on queue have been executed subsequent sweeps can reclaim the memory.

## What causes Finalize methods to be called
1. Generation 0 is full
2. ```System.GC.Collect()``` called explicitly
3. CLR unloading AppDomain - nothing therein considered a root
4. CLR shuts down

## Dispose pattern
- Any type defining a Finalize should implement the Dispose pattern.
- Dispose would call ```GC.SupressFinalize(this)```
- If disposing is occuring it is safe to access managed resources and their
finalisers will not have been called.

## Weak references
- GC has two special structures: long and short(doesn't track resurrection)
weak reference tables.

## Reference Counting
- Advantage: Objects can be claimed as as soon
- 'Smart pointers'  in C/C++ => ctor/dtor/assignment ops manage the references
