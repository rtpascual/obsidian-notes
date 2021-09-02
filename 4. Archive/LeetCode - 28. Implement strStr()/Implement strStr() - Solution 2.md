```
---
aliases:
---
```

Tags:

# Implement strStr() - Solution 2
Simpler solution than [[Implement strStr() - Solution 1|Solution 1]]. Check for edge cases first then use split and get length of first element of split to get the first occurrence of `needle` in `haystack`.

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if not needle:
            return 0
        elif needle not in haystack:
            return -1
        else:
            return len(haystack.split(needle)[0])
```

## Result
Runtime: 28 ms, faster than 92.78% of Python3 online submissions for Implement strStr().

Memory Usage: 14.6 MB, less than 32.63% of Python3 online submissions for Implement strStr().

### Input
```md
"hello"  
"ll"  

"aaaaa"  
"bba"  

""  
""
```

### Output
```md
2  

-1  

0
```