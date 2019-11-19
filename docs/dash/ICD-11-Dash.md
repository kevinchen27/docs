## Creating network tree from 26 json files

ICD 11 data consists of 26 root nodes, each having its own subtree. The data for each subtree/root was downloaded using a recursive algorithm deployed by Dibakar. The network graph database was made created using NetworkX, with the following code

`trees = []
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
    trees.append(G)`
    
The JSON files were imported and read into a list, and another list was created which stored the nodes and edges of all the nodes in the 26 trees.

## Tidying data into pandas.dataframe

The reason we want to this is because Dash works well with pandas data.frames