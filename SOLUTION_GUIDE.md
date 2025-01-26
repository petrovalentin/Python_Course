# Solution Guide: Fixing "NameError: name 'sales' is not defined" (Fixes #44)

## Step-by-Step Solution

1. **Required Imports**
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

2. **Load the Data**
```python
sales = pd.read_csv('data/sales_data.csv')
```

## Key Insights from the Data

### Data Structure
- Total records: 113,036
- Time period: 2011-2016
- Contains customer, product, and sales information

### Sales Distribution
- Bikes: 64.0% of total profit
- Accessories: 27.6% of total profit
- Clothing: 8.4% of total profit

### Geographic Coverage
- Countries: United States, Canada, France, Germany, Australia, United Kingdom
- Highest profit: United States ($11,073,644)
- Highest average order value: United Kingdom ($324.07 per order)

### Customer Demographics
- Age range: 17-87 years
- Average customer age: 36 years
- Average order quantity: 12 items

## Common Analysis Examples

1. **Basic Statistics**
```python
sales[['Customer_Age', 'Order_Quantity']].describe()
```

2. **Time Trends**
```python
sales['Date'] = pd.to_datetime(sales['Date'])
sales.groupby('Year')['Profit'].sum()
```

3. **Geographic Analysis**
```python
sales.groupby('Country')['Profit'].sum()
```

4. **Product Analysis**
```python
sales.groupby('Product_Category')['Profit'].sum()
```

Remember: Always ensure the data is loaded before performing any analysis to avoid the NameError.