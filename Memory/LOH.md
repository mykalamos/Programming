# Large Object Heap
https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/large-object-heap

- GC divides objects up into
  - Small
  - Large
- Compacting can be expensive
  - Large objects allocated on LOH.

## How objects get to LOH
- >= to 85,000 bytes
  - Threshold determined by performance tuning

- GC is a generational collector
- 3 generations: (0, 1, 2)
- Most objects die in gen0
- gen1 acts as a buffer between young object areas and long-lived object areas.

- Newly allocated objects form a new generation of objects and are implicitly generation 0 collections.
- Unles they are Large (gen3 collected as part of gen2).

- Full GC = Gen 2
- GenX collection - All gens <= x

- Generations = logical view of the GC heap
- Objects live in _managed heap segments_
  - Chunk of memory that the GC reserves from the OS by calling ```VirtualAlloc```
- When the CLR is loaded, the GC allocates two initial heap segments
  1. Small objects (SOH)
  2. LOH

- Segments are committed (in smaller chunks) as more and more objects are allocated onto them.
- For the SOH, objects that survive a GC are promoted to the next generation

- User code can only allocate in gen0 or the LOH.
- GC 'allocates' to higher gens

- During a GC, the GC traces through the live objects and compacts them.
- Due to compaction cost, the GC sweeps the LOH
- Makes a free list out of dead objects that can be reused later to satisfy large object allocation requests
- Adjacent dead objects are made into one free object.

- From net 4.5.1 ```GCSettings.LargeObjectHeapCompactionMode``` property
  - Specify that the LOH should be compacted during the next full blocking GC.
  - In future, .NET may decide to compact the LOH automatically
  - Pinning

- If no space for LOH requests, the GC
  - Acquire more segments from the OS
  - gen2 GC

- During a gen1/2 GC, the GC releases segments that have no live objects on them back to the OS by calling ```VirtualFree```.
- Space after the last live object to the end of the segment is decommitted
  - Not on ephemeral segment (gen0/gen1)
  - GC keeps committed memory because your application will be allocating in it right away). 
  - Free spaces remain committed though they are reset, meaning that the OS doesn't need to write data in them back to disk.
- If it needs to use the decommitted space at the end of the segment to satisfy large object allocation requests, it commits the memory again. (For an explanation of commit/decommit, see the documentation for VirtualAlloc.

## When LOH GC occurs
- Allocation exceeds the generation 0 or large object threshold
  - These thresholds are dynamically tuned as the program runs.
- The GC.Collect method is called
- The system is in low memory situation.
  - If GC thinks that doing a gen2 GC will be productive, it triggers one.

## LOH performance implications

### Allocation cost
- CLR guarantees memory for every new object it gives out is _cleared_
- Unless triggers a GC, allocation cost of a large object is dominated by clearing 
- If it takes two cycles to clear one byte, it takes 170,000 cycles to clear the smallest large object.
- Clearing the memory of a 16-MB object on a 2-GHz machine takes approximately 16 ms. That's a rather large cost.

### Collection cost
- The LOH and gen2 are collected together, if either one's threshold is exceeded
- If gen2 is large, it can cause performance problems if many gen2 GCs are triggered
- If many large objects are allocated on a temporary basis and you have a large SOH, you could be spending too much time doing GCs.

### Array elements with reference types
- Very large objects on the LOH are usually arrays (it's very rare to have an instance object that's really large)
- If the elements of an array are reference-rich, it incurs a cost that is not present if the elements are not reference-rich.
- If the element doesn't contain any references, the garbage collector doesn't need to go through the array at all.

- Allocate a pool of large objects that you reuse instead of allocating temporary ones

TBC
