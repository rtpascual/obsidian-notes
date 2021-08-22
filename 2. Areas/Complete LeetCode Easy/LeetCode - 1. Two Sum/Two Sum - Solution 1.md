```
---
aliases:
---
```

Tags: [[For Statements|For Loop]] [[Range Function|Range]] [[Len Function|Len]] [[If Statements|If]]

# Two Sum - Solution 1
Brute force checking each element in `nums` with each other until they add up to `target`.

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        for i in range(0,len(nums)):            
            for j in range(0,len(nums)):
                if (nums[i] + nums[j] == target) and (i!=j):
                    return [i,j]
```

## Result
Runtime: 8056 ms, faster than **5.02%** of Python3 online submissions for Two Sum.

Memory Usage: 14.9 MB, less than **80.98%** of Python3 online submissions for Two Sum.

### Input
```md
nums = [2,7,11,15], target = 9
```

### Output
```md
[0,1]
```