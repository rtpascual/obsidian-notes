```
---
aliases:
---
```

Tags:

# Merge Two Sorted Lists - Solution 1
Checked if both lists have something, then set `l1` to be the lowest of the two values and recursively call the function again for the next value. At the end return `l1` or `l2` in case `l1` has nothing.

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        if l1 and l2:
            if l1.val > l2.val:
                l1, l2 = l2, l1
            l1.next = self.mergeTwoLists(l1.next,l2)
        return l1 or l2
```

## Result
Runtime: 40 ms, faster than 49.43% of Python3 online submissions for Merge Two Sorted Lists.

Memory Usage: 14.1 MB, less than 96.11% of Python3 online submissions for Merge Two Sorted Lists.

### Input
```md
[1,2,4]  
[1,3,4]

[]  
[]

[]  
[0]
```

### Output
```md
[1,1,2,3,4,4]

[]

[0]
```