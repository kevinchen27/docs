## Why Pandas

Pandas is essential for data analysis. It allows us to work with data.frames which makes it easy for us to use as input for machine learning models and for graphics packages. Dash also works well with data.frames, and hence this tutorial is included.

## Install pandas

`pip install pandas`

## Import pandas

`import pandas as pd`

## Read csv as data.frame

`df = pd.read_csv("salaries.csv")`
<br>
CSV stand for comma-separated values. Most modern data is formatted into csv files for easier analysis with pandas data.frames.


## Converting Numpy array to data.frame

Matrix of 5 rows and 10 columns
<br>
`mat = np.arange(0,50).reshape(5,10)`
<br>
<br>
Converting to pandas data.frame
`df = pd.DataFrame(data = mat)`

## Data.frame format

Data.frames have 2 attributes:
<br>
- rows or indices
- columns
<br>
Row indices are useful for keeping track of observations and for subsetting rows of a data.frame with loc

## Finding column names

`df.columns`
columns is an attribute, not a method, so there are no parentheses.

## Renaming columns

`df.columns = ["f1","f2","f3","f4","label"]`

## Referencing columns

Columns in dataa.frames are referenced in square brackets using double quotes:
<br>
`df["<column name>"]`
<br>
A single column that is referenced returns a Series object. 
<br>
`df["col 1"]` - returns series
<br>

## Referencing columns to return data.frame

To return a data.frame, place the reference inside a list:
<br>
`df[["<column name>"]]`  - returns data.frame
<br>
You can also call multiple columns by name by placing them inside lists

## Referencing rows and columns with loc

`loc` is used to return certain rows and columns of a data.frame
<br>
`df.loc["<row>", "<column>"]`
<br>
`loc` is useful if you know the "index" or name of the row (and column) that you want to subset. However, it is easier to use `iloc` if you want to reference rows and columns by integers

## Referencing rows and columns with iloc

If you want to reference rows and columns by their position, use `iloc`
<br>
`df.iloc[<rownumber>,<colnumber>]`
<br>
To reference multiple rows and multiple columns, put the rows and/columns into a list