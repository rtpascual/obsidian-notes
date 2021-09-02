```
---
aliases:
---
```

Tags:

# Remove Element - Solution 1
Initialize `k` as a pointer to keep track of the index where the first `k` elements that do not match `val` will go. Loop through the length of `nums` and place `k` elements to the front of `nums` then increment `k`.

```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        k = 0
        
        for i in range(len(nums)):
            if nums[i] != val:
                nums[k] = nums[i]
                k += 1
        return k
```

## Result
Runtime: 31 ms, faster than 76.74% of Python3 online submissions for Remove Element.

Memory Usage: 14.2 MB, less than 77.00% of Python3 online submissions for Remove Element.

### Input
```md
[3,2,2,3]  
3  

[0,1,2,2,3,0,4,2]  
2
```

### Output
```md
[2,2]  

[0,1,3,0,4]
```