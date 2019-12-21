## Creating network tree from 26 json files

ICD 11 data consists of 26 root nodes, each having its own subtree. The data for each subtree/root was downloaded using a recursive algorithm deployed by Dibakar Sigdel. The network graph database was made created using NetworkX, with the following code

```
trees = []
for data in N:
    G = nx.Graph()
    for item in data:
        item_id = item['id']
        G.add_node(item_id,\
               title=item['title'],\
               defn = item['defn'])
        childs = item['childs']
        if childs!= 'Key Not found':
            for c_id in childs:
                G.add_edge(item_id,c_id, object = 'child')
    trees.append(G)
```
    
The JSON files were imported and read into a list, and another list was created which stored the nodes and edges of all the nodes in the 26 trees.

## Properties of nodes 
- Item id: ID of the node
- Title: Name of the node
- Defn: Description of the node
- Child: Children of the node (helps in building edges that specify relationship

## Tidying data into pandas.dataframe

<<<<<<< HEAD
The reason we want to do this is because Dash works well with pandas data.frames. 

```
lists = [] #list storing every single root with its subtree
for G in trees:
    root = list(G.nodes())[0] #stores the root tree
    node2depth = [] 
    #for loop to iterate through every node in the each subtree
    for node in G.nodes():
        depth = nx.shortest_path_length(G, root, node)
        #print(node,"|",depth)
        node2depth.append({"node":node,"depth":depth}) 
    DF = pd.DataFrame(node2depth) #stores node id and corresponding depth level
    DF = DF.set_index("depth")
    lists.append(DF.groupby("depth").count())
```

<p align = "center">
<img src="https://github.com/kevinchen27/docs/blob/master/images/node%20depth.png" width="500" align = "middle"/>
</p>


## Transform data.frame into tidy format (observations in rows, variables in columns)

```
df = pd.concat(lists, axis=1)
df = df.fillna(0)
df = df.transpose()
df.index = titles
df = df.astype(int)
df2 = df.assign(total_nodes = lambda x: df.sum(axis =1))
```
=======
The reason we want to do this is because Dash works well with pandas data.frames
>>>>>>> fdebf356440937f88cd478d30c950f880a9470e1
