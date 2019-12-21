## What is NetworkX

NetworkX is a library in Python that specializes in working with network graphs. NetworkX comes with a set of functions that allow for populating, editing and exploring network graphs with node and edge attributes

## Network graphs

Network graphs represent connections between data points called "nodes" and connections between these nodes called "edges". All nodes can have properties attached to them, and edges too have properties which specify the relationship between two nodes. 
<br>
In ICD 11, each node represents a disease/condition and has properties such as:
<br>
- ID: Disease/Condition ID in ICD 11
- Title: Name of the node
- Defn: Description of the node

## Creating Network Graphs

### Install NetworkX library

`pip install networkx`

### Import library

`import networkx as nx`

### Create empty graph 

`G= nx.Graph()`

### Add edges

Adding edge between nodes automaticaly creates the nodes between which the edge is specified. You can also specify the properties of the edge.
<br>
`G.add_edge('A','B', <property 1> = <insert number or word>, ...)`

### Add nodes with properties

You can also add nodes and specify its properties:
<br>
`G.add_node('A', <property1> = <insert property>`