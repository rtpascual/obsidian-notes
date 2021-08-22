```
---
aliases:
---
```

Tags:

# Palindrome Number - Solution 1
All negative integers are not palindromes so return `False` right away. Convert integer to `string` and compare with reverse using String Slice.

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        
        return str(x) == str(x)[::-1]
```

## Result
Runtime: 75 ms, faster than **22.38%** of Python3 online submissions for Palindrome Number.

Memory Usage: 14.2 MB, less than **77.57%** of Python3 online submissions for Palindrome Number.

### Input
```md
121  
-121  
10  
-101
```

### Output
```md
true  
false  
false  
false
```