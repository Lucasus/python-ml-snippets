#### What can you find here?
Useful Python code snippets, helpful when working on machine learning modesl with scikit-learn and pandas

#### Snippets are below:

##### Loading data

```python
import pandas as pd

# Load data from csv file, file doesn't have header column
# plus setting type of some column 
df = pd.read_csv(
    "datasets/some_dataset.csv", 
    header = None, 
    sep = ';',
    names = ['column_name1', 'column_name2'],
    dtype={'column_name2':np.int})
```

##### Getting basic info about data

```python
# df is pandas dataframe

# Get first 5 rows
df.head() 

# Get information about data types, number of rows
df.info()
```

##### Plotting 

Configuration
```python
#Configure default size of plots in Jupyter Notebook (mostly to make them bigger)
import matplotlib.pyplot as plt
plt.rcParams['figure.figsize'] = [16, 8]
```

Plot distibution of some value - sort by occurence count, show top 20 
```python

```
Result:




