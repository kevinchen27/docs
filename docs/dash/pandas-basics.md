## Install pandas

`pip install pandas`

## Import pandas

`import pandas as pd`

## Read csv as data.frame

`df = pd.read_csv("salaries.csv")`

## Converting Numpy array to data.frame

Matrix of 5 rows and 10 columns
<br>
`mat = np.arange(0,50).reshape(5,10)`
<br>
<br>
Converting to pandas data.frame
`df = pd.DataFrame(data = mat)`

## Finding column names

`df.columns`

## Renaming columns

`df.columns = ["f1","f2","f3","f4","label"]`
