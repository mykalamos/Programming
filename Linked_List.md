# Linked List
# 🔁 Singly Linked List Reversal — Step-by-Step (3 Nodes)

Initial list: A → B → C → null

| Step | prev | current | next | current.next = prev | Reversed List (so far)        |
|------|------|---------|------|----------------------|-------------------------------|
| 0    | null | A       | B    | A.next = null        | null                          |
| 1    | A    | B       | C    | B.next = A           | A → null                      |
| 2    | B    | C       | null | C.next = B           | B → A → null                  |
| 3    | C    | null    | -    | -                    | C → B → A → null (✅ Done)    |

