# python-ml-snippets
Python code snippets - scikit-learn, pandas, machine learning

##### Getting basic info about data

```python
# df is pandas dataframe

# Get first 5 rows
df.head() 

```

##### Loading data

```python
# Load data from csv file, file doesn't have header column
# plus setting type of some column 

df = pd.read_csv(
    "datasets/some_dataset.csv", 
    header = None, 
    sep = ';',
    names = ['column_name1', 'column_name2'],
    dtype={'column_name2':np.int})

```
