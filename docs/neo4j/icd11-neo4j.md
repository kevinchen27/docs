# Neo4j with ICD 11 Data

ICD 11 MMS data was transformed into a network graph in Neo4j using Neo4j's Python Bolt Driver. A Neo4j driver enables a developer to run Cypher queries in Python. These queries can be consumed as BoltStatementResults, which is an object returned by Neo4j in Python. 

## Install Neo4j 

`pip install neo4j`

## Import Neo4j

`from neo4j import GraphDatabase`

## Load JSON file


```
with open("MMS.json","r") as mms:
    mms_data = json.load(mms)        
```

## Initialize Neo4j Driver

To initialize driver, Neo4j must be open in the application and local server set up in Neo4j. The driver argument takes the following arguments:
<br>
- uri: identifies graph database and how to connect it
- auth: authentication that requires the username, password

```
driver = GraphDatabase.driver(uri = "bolt://localhost:11008", auth = ("neo4j","pythondriver"))
```

## Populate MMS data in Neo4j

A single MMS 