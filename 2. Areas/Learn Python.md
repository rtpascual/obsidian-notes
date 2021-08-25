```
---
aliases:
---
```

Tags:

# Learn Python
Notes of what I have learned about Python while working LeetCode questions and side projects.

## Enumerate Function
### `enumerate(iterable, start=0)`
Built-in function for python. Returns an enumerable object.
_iterable_ must be a sequence, an iterator, or an object that supports iteration.
By default, _start = 0_.

#### Example
```python
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons)) # Output 1
list(enumerate(seasons, start=1)) # Output 2
```

#### Output
```md
Output 1
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

Output 2
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```

## for Statements
Works similar to `foreach` in C#.

#### Example
```python
# Measure some strings:
words = ['cat', 'window', 'defenestrate']

for w in words:
	print(w, len(w))
```

#### Output
```md
cat 3
window 6
defenstrate 12
```

### Multiple parameters
`for` statement can also have multiple parameters.

#### Example with items and it's index
```python
array = ['hello', 'world']

for index, element in enumerate(array):
	print(f'Element {element} is in index {index}')
```

#### Output
```md
Element hello is in index 0
Element world is in index 1
```

#### Example with two-dimensional array
```python
2dArray = [(0,1), ('a','b')]

for i, j in 2dArray:
	print(f'i: {i} j: {j}')
```

#### Output
```md
i: 0 j: 1
i: a j: b
```

## If Statements
Unlike in C#, there is no use of parenthesis and can be added for more readability for multiple conditions.

#### Example
```python
# Return value if equal to 2
if value == 2:
	return value
```

#### Example multiple conditions
```python
# Return value + num if value equal to 2 and num equal to 3
if (value == 2) and (num == 3):
	return value + num
	
# Another example
```