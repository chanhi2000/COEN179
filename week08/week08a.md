# week08a

## SHORTEST PATH
- ####input:
	- weighted graph ( every edge has a associated weight $$w(e)$$ )
	- assume $$\omega(e)\geq0$$
- ####outputs:
	- the deepest path from one vertex $$v$$ to any other vertex in the graph.
 
- "cheapest" path form $$v$$ to $$w$$ is the minimum total afterall such paths.
- BFS search is needed to do this job.

![fig01](img/[COEN179]week08a-fig01.png)
![fig02](img/[COEN179]week08a-fig02.png)
![fig03](img/[COEN179]week08a-fig03.png)

## MINIMUM SPANNING TREE
- a tree that contains all the vertices of the graph (using edges of the graph) is called a spanning tree.
- **problem**: find a spanning tree for the graph with minimum total weight.

![fig04](img/[COEN179]week08a-fig04.png)
- prim's algorithm
- kruskal's algorithm