## Install plotly 

Basic plotly gives us an idea of Dash syntax and documentation. Dash syntax for its graphics are built on top of plotly. Plotly images are saved as html files in the computer.
<br>
`pip install plotly==4.2.1`

## Import plotly

`import plotly.offline as pyo`
`import plotly.graph_objs as go`

## Scatter plots

Data must first be in a list
<br>
### Setup data
<br>

```
data = [go.Scatter(x= <list of values for x-axis>,
    y =<list of values for y-axis>,
    mode = 'markers', 
    marker = dict(size = <numeric size>,
    color = "<insert color or rgb>",
    symbol = "<type of scatterplot symbol>",
    line = dict(<dictionary specifying with of line>)
    ))]
 ```    
    
<br>
<br>
### Define Layout

```
layout = go.Layout(title = "<insert plot title",
                  xaxis = dict(title = "MY X AXIS" ,
                  yaxis = dict(title = "MY Y AXIS"), 
                  hovermode = "closest")
```
                  
<br>
<br>
### Save HTML file
`pyo.plot(data, filename = "<insert name>.html")`
<br>
<br>

### Execute
`fig = go.Figure(data=data,layout=layout)`
<br>
`pyo.plot(fig,filename="<filename>.html")`



