```
---
aliases:
---
```

Tags:

# Longest Common Prefix - Solution 1
Compared each character across every `str` in `strs`, if it matches the character in the same index of first `str` then set `prefix`. Break out of loops as soon as there is no match.

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