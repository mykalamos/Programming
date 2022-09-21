- https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1?view=net-6.0
- https://en.wikipedia.org/wiki/Linked_list
```
 - A linear collection of data elements whose order is not given by their physical placement in memory.
 - Instead, each element points to the next.
 - Access time is linear
```
## Reverse
- https://www.geeksforgeeks.org/reverse-a-linked-list/
Initialize three pointers
- prev as NULL
- curr as head
- next as NULL
```
while($current != NULL) {
 $next = $current->next;
 $current->next = prev; // rewire here
 $prev = $current;
 $current = $next;
}
```

## Recursion
TODO
