```
---
aliases: [for statement,for loop]
---
```

Tags: 

# for Statements
Works similar to `foreach` in C#.

##### Example
```python
# Measure some strings:
words = ['cat', 'window', 'defenestrate']

for w in words:
	print(w, len(w))
```

##### Output
```md
cat 3
window 6
defenstrate 12
```

### Multiple parameters
`for` statement can also have multiple parameters.

##### Example with items and it's index
```python
array = ['hello', 'world']

for index, element in enumerate(array):
	print(f'Element {element} is in index {index}')
```

##### Output
```md
Element hello is in index 0
Element world is in index 1
```

##### Example with two-dimensional array
```python
2dArray = [(0,1), ('a','b')]

for i, j in 2dArray:
	print(f'i: {i} j: {j}')
```

##### Output
```md
i: 0 j: 1
i: a j: b
```
