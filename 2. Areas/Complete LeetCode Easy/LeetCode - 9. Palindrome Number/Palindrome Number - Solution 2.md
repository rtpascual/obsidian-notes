```
---
aliases:
---
```

Tags:

# Palindrome Number - Solution 2
Follow up on the question was to solve without converting the `integer` to `string`.

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0 or (x > 0 and x % 10 == 0):
            return False
        
        reverse = 0
        while x > reverse:
            reverse = reverse * 10 + x % 10
            x = x // 10
        return True if (x == reverse or x == reverse // 10) else False
```

## Result
Runtime: 52 ms, faster than 88.99% of Python3 online submissions for Palindrome Number.

Memory Usage: 14 MB, less than 92.68% of Python3 online submissions for Palindrome Number.

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