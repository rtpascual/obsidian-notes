```
---
aliases:
---
```

Tags: 

# Longest Common Prefix - Solution 1
Made use of `zip` function to unzip `strs` then enumerate to get index. Loop through each character of `str` in `strs`.

```python
strs = ["flower", "flow", "flight"]

x = zip(*strs)

print(tuple(x))
>>> (('f', 'f', 'f'), ('l', 'l', 'l'), ('o', 'o', 'i'), ('w', 'w', 'g'))

x = enumerate(zip(*strs),1)

print(tuple(x))
>>> ((1, ('f', 'f', 'f')), (2, ('l', 'l', 'l')), (3, ('o', 'o', 'i')), (4, ('w', 'w', 'g')))
```

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
		# Return empty string if there are no items in strs
        if not len(strs):
            return ''
			
        # Initialize integer to capture index for return string
        i = 0
        
		# Loop through each set of characters at index = i for each str in strs
        for i, c in enumerate(zip(*strs),1):
			# Make characters into a set, which should have length = 1 if all characters match
            if len(set(c)) != 1:
				# Characters do not match, move back 1 for index and break out of loop
                i -= 1
                break
        
		# Return string from first str, first i characters
        return strs[0][:i]
```

## Result
Runtime: 32 ms, faster than 79.63% of Python3 online submissions for Longest Common Prefix.

Memory Usage: 14.2 MB, less than 82.24% of Python3 online submissions for Longest Common Prefix.

### Input
```md
["flower","flow","flight"]  
["dog","racecar","car"]
```

### Output
```md
"fl"  
""
```