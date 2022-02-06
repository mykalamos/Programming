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

- The allocation requests are then satisfied by putting managed objects on these managed heap segments. If the object is less than 85,000 bytes, it is put on the segment for the SOH; otherwise, it is put on an LOH segment. Segments are committed (in smaller chunks) as more and more objects are allocated onto them. For the SOH, objects that survive a GC are promoted to the next generation. Objects that survive a generation 0 collection are now considered generation 1 objects, and so on. However, objects that survive the oldest generation are still considered to be in the oldest generation. In other words, survivors from generation 2 are generation 2 objects; and survivors from the LOH are LOH objects (which are collected with gen2).
