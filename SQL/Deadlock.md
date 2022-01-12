# Deadlock Definition

A set of processes is deadlocked if each process in the set is waiting for an event that only another process in the set can cause (including itself).

## Waiting for an event could be:

- waiting for access to a critical section
- waiting for a resource Note that it is usually a non-preemptable (resource). pre-emptable resources can be yanked away and given to another. 

It could also be a situation in which two computer programs sharing the same resource are effectively preventing each other from accessing the resource, resulting in both programs ceasing to function.

## Conditions for Deadlock

- Mutual exclusion: resources cannot be shared.
- Hold and wait: processes request resources incrementally, and hold on to what they've got.
- No pre-emption: resources cannot be forcibly taken from processes.
- Circular wait: circular chain of waiting, in which each process is waiting for a resource held by the next process in the chain. 

## Strategies for dealing with Deadlock

- Ignore the problem altogether ie. ostrich algorithm it may occur very infrequently, cost of detection/prevention etc may not be worth it.
- detection and recovery
- avoidance by careful resource allocation
- prevention by structurally negating one of the four necessary conditions. 
