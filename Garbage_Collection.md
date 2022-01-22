CLR - automatic memory management
----------------------------------

Problem
-------
- Forgetting to free up memory
- Trying to access memory after it has been freed

- Only the garbage collector deallocates memory. Simpler for the developer.

Solution
--------
- Garbage Collector
- Developer does not have to free memory
- Efficient allocation on heap
- Memory reclamation
- Memory safety - objects cant access allocation of anoher object

Virtual Memory
--------------
- Each process has own virtual address space
- 3 states
  - Free
  - Reserved
  - Committed - assigned to physical storage

Managed heap
------------
- When a process is initialized, the runtime reserves a contiguous region of
unallocated address space - the managed heap.
- The heap also maintains a pointer which indicates where the next object is
to be allocated.
- Initially set to the base address of the heap.
- Memory allocated contiguously.

Roots
-----
- e.g. Globals, Statics, Locals, CPU Registers, Finalize queue
- Object graph constructed.
- Heap traversed linearly looking for contiguous blocks of collectable
objects.
- Memory shifted using memcpy. Roots need to be rewired following compaction.
- Compaction only occurs if significant unreachable objects found

Large Object Heap
-----------------
- Performance optimisation
- Usually not compacted for efficiency

Managed Heap
------------
- Divided into 3 generations 0,1 (Ephemeral) and ,2.
- Assumptions
  1. Faster to compact memory for a part of the heap rather than the whole
  2. Newer objects tend to have following:
    1. Shorter lifetimes than older ones
    2. Related to each other and accessed at around the same time
- GC tends to run when Gen0 is full.
- Surviving objects are promoted to Gen1 and 2.

Background garbage collection
-----------------------------
- Replaces concurrent gc from net4 
- From net45 background gc available on server and workstation
- Foreground gc = 0,1. All threads suspended
- Background does not suspend all threads

Finalization
-------------
- For resources that wrap unmanaged resources e.g. file, mutex
- Finalizable objects and their graphs get promoted to older generations.
- Allocation takes longer as pointers get put on finalization list/queue.
- During a GC reclaimable object have the references removed from
finalization list and placed on freachable queue.
- Dedicated special high-priority CLR thread calls finalize (avoid thread
synchronisation issues).
- Assumptions about the current thread should therefore be avoided in
finalize methods.
- Freachable queue considered a root so objects can't be reclaimed. After
finalizers on queue have been executed subsequent sweeps can reclaim the
memory.

What causes Finalize methods to be called
------------------------------------------
1. Generation 0 is full
2. ```System.GC.Collect()``` called explicitly
3. CLR unloading AppDomain - nothing therein considered a root
4. CLR shuts down

Dispose pattern
---------------
- Any type defining a Finalize should implement the Dispose pattern.
- Dispose would call GC.SupressFinalize(this);
- If disposing is occuring it is safe to access managed resources and their
finalisers will not have been called.

Weak references
---------------
- GC has two special structures: long and short(doesn't track resurrection)
weak reference tables.
