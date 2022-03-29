# Graphs

* A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.
### Some terms:
* Vertex/Node: a data object that can have zero or more adjacent vertices.
* Edge: a connection between two nodes.
* Neighbor: adjacent nodes connected via an edge.
* Degree: number of edges connected to that vertex.
## Directed vs Undirected Graphs
* Directed graph: direction between edges is specified etc with arrows
* Undirected graphs: Direction is not specified between nodes.

## Complete vs Connected vs Disconnected
* Complete: all nodes are connected to all other nodes.
* Connected: Each node connected at least to one other node.
* Disconnected: Some nodes may not be connected to other nodes.

## Acyclic vs Cyclic

* Acyclic/DAG: is a directed graph without cycles as a tree.
* Cyclic: is when a graph starts and ends at the same vertex.

Graphs can be presented as:
* Adjacency Matrix: as 2-D array and indicating connection with a 1 and no connection with a 0.
* Adjacency List: as a list showing connections with arrows.

## Traversals:
We traverse graphs as we traverse trees.
* Breadth first
```
ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    DECLARE visited <-- new Set()

    breadth.Enqueue(vertex)
    visited.Add(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                visited.Add(child)
                breadth.Enqueue(child)   

    return nodes;
```
* Depth first: Stack is used `root, push, peek, pop`
<br />

## References

[Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

<br />

## [<-- Back](README.md)
