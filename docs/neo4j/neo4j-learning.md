## Neo4j 

Neo4j is a graph database platform that simplifies operations and analysis on network graphs. It is designed for fast management of nodes and relationships and is significantly faster than performing JOINS on tables. 

## Neo4j Cypher

Cypher is Neo4j's query language. It is built for working with graph data and uses patterns to match and describe graph data. Example of a Neo4j query:

### Node syntax in Cypher

() represents an anonymous node. If we want to refer to the node elsewhere, we add a varriable, like (matrix). 
<br>
() - anonymous node
<br>
(matrix) - variable added to node. This variable can be referenced later in the query
<br>
(:Movie) - label :Movie declares the node's type
<br>
(matrix:Movie) - variable name matrix with label Movie
<br>
(matrix:Movie {title: "The Matrix"}) - variable matrix of type Movie with the property title having value 'The Matrix'
<br>
(matrix:Movie {title: "The Matrix", released: 1997})
<br>
Variables are restricted to single statement i.e they may have different or no meaning in another statement

### Pattern Syntax

Example:
<br>
`(:Person) - [:LIVES_IN]->(:CITY)-[:PART_OF]->(:Country)` 
<br>
This statement finds a Person (label) who "Lives in" (relationship) in a "City" (label) which is "Part Of" (relationship) a "country" (label)

### Pattern Syntax with variables

Using a variable is useful if one wants to refer to that variable later on in a query. IF we are matching a label, we may just specify any variable name before the colon as shown below:

```
MERGE (a:Person {name:"Ann"})
CREATE (a)-["HAS_PET]->(:Dog{name:"Sam"})
```
<br>
The above query Creates a relationship with the Dog whose name is Sam. The person is stored as `a` and `a` is referred to when creating the node and relationship with Ann's pet.