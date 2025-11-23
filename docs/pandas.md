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
```

## Basics
Series: Typically represents a column. A one-dimensional labeled array holding data of any type
```
# From a list
s = pd.Series([1, 2, 3, 4, 5, 6])

# Or from a dictionary
d = {"b": 1, "a": 0, "c": 2}
pd.Series(d)
```

DataFrame: A two-dimensional data structure that holds data like a two-dimension array or a table with rows and columns.
```
```

## References
1. [10 minutes to pandas](https://pandas.pydata.org/docs/user_guide/10min.html)