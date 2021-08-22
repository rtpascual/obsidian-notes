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
        prefix = ""
        
        # Split characters in first str in strs
        for i, c in enumerate(list(strs[0])):
            for s in strs[1:]: # Loop through each str in strs, skip first str
                if c == s[i]:
                    prefix = s[0:i]
                else:
                    break
            else:
                continue
            break
        
        return prefix
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