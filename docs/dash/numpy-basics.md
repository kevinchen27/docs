# Numpy

Numpy is a package used to conduct data analysis in Python. For Dash, numpy arrays are useful as input for Plotly and Dash objects (Dash is built by Plotly)

## First install pandas and numpy

`pip install numpy`

## Import numpy

`import numpy as np`

## Arrays in Numpy

Convert list to array
<br>
`mylist = [1,2,3,4]`
<br>
`arr = np.array(mylist)`
<br>

## Differences with Lists

- **+** in arrays do element-wise addition, versus concatenation in lists
- *  in arrays do element-wise multiplication, versus duplication in lists
- ** in arrays do element-wise squaring; this does not work in lists

## Math operations
`np.sum()` gives sum of elements in array
<br>
`np.dot()` gives dot product of two arrays
<br>
`np.sqrt()` gives square root of an array
<br>
`np.mean()` gives mean of array
<br>
`np.var()` gives variance of array