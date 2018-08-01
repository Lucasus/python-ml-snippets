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

# Get basic distribution information
df.describe()
```

##### Data manipulation
Very useful snippet: https://gist.github.com/bsweger/e5817488d161f37dcbd2

##### Training / test sets preparation

Taking first 80% of rows as training set, remaining as test set
```python
X = df.loc[:,["attribute_1", "attribute_2", "attribute_3", "attribute_4"]]
y = df.loc[:, "label"]

train_count = int(len(df.index)*0.8)
X_train = X.head(train_count)
y_train = y.head(train_count)

test_count = len(df.index) - train_count
X_test = X.tail(test_count)
y_test = y.tail(test_count)
```

Taking 80% of random rows as training set, remaining as test set
```python
X = df.loc[:,["attribute_1", "attribute_2", "attribute_3", "attribute_4"]]
y = df.loc[:, "label"]
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.20, random_state=42)
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
import pandas as pd
pd.value_counts(df['some_column']).nlargest(20).plot.bar()
```
Result:
![Plot 1](plot1.png?raw=true "Title")



