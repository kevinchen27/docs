## Barplots in Plotly

### Create data set
`data = [go.Bar(x=<insert list/array or df col>,y=<insert list/array or df col>)]`
<br>
<br>
x is an array or column of factors
<br>
y is corresponding array or column of total count of something

### Define layout

`layout=go.Layout(title="<insert graph title>", ...)`

### Store figure in fig and execute

`fig = go.Figure(data,layout)`
<br>
`pyo.plot(fig)`