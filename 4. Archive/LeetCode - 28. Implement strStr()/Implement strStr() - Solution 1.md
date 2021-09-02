```
---
aliases:
---
```

Tags:

# Implement strStr() - Solution 1
First if statement to handle edge cases (`needle` being empty string or `haystack == needle`). Then loop through each character in `haystack` and return the start index of slice of `haystack` that equals `needle`. If nothing found, return `-1`.

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if not needle or haystack == needle:
            return 0
        
        for c in range(len(haystack)):
            if haystack[c:c+len(needle)] == needle:
                return c
        return -1
```

## Result
Runtime: 64 ms, faster than 27.40% of Python3 online submissions for Implement strStr().

Memory Usage: 14.5 MB, less than 60.75% of Python3 online submissions for Implement strStr().

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