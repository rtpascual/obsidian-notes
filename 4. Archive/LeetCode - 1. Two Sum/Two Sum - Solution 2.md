```
---
aliases:
---
```

Tags: [[For Statements|For Loop]], [[Enumerate Function]], [[Hash Map]], [[If Statements|If]]

# Two Sum - Solution 2
Different solution using a [[Hash Map|hash map]] to iterate through `nums` once.

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        
        for i, value in enumerate(nums):
            remaining = target - nums[i]
            
            if remaining in hashmap:
                return [i, hashmap[remaining]]
            else:
                hashmap[value] = i
```

## Result
Runtime: 56 ms, faster than 88.25% of Python3 online submissions for Two Sum.

Memory Usage: 15.2 MB, less than 54.17% of Python3 online submissions for Two Sum.

### Input
```md
nums = [2,7,11,15], target = 9
```

### Output
```md
[0,1]
```