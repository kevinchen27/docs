## Intro to Dash

Dash is great because:
- You can create dashboards in python
- Served as web apps that you can deploy, not static html files
- Composed of 2 parts: layout and interactivity like how moving sldier affects visualization

## Essential packages

These packages must also be installed via pip install prior to loading them: 
```
import dash
import dash_core_components as dcc
import dash_html_components as html
import plotly.graph_objs as go
import numpy as np
import pandas as pd
```

## Step 1: Create instance of Dash

`app = dash.Dash()`
<br>
`app.layout = html.Div()` Creates a division in our dashboard to insert things

## Sample barplot

```
app.layout = html.Div(children = [    
    html.H1("Hello Dash!"), 
    html.Div("Dash: Web Dashboard with Python"),
    dcc.Graph(id= "example", #dcc - dash core component and id for reference
             figure = {"data":[  #figure will take in dictionary
                 {"x":[1,2,3],"y":[4,1,2],"type":"bar","name":"SF"},
                 {"x":[1,2,3],"y":[2,4,5],"type":"bar","name":"NYC"}
             ],
                      "layout":{   #figure will have key for data and dictionary
                          "title":"BAR PLOTS!" 
                      }}) #everything inside the div is a cjildren's list
                ])

if __name__ == '__main__': #checks if im running this script, it will grab application obj and run the server 
    app.run_server()
```
<br>    
**Documentation Breakdown**
<br>
After creating Dash app, we specify the layout of the Dashboard
<br>
`children` - List of components in the Dashboard
<br>
`html.Div` Creates a "division" on the webpage. This is needed because that "division" or block will contrain the Dash graphic, and we can create multiple Divisions for multiple Dashboards on the same webpage
<br>
`html.H1` - gives a header to the webpage
<br>
`html.Div` - this nested Div creates another block within which is the Dashboard graphic
<br>
`dcc.Graph` - specifies the type of graph that will be used. Depending on the graph, the data input will vary
<br>
`layout` - Can specify the title of the plot. Arguments are listed in Plotly documentation
<br>
We finally run the server using `app.run_server`. The server is required to keep running to access the webpage with the dashboard