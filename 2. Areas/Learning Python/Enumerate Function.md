```
---
aliases:
---
```

Tags:

# Enumerate Function
## `enumerate(iterable, start=0)`
Built-in function for python. Returns an enumerable object.
_iterable_ must be a sequence, an iterator, or an object that supports iteration.
By default, _start = 0_.

### Example
```python
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons)) # Output 1
list(enumerate(seasons, start=1)) # Output 2
```

### Output
```md
Output 1
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

Output 2
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```
