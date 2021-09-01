```
---
aliases:
---
```

Tags:

# Remove Duplicates from Sorted Array - Solution 1
First check for if `nums` has anything, if not return 0. Loop through the length of `nums` while keeping track of index of new `nums` with unique values.

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        if not nums:
            return 0
        
        end = 0
        for n in range(1,len(nums)):
            if nums[n] != nums[end]:
                end += 1
                nums[end] = nums[n]
        return end + 1
```

## Result
Runtime: 80 ms, faster than 92.17% of Python3 online submissions for Remove Duplicates from Sorted Array.

Memory Usage: 15.7 MB, less than 46.28% of Python3 online submissions for Remove Duplicates from Sorted Array.

### Input
```md
[1,1,2]  
[0,0,1,1,1,2,2,3,3,4]
```

### Output
```md
[1,2]  
[0,1,2,3,4]
```