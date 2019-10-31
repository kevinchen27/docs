## Line Charts

Essentially data points called markers joined by line segments

### Create x and y values

`data = [go.Scatter(x=<insert list of values>,y=<insert list of values>,mode = "lines",name="mylines")`

### Define layout

layout = go.Layout(title = "<insert title>"

### Execute figure

<br>
`fig = go.Figure(data = data, layout = layout)`
<br>
`pyo.plot(fig)`