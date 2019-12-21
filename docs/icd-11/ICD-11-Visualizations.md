ICD 11 Visualizations were created using Dash and data cleaned and obtained from ICD 11 Website and API. A data.frame of each root node with number of nodes per level was created and imported.

## Importing libraries

```
import pandas as pd
import numpy as np
import dash
import dash_core_components as dcc
import dash_html_components as html
from dash.dependencies import Input, Output
import plotly.graph_objs as go
import dash_bio as dashbio
```

## Import csv as data.frame

```
pd.read_csv("withoutsum.csv")
```

## Interactive barplot showing nodes per level for each root

### Set up instance of Dash

`app = dash.Dash()`

### Specify dashboard layout

Once an instance of Dash is created, the layout of the dashboard must be specified. `html.Div` creates a division or container on the web page within which the dashboard will be fit. 
<br>
Inside html.Div(), a list is accepted and components of the dashboard are specified. In this case, we have a dropdown from which a user can choose which root node they want to look and look at the distribution of nodes in each level of that root node. A pointer to the graph of the dashboard also needs to be specified.

```
app.layout = html.Div([
                dcc.Dropdown(id="disease-type", #
                            options = [{"label":disease, "value":disease} for disease in df[cols[0]]], #dropdown list containing each root node
                             value = df[cols[0]].iloc[0]
                            ),
    dcc.Graph(id="graphics")
            ])
```

### Specify callback

`@app.callback` is a decorator that specifies which are the inputs and outputs of the graph. The decorator points to the elements specified in the dashboard layout object.

```
@app.callback(
Output("graphics","figure"), #connects to the graphics id in 
[Input("disease-type","value")])
```

### Update graph function

Since our dashboard is an interactive graphic that updates depending on user input, we need to create a function that describes this behavior. The function below matches the user input with the data in the data.frame, and returns the barplot with detailed layout of the data, title, and x and y axes.

```
def update_graph(selected_disease):
    filtered_df = df[df[cols[0]] == selected_disease]
    nodes = filtered_df.loc[:,"1":"12"].values.tolist()
    nodes = nodes[0]
    return {
        "data": [
                 {"x":list(cols)[2:14],"y":nodes,"type":"bar"},
             ],
        "layout": go.Layout(title = "Nodes Per Level",
                           xaxis = {"title":"Levels"},
                            yaxis = {"title":"Nodes"}
                           )
    }
```

### Run server

Finally, we launch the server on which the dashboard is hosted with the following command:
```
if __name__ == "__main__":
    app.run_server()
```

### Snapshot of Graphic

<p align = "center">
<img src="https://github.com/kevinchen27/docs/blob/master/images/dash1.png" width="500" align = "middle"/>
</p>
