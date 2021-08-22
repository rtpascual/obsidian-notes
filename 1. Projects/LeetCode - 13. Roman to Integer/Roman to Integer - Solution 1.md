```
---
aliases:
---
```

Tags:

# Roman to Integer - Solution 1
Used dictionary to store the key-value pairs of roman numerals then looped through each character of the input string in reverse. If the previous roman numeral has a higher value than the current, subtract, else add.

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        roman = {
            "I":1,
            "V":5,
            "X":10,
            "L":50,
            "C":100,
            "D":500,
            "M":1000
        }
        
        num = prev = 0
        
        for i in s[::-1]:
            if prev > roman[i]:
                num -= roman[i]
            else:
                num += roman[i]
            prev = roman[i]
        
        return num
```

## Result
Runtime: 48 ms, faster than 63.38% of Python3 online submissions for Roman to Integer.

Memory Usage: 14.4 MB, less than 27.49% of Python3 online submissions for Roman to Integer.

### Input
```md
"III"  
"IV"  
"IX"  
"LVIII"  
"MCMXCIV"
```

### Output
```md
3  
4  
9  
58  
1994
```