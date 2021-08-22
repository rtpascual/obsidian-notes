```
---
aliases:
---
```

Tags:

# Reverse Integer - Solution 1
Turned the signed integer into a string, strip leading 0s, and reverse the string then convert back to an integer. Check if `output` is within bounds or return 0. If `x` was negative, multiply `output` with -1.

```python
class Solution:
    def reverse(self, x: int) -> int:
        rev = str(abs(x)) # Convert signed int to unsigned int then string
        rev = rev.strip() # Strip leading 0s
        rev = rev[::-1] # Reverse string
        output = int(rev) # Convert string back to int
        
        if output >= 2** 31 -1 or output <= -2** 31:
            return 0
        elif x < 0:
            return output * -1
        else:
            return output
```

## Result
Runtime: 32 ms, faster than **68.30%** of Python3 online submissions for Reverse Integer.

Memory Usage: 14 MB, less than **91.13%** of Python3 online submissions for Reverse Integer.

### Input
```md
123  
-123  
120  
0
```

### Output
```md
321  
-321  
21  
0
```