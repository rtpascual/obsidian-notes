```
---
aliases:
---
```

Tags: 

# Longest Common Prefix - Solution 1
Made use of `zip` function to unzip `strs` then enumerate to get index. Loop through each character of `str` in `strs`.

- case 1: 

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if not len(strs):
            return ''
        
        i = 0
        
        for i, c in enumerate(zip(*strs),1):
            if len(set(c)) != 1:
                i -= 1
                break
        
        return strs[0][:i]
```

## Result
Runtime and memory stats.

### Input
```md
Inputs for solution
```

### Output
```md
Outputs for solution
```