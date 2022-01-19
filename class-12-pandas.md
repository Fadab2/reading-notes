# Pandas

- Pandas is a data anaylsis tool.
- to use Panadas we must first import it using:

```
import numpy as np
import pandas as pd
```

- We can create a series and let pandas create indexes for us:

```
s = pd.Series([1, 3, 5, np.nan, 6, 8])

```

- Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns:

```
dates = pd.date_range("20130101", periods=6)

dates
Out[6]:
DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
               '2013-01-05', '2013-01-06'],
              dtype='datetime64[ns]', freq='D')

df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

df
                 A         B         C         D
2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
2013-01-02  1.212112 -0.173215  0.119209 -1.044236
2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
2013-01-04  0.721555 -0.706771 -1.039575  0.271860
2013-01-05 -0.424972  0.567020  0.276232 -1.087401
2013-01-06 -0.673690  0.113648 -1.478427  0.524988
```

- We can create a DataFrame by passing a dictionary objects that can be converted to series-like.

```
df2 = pd.DataFrame(
    {
        "A": 1.0,
        "B": pd.Timestamp("20130102"),
        "C": pd.Series(1, index=list(range(4)), dtype="float32"),
        "D": np.array([3] * 4, dtype="int32"),
        "E": pd.Categorical(["test", "train", "test", "train"]),
        "F": "foo",
    }
)
output:
   A          B    C  D      E    F
0  1.0 2013-01-02  1.0  3   test  foo
1  1.0 2013-01-02  1.0  3  train  foo
2  1.0 2013-01-02  1.0  3   test  foo
3  1.0 2013-01-02  1.0  3  train  foo
```

### Viewing data

- to view top row we use: `df.head()`
- to view bottom row we use: `df.tail(2)` we can pass it how many rows we want to see.
- to display just the index `df2.index`
- Numpy have one data type per array while pandas have a data type per column.
- the `df.describe()` gives an overview of the data
- the `df.T` transposes data
- sorting data by an axis `df.sort_index(axis=1, ascending=False)`
- sorting data by values `df.sort_values(by="B")`
- selecting a single column `df["A"]`
- selecting using slices `df[0:3]`
- selecting by labels `df.loc[dates[0]]`
- selecting on a multi-axis by label `df.loc[:, ["A", "B"]]`

### Selection by position

- Select via the position of the passed integers `df.iloc[3]`
- integer slices, acting similar to NumPy/Python `df.iloc[3:5, 0:2]`
- lists of integer position locations, similar to the NumPy/Python style `df.iloc[[1, 2, 4], [0, 2]]`
- licing rows explicitly `df.iloc[1:3, :]`
- slicing columns explicitly `df.iloc[:, 1:3]`
- getting a value explicitly `df.iloc[1, 1]`

### Boolean indexing

- single column’s values to select data `df[df["A"] > 0]`
- Selecting values from a DataFrame where a boolean condition is met `df[df > 0]`
- using the isin() method for filtering `df2 = df.copy()`

### Setting

- Setting a new column automatically aligns the data by the indexes as in:

```
s1 = pd.Series([1, 2, 3, 4, 5, 6], index=pd.date_range("20130102", periods=6))
output:
2013-01-02    1
2013-01-03    2
2013-01-04    3
2013-01-05    4
2013-01-06    5
2013-01-07    6
```

- Setting values by label `df.at[dates[0], "A"] = 0`
- Setting values by position: `df.iat[0, 1] = 0`
- Setting by assigning with a NumPy array: `df.loc[:, "D"] = np.array([5] * len(df))`

### Missing data

- the `np.nan` represents missing data in panadas.
- To drop any rows that have missing data `df1.dropna(how="any")`
- Filling missing data `df1.fillna(value=5)`

### Operations

- stats operations in general exclude missing data.
- get the mean `vdf.mean()`
- to get the mean on the other axis `df.mean(1)`

### Apply

- Applying functions to the data to calculate cumulative sum `df.apply(np.cumsum)`
- Applying lamba function to get max and min `df.apply(lambda x: x.max() - x.min())`

- turn a string s to lower case `s.str.lower()`
- group the data `df.groupby("A").sum()`
- plot data using matplotlib `ts.plot();`
- read data from csv file `pd.read_csv("filename.csv")`
  <br />

## References:

[10 minutes to pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
[]()

<br />

## [<-- Back](README.md)
