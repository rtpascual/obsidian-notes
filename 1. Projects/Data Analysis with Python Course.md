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
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

sales = pd.read_csv('data/sales_data.csv', parse_dates=['Date'])
```

Data frame is csv representation and is more enforced, columns enforce data types.

Different ways to increase understanding of data set:

```python
# Find number of rows, columns
sales.shape

# See data types and non-null count of each column
sales.info()

# Returns count and statistical data for each column (mean, std, avg, min, max, etc)
sales.describe()
```

Below code shows correlation between columns (red --> blue = low --> high correlation):
```python
fig = plt.figure(figsize=(8,8))
plt.matshow(corr, cmap='RdBu', fignum=fig.number)
plt.xticks(range(len(corr.columns)), corr.columns, rotation='vertical')
plt.yticks(range(len(corr.columns)), corr.columns)
```
