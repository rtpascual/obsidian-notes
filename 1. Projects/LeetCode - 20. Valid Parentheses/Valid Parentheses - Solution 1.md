```
---
aliases:
---
```

Tags:

# Valid Parentheses - Solution 1
Quickly returns `False` if length of `s` is less than 2. Initialize two lists for open and close parentheses that are matched by index. For each loop through each character in `s`:

1. Add open parentheses to `stack`
2. Return `False` if first character in `s` is closing parenthesis.
3. Check if closing parentheses matches open parentheses index, then `pop` open parentheses out of `stack`

Then after loop is done, length of `stack` should be 0 if all parentheses is valid.

```python
class Solution:
    def isValid(self, s: str) -> bool:
        if len(s) < 2: return False
        
        open = ['(','[','{']
        close = [')',']','}']

        stack = []

        for c in s:
            if c in open:
                stack.append(c)
            else:
                if len(stack) != 0 and stack[-1] == open[close.index(c)]:
                    stack.pop()
                else:
                    return False
        return len(stack) == 0
```

## Result
Runtime: 28 ms, faster than 84.44% of Python3 online submissions for Valid Parentheses.

Memory Usage: 14.1 MB, less than 87.01% of Python3 online submissions for Valid Parentheses.

### Input
```md
"()"  
"()[]{}"  
"(]"  
"([)]"  
"{[]}"
```

### Output
```md
true  
true  
false  
false  
true
```