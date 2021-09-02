```
---
aliases:
---
```

Tags:

# LeetCode Study Plan - Data Structure I
In computer science, a data structure is a way to store and organize data. During the computer programming process, identifying and using the appropriate data structure is an important task as it can improve the overall efficiency of the algorithm. In large-scale systems, choosing the most suitable data structure directly impacts the difficulty of program design and the final quality and performance.

## 217. Contains Duplicate
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

**Input:** nums = \[1,2,3,1\]
**Output:** true

**Example 2:**

**Input:** nums = \[1,2,3,4\]
**Output:** false

**Example 3:**

**Input:** nums = \[1,1,1,3,3,4,3,2,4,2\]
**Output:** true

**Constraints:**

-   `1 <= nums.length <= 105`
-   `-109 <= nums[i] <= 109`

### Solution
One line solution that compares the length of the set of `nums` with the length of `nums`.

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return len(set(nums)) != len(nums)
```

Runtime: 120 ms, faster than 62.45% of Python3 online submissions for Contains Duplicate.

Memory Usage: 19.9 MB, less than 87.10% of Python3 online submissions for Contains Duplicate.
