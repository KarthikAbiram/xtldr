---
hide:
  - navigation
---

# Pandas

## Install
```
uv add pandas
```

## Quick Start
```
import pandas as pd

# Read a csv file
df = pd.read_csv('filename.csv')

# Write to csv
df.to_csv('filename.csv')

# Read an excel file
pd.read_excel("foo.xlsx", "Sheet1", index_col=None, na_values=["NA"])

# Write to an excel file
df.to_excel("foo.xlsx", sheet_name="Sheet1")
```

### Basics
Series: Typically represents a column. A one-dimensional labeled array holding data of any type
```
# From a list
s = pd.Series([1, 2, 3, 4, 5, 6])

# Or from a dictionary
d = {"b": 1, "a": 0, "c": 2}
pd.Series(d)
```

DataFrame: A two-dimensional data structure that holds data like a two-dimension array or a table with rows and columns.
```python
df = pd.DataFrame(
    {
        "A": 1.0, # Constant value for all rows
        "B": pd.Timestamp("20130102"), # Timestamp 2013-01-02 for all rows
        "C": pd.Series(1, index=list(range(4)), dtype="float32"), # Constant 1.0 for all rows
        "D": np.array([3] * 4, dtype="int32"), # Constant 3 for all rows
        "E": pd.Categorical(["test", "train", "test", "train"]), # List, one value for each row
        "F": "foo", # Constant string for all rows
    }
)

# Printing df:
     A          B    C  D      E    F
0  1.0 2013-01-02  1.0  3   test  foo
1  1.0 2013-01-02  1.0  3  train  foo
2  1.0 2013-01-02  1.0  3   test  foo
3  1.0 2013-01-02  1.0  3  train  foo
```

Previewing data:
```python
df.columns # List of columns
df.head() # Initial few rows of data
df.tail(3) # Last 3 rows of data
df.describe() # Compute and show statistical summary like count, max, min, mean
df['A'] # Returns 'A' column
df[0:3] # Returns first 3 rows of data
pd.pivot_table(df, values="D", index=["A", "B"], columns=["C"]) # Creates a pivot table
```

## References
1. [10 minutes to pandas](https://pandas.pydata.org/docs/user_guide/10min.html)