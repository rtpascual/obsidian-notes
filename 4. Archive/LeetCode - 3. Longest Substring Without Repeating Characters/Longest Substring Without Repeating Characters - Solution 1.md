```
---
aliases:
---
```

Tags:

# Longest Substring Without Repeating Characters - Solution 1
Loop through `s`, storing each character and where it is in `s` using a hash map. Update `start` if the character, `c`, is already in `usedchar` and the position is less than or equal to the character that already exists in `usedchar`. Else `c` is a new character and `maxlength` is updated on whichever is higher, `maxlength` or the current position in the string from `start + 1`.

`start` is not included in the window of the longest substring of characters which is why `start <= usedchar[c]` and `i - start + 1` are used.

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        usedchar = {}
        start = maxlength = 0
        
        for i, c in enumerate(s):
            if c in usedchar and start <= usedchar[c]:
                start = usedchar[c] + 1
            else:
                maxlength = max(maxlength, i - start + 1)
            
            usedchar[c] = i
        
        return maxlength
```

## Result
Runtime: 52 ms, faster than 93.30% of Python3 online submissions for Longest Substring Without Repeating Characters.

Memory Usage: 14.2 MB, less than 93.03% of Python3 online submissions for Longest Substring Without Repeating Characters.

### Input
```md
"abcabcbb"  
"bbbbb"  
"pwwkew"  
""
```

### Output
```md
3  
1  
3  
0
```