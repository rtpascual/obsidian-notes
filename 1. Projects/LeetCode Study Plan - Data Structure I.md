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

## 53. Maximum Subarray
Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return _its sum_.

A **subarray** is a **contiguous** part of an array.

**Example 1:**

**Input:** nums = \[-2,1,-3,4,-1,2,1,-5,4\]
**Output:** 6
**Explanation:** \[4,-1,2,1\] has the largest sum = 6.

**Example 2:**

**Input:** nums = \[1\]
**Output:** 1

**Example 3:**

**Input:** nums = \[5,4,-1,7,8\]
**Output:** 23

**Constraints:**

-   `1 <= nums.length <= 3 * 104`
-   `-105 <= nums[i] <= 105`

**Follow up:** If you have figured out the `O(n)` solution, try coding another solution using the **divide and conquer** approach, which is more subtle.

### Solution


```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        n = total = nums[0]
        
        for i in nums[1:]:
            n = max(i, n + i)
            total = max(total, n)
        return total
```
