# Jupyter Lab

- Jupyter Lab is web-based user interface for project Jupyter.
- JupyterLabe enables us to work with documents such text, terminals, CSV, Jupyter notebooks, etc in a flexible way.
- We can arrange activities side by side using tabs and spliters.
- Jupyter provides interactive computing such as code consoles, kernel-backend documents enable us to run different files such as Markdown, Python, R.
- Provides live editting/preview documents
- Jupyter also enables us of viewing and handling different data format such as CSV, JSON, PDF, Vega.

## Some Jupyter keyboard shortcuts:

- `c copy cell, v paste cell, x cut cell, dd delete cell, z to undo, y cell formate for code, m cell format for markdown`
- `Shift + Enter to run the code, 00 to restart the kernel`
- We can write markdown using normal markdown syntax such #, \*, - etc.

# Numpy

- Numpy is a python library for data analysis
- Numpy speeds up data processing and many data analysis and machine learning packages leverage it.
- To read data using csv separated by `;`we import csv and write our code as below:

```import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))
```

- The below code will:
- Extract the last element from each row after the header row.
- Convert each extracted element to a float.
- Assign all the extracted elements to the list qualities.
- Divide the sum of all the elements in qualities by the total number of elements in qualities to the get the mean.

```
    qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)

output: 5.6360225140712945
```

- The above examples using csv is complex, that is why Numpy comes into play to simplify these kind of process.

## Creating A NumPy Array

- All the elements in a numpy array have to be same data type.
- If we inlude a string then all data in the array will be converted into strings so we exclude any headers from the data so we can perform some operations on our data.

```
import csv
with open("winequality-red.csv", 'r') as f:
   wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```

- The above code will remove the first row, put the data on a numpy array as a float data type and store it on `wines` variable as show below:

```
[ 7.8 , 0.76 , 0.04 , ..., 0.65 , 9.8 , 5. ],
...,
[ 6.3 , 0.51 , 0.13 , ..., 0.75 , 11. , 6. ],
[ 5.9 , 0.645, 0.12 , ..., 0.71 , 10.2 , 5. ],
[ 6. , 0.31 , 0.47 , ..., 0.66 , 11. , 6. ]])
```

- To check the number of rows and columns we use the `shape` property as in `wines.shape`
- We can also create a numpy array using different methods for example to create an array of a fixed size, we can specify the number of rows and columns and fill it with zeros as in `np.zeros((3,4))`
- We can also create an array and fill it with random numbers as in `np.random.rand(3,4)`

### Using NumPy To Read In Files

- We can read csv files using numpy.genfromtxt function.

```
wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)
```

### Indexing NumPy Arrays

- Array indexing is used to pick specific elements/group of elements from the array.
- Numpy array indexes start at 0.
- We specify indexes matching the size of our array, eg for 2d array we can use array[2,3] to specify row 2 column 4.

### Slicing NumPy Arrays

- `:` is used to select all the elelments from the start eg `wines[:3,3]` Will select rows 0 to 3 and columns 3.
- If we don't specify an ending then `:` will select the whole rows or columns as in array[:,3] will select all rows and column 3 and `array[:,:] will select the entire 2D array elements.
  ##3 Assigning Values To NumPy Arrays
- We can use indexes to assign values to specific index/location such as `array[4, 10] = 5` will add a value of 5 to row 4 and column 10.

### 1-Dimensional NumPy Arrays

- We can generate 1D array of random numbers using `np.random.rand(3)` by passing it a single number and if we pass it 2 numbers then we get a 2D array.
- Numpy arrays get more complex once we have more than 2D arrays.

### N-Dimensional NumPy Arrays

- We can store data on year monthly income in quatarly format for easy/fast access

```
year_one = [
    [500,505,490],
    [810,450,678],
    [234,897,430],
    [560,1023,640]
]
```

- We can use the `shape` to find the shape of the array such as `array.shape` will display the shape of the array.

### NumPy Data Types

- Numpy stores data in C type data types not Python because Numpy is writen using C langauge, but still maps to Python data type:
- We can use `array.dtype` to find the data type of an array.
- float — numeric floating point data.
- int — integer data.
- string — character data.
- object — Python objects.
- We can use `array.astype()` to specify the data type or convert the data type.

### NumPy Array Operations

- We can perform `/, *, -, +, ^` operations on a numpy array.

### Broadcasting

- When arrays aren't the same size numpy uses Broadcasting to perform the task and match the sizes or displays an error.

### NumPy Array Methods

- `sum()` used to get the sum of whatever elements specified
- passing the `axis` as 0 or will make the axis excluded from the operation.
- Other methods are `mean(), std, min, max`

<br /> 
## References:

[JupyterLab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)
[NumPy Tutorial: Data Analysis with Python](https://www.dataquest.io/blog/numpy-tutorial-python/)

<br /> <br />

## [<-- Back](README.md)
