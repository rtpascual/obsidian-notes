```
---
aliases:
---
```

Tags: [[Learn Python]], [[Data Analysis with Python]]

# Data Analysis with Python Course
## What is data analysis?
The process of inspecting, cleansing, transforming and modeling data. Goal of discovering useful information, informing conclusion, and helping decision making.

Gathering data, cleaning it, and transforming the data for analysis. Modeling data adapting real life scenarios to information system, using statistics in order to see if any pattern or model arise.

Once done processing data and finding models, try to draw conclusion.

Create different views for different groups based on their goals and level of detail of the data.

### Data Analysis Process
Starts by getting data, examples are your own database, web API, or file store in a different format.

Data would have to be cleaned and then transformed to have it ready for analysis.

Analyze the data and build statistical models and create visuals and representations.

Build machine learning models, build ETL pipelines, create dashboards or reports, etc.

## Data Analysis Example A
Example code gets csv file into python:
```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

sales = pd.read_csv('data/sales_data.csv', parse_dates=['Date'])
```

Data frame is csv representation and is more enforced, columns enforce data types.

Different ways to increase understanding of data set:

```py
# Find number of rows, columns
sales.shape

# See data types and non-null count of each column
sales.info()

# Returns count and statistical data for each column (mean, std, avg, min, max, etc)
sales.describe()
```

Below code shows correlation between columns (red --> blue = low --> high correlation):
```py
fig = plt.figure(figsize=(8,8))
plt.matshow(corr, cmap='RdBu', fignum=fig.number)
plt.xticks(range(len(corr.columns)), corr.columns, rotation='vertical')
plt.yticks(range(len(corr.columns)), corr.columns)
```

## Data Analysis Example B
Following code allows to get all sales in state of Kentucky:
```py
sales.loc(sales['State'] == 'Kentucky')
```

loc is able to filter the data and view a subset.

### Reading data from SQL Database
Example code gets data from SQL database in python:
```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import sqlite3

conn = sqlite3.connect('data/sakila.db')

df = pd.read_sql('''
	SELECT
		rental.rental_id, rental.rental_date, rental.return_date,
		customer.last_name AS customer_lastname,
		store.store_id,
		city.city AS rental_store_city,
		film.title AS film_title, film.rental_duration AS film_rental_duration,
		film.rental_rate AS film_rental_rate, film.replacement_cost AS film_replacement_cost,
		film.rating AS film_rating
	FROM rental
	INNER JOIN customer ON rental.customer_id == customer.customer_id
	INNER JOIN inventory ON rental.inventory_id == inventory.inventory_id
	INNER JOIN store ON inventory.store_id == store.store_id
	INNER JOIN address ON store.address_id == address.address_id
	INNER JOIN city ON address.city_id == city.city_id
	INNER JOIN film ON inventory.film_id == film.film_id
	;
''', conn, index_col='rental_id', parse_dates=['rental_date', 'return_date'])
```

## NumPy Introduction A
NumPy is a numeric computing library, processing numbers and calculating with numbers.

NumPy has limited scope.

Python processing numeric numbers is slow when processing large amounts of data. NumPy is very efficient that sits on top of Python.

Usually don't use NumPy directly, matplotlib and pandas sit on top of NumPy.

## NumPy Introduction B
Regular Python stores more memory for a variable of integer type because it stores attributes as well for the variable that may not be necessary.

In NumPy, you can control the size of the bits used for the integer.

NumPy is an array processing library.

Built-in data structures in Python are not optimized for high level computing.

Main advantage is that NumPy takes advantage of CPU instructions.

## NumPy Arrays
Basic NumPy arrays:
```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([0., .5, 1., 1.5, 2.])
```

Can get elements by stating indices:
```python
import numpy as np

b = np.array([0., .5, 1., 1.5, 2.])

b[0], b[2], b[-1] 	# Returns (0.0, 1.0, 2.0)
b([0, 2, -1]) 		# Returns NumPy array([0., 1., 2.])
```

Default NumPy array types and initializing with specific type:
```python
import numpy as np

a = np.array([1, 2, 3])

a.dtype 								# Returns int64 (default 64 if system is 64-bit)

np.array([1, 2, 3, 4], dtype=np.float) 	# Creates NumPy array with float instead of int

np.array([1, 2, 3, 4], dtype=int8) 		# Creates NumPy array with int8 instead of int64
```

NumPy is usually used for numbers, dates, booleans in numeric processing.

It is possible to create matrices with NumPy. NumPy has a lot of attributes and functions to work with multi-dimensional arrays.

```python
import numpy as np

A = np.array([
	[1, 2, 3],
	[4, 5, 6]
])

A.shape # Returns (2,3)
A.ndim 	# Returns 2
A.size 	# Returns 6

B = np.array([
	[
		[12, 11, 10],
		[9, 8, 7],
	],
	[
		[6, 5, 4],
		[3, 2, 1],
	]
])

B.shape # Returns (2, 2, 3)
B.ndim 	# Returns 3
B.size 	# Returns 12
```

If multi-dimensional array is not done correctly, NumPy will fall back to Python object type.

### Index and Slice
```python
import numpy as np

A = np.array([
	[1, 2, 3],
	[4, 5, 6],
	[7, 8, 9]
])

A[1] 		# Returns array([4, 5, 6])

A[1][0] 	# Returns 4

A[1, 0] 	# Returns 4 as well, alternative to above

A[0:2] 		# Returns array([
			#				[1, 2, 3],
			#				[4, 5, 6]
			#			   ])
		
A[:, :2] 	# Returns every row, elements up to 2 index (0 and 1)
		 	# array([
			#		[1, 2],
			#		[4, 5],
			#		[7, 8]
			#	   ])

A[1] = np.array([10, 10, 10])
# A = 	array([
#				[1, 2, 3],
#				[10, 10, 10],
#				[7, 8, 9]
#			 ])

A[2] = 99
# A = 	array([
#				[1, 2, 3],
#				[10, 10, 10],
#				[99, 99, 99]
#			 ])
```

### Summary Statistics
```python
import numpy as np

a = np.array([1, 2, 3, 4])

a.sum() 		# Returns 10
a.mean() 		# Returns 2.5
a.std() 		# Returns 1.118033988749895
a.var() 		# Returns 1.25

A = np.array([
	[1, 2, 3],
	[4, 5, 6],
	[7, 8, 9]
])

A.sum() 		# Returns 45
A.mean() 		# Returns 5.0
A.std() 		# Returns 2.581988897471611

A.sum(axis=0) 	# Returns array([12, 15, 18])
A.sum(axis=1) 	# Returns array([6, 15, 24])
```

## NumPy Operations
### Broadcasting and Vectorized Operations
```python
import numpy as np

a = np.arange(4) 	# a = array([0, 1, 2, 3])

a + 10 				# Result is new array([10, 11, 12, 13])

a * 10 				# Result is new array([0, 10, 20, 30])

a += 100 			# a = array([100, 101, 102, 103])
```

NumPy also handles cases with multiple arrays

```python
import numpy as np

a = np.arange(4) 				# a = array([0, 1, 2, 3])
b = np.array([10, 10, 10, 10]) 	# b = array([10, 10, 10, 10])

a + b 							# Result is array([10, 11, 12, 13])
a * b 							# Result is array([0, 10, 20, 30])
```

## NumPy Boolean Arrays
Also called masks.

Can be used for filtering.

```python
import numpy as np

a = np.arange(4) 				# a = array([0, 1, 2, 3])
a[[True, False, False, True]] 	# Returns array([0, 3])
a >= 2 							# Returns array([False, False, True, True])
a[a >= 2] 						# Returns array([2, 3])
a[a > a.mean()] 				# Returns array([2, 3])
a[~(a> a.mean())] 				# Returns array([0, 1])
a[(a == 0) | (a == 1)] 			# Returns array([0, 1])
a[(a <= 2) & (a % 2 == 0)]		# Returns array([0, 2])
```

