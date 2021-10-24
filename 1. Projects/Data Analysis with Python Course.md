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

Dataframe is csv representation and is more enforced, columns enforce data types.

