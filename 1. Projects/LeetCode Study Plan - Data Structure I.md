```
---
aliases:
---
```

Tags:

# LeetCode Study Plan - Data Structure I
In computer science, a data structure is a way to store and organize data. During the computer programming process, identifying and using the appropriate data structure is an important task as it can improve the overall efficiency of the algorithm. In large-scale systems, choosing the most suitable data structure directly impacts the difficulty of program design and the final quality and performance.

---

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

---

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
Have two integers `n` and `total` set to the first element of `nums`. Loop through `nums` starting from the second element. Get the max value between the current element of `nums` in the iteration or `n` plus the current element of `nums` then get the max value between `n` or `total`.

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        n = total = nums[0]
        
        for i in nums[1:]:
            n = max(i, n + i)
            total = max(total, n)
        return total
```

Runtime: 64 ms, faster than 76.53% of Python3 online submissions for Maximum Subarray.

Memory Usage: 15 MB, less than 85.56% of Python3 online submissions for Maximum Subarray.

---

## 1. Two Sum
See [[Two Sum]].

---

## 88. Merge Sorted Array
You are given two integer arrays `nums1` and `nums2`, sorted in **non-decreasing order**, and two integers `m` and `n`, representing the number of elements in `nums1` and `nums2` respectively.

**Merge** `nums1` and `nums2` into a single array sorted in **non-decreasing order**.

The final sorted array should not be returned by the function, but instead be _stored inside the array_ `nums1`. To accommodate this, `nums1` has a length of `m + n`, where the first `m` elements denote the elements that should be merged, and the last `n` elements are set to `0` and should be ignored. `nums2` has a length of `n`.

**Example 1:**

**Input:** nums1 = \[1,2,3,0,0,0\], m = 3, nums2 = \[2,5,6\], n = 3
**Output:** \[1,2,2,3,5,6\]
**Explanation:** The arrays we are merging are \[1,2,3\] and \[2,5,6\].
The result of the merge is \[1,2,2,3,5,6\] with the underlined elements coming from nums1.

**Example 2:**

**Input:** nums1 = \[1\], m = 1, nums2 = \[\], n = 0
**Output:** \[1\]
**Explanation:** The arrays we are merging are \[1\] and \[\].
The result of the merge is \[1\].

**Example 3:**

**Input:** nums1 = \[0\], m = 0, nums2 = \[1\], n = 1
**Output:** \[1\]
**Explanation:** The arrays we are merging are \[\] and \[1\].
The result of the merge is \[1\].
Note that because m = 0, there are no elements in nums1. The 0 is only there to ensure the merge result can fit in nums1.

**Constraints:**

-   `nums1.length == m + n`
-   `nums2.length == n`
-   `0 <= m, n <= 200`
-   `1 <= m + n <= 200`
-   `-109 <= nums1[i], nums2[j] <= 109`

**Follow up:** Can you come up with an algorithm that runs in `O(m + n)` time?

### Solution
First we only perform any logic if `nums2` has length > 0. Then loop through starting from `nums1[m]` and insert elements from `nums2`. Finish the solution by using sort on `nums1`.

```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        if n != 0:
            index = 0

            for i in range(m,len(nums1)):
                nums1[i] = nums2[index]
                index += 1

            nums1.sort()
```

Runtime: 36 ms, faster than 72.99% of Python3 online submissions for Merge Sorted Array.

Memory Usage: 14.2 MB, less than 62.41% of Python3 online submissions for Merge Sorted Array.

## 350. Intersection of Two Arrays II
Given two integer arrays `nums1` and `nums2`, return _an array of their intersection_. Each element in the result must appear as many times as it shows in both arrays and you may return the result in **any order**.

**Example 1:**

**Input:** nums1 = \[1,2,2,1\], nums2 = \[2,2\]
**Output:** \[2,2\]

**Example 2:**

**Input:** nums1 = \[4,9,5\], nums2 = \[9,4,9,8,4\]
**Output:** \[4,9\]
**Explanation:** \[9,4\] is also accepted.

**Constraints:**

-   `1 <= nums1.length, nums2.length <= 1000`
-   `0 <= nums1[i], nums2[i] <= 1000`

**Follow up:**

-   What if the given array is already sorted? How would you optimize your algorithm?
-   What if `nums1`'s size is small compared to `nums2`'s size? Which algorithm is better?
-   What if elements of `nums2` are stored on disk, and the memory is limited such that you cannot load all elements into the memory at once?

### Solution
Sort both `nums1` and `nums2` and initialize two pointers `i` and `j` along with list `intersection` to store what would be returned. Use a while loop and go compare both input lists using `i` and `j` as indexes and increment the index of the list that is lesser. Otherwise, both elements are equal and so the value is stored in `intersection`.

```python
class Solution:
    def intersect(self, nums1: List[int], nums2: List[int]) -> List[int]:
        nums1.sort()
        nums2.sort()
        
        i, j, intersection = 0, 0, []
        
        while i < len(nums1) and j < len(nums2):
            if nums1[i] < nums2[j]:
                i += 1
            elif nums1[i] > nums2[j]:
                j += 1
            else:
                intersection.append(nums1[i])
                i += 1
                j += 1
        
        return intersection
```

Runtime: 44 ms, faster than 85.33% of Python3 online submissions for Intersection of Two Arrays II.

Memory Usage: 14.2 MB, less than 90.03% of Python3 online submissions for Intersection of Two Arrays II.

## 121. Best Time to Buy and Sell Stock
You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return `0`.

**Example 1:**

**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

**Example 2:**

**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transactions are done and the max profit = 0.

**Constraints:**

-   `1 <= prices.length <= 105`
-   `0 <= prices[i] <= 104`

### Solution
Pretty straightforward solution. Check for edge case of `prices` having length of 1, then set `low` to `prices[0]` then loop through `prices` starting from index 1 to set new `low` and `high` values and return `high` afterwards.

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        if len(prices) < 2:
            return 0
        
        low, high = prices[0], 0
        
        for price in prices[1:]:
            if price < low:
                low = price
            elif price - low > high:
                high = price - low
        
        return high
```

Runtime: 988 ms, faster than 77.31% of Python3 online submissions for Best Time to Buy and Sell Stock.

Memory Usage: 25 MB, less than 95.56% of Python3 online submissions for Best Time to Buy and Sell Stock.

## 566. Reshape the Matrix
In MATLAB, there is a handy function called `reshape` which can reshape an `m x n` matrix into a new one with a different size `r x c` keeping its original data.

You are given an `m x n` matrix `mat` and two integers `r` and `c` representing the number of rows and the number of columns of the wanted reshaped matrix.

The reshaped matrix should be filled with all the elements of the original matrix in the same row-traversing order as they were.

If the `reshape` operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/04/24/reshape1-grid.jpg)

**Input:** mat = \[\[1,2\],\[3,4\]\], r = 1, c = 4
**Output:** \[\[1,2,3,4\]\]

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/04/24/reshape2-grid.jpg)

**Input:** mat = \[\[1,2\],\[3,4\]\], r = 2, c = 4
**Output:** \[\[1,2\],\[3,4\]\]

**Constraints:**

-   `m == mat.length`
-   `n == mat[i].length`
-   `1 <= m, n <= 100`
-   `-1000 <= mat[i][j] <= 1000`
-   `1 <= r, c <= 300`