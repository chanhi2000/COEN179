# week06a

## GRAPH ALGORITHM

- #### DEFINITION:
	- A graph $$G(V,E)$$ has
	- $$V=\{v_1,v_2,\cdots,v_n\}$$: set of vertices
	- $$E=\{e_1,e_2,\cdots,e_n\}$$: set of edges
	- where $$e_{12}=(v_1,\:v_2)$$.

- if the **ordering of the pair** matters, we call G, *directed graph*.
- otherwise, we call G, *undirected graph*.

- example: digraph
```sequence
V1->V2: e12
V3<->V2: e23
V4->V2: e42
V5->V4: e45
V2->V5: e25
```

- example: undigraph
```sequence
V1-V2: e12
V3-V2: e23
V4-V2: e24
V5-V4: e45
V2-V5: e25
```


- #### REPRESENTATION:
	- ADJACENCY MATRIX,
		- $$v[1],\:v[2],\:\cdots\:,v[n]$$
		- represents the edge set using a 2-dimensional array.
$$
\begin{matrix}
&v[1]&v[2]&\cdots&v[n]\\
v[1]&&&&\\
v[2]&&&&\\
\vdots&&&&\\
v[n]&&&&\\
\end{matrix}
$$
- row: $$i$$
- column: $$j$$
- **1**: there is such an edge from $$v[i]$$ to $$v[j]$$
- **0**: no such edge.

- example: undigraph
``` sequence
V1-V2: e12
V3-V2: e23
V4-V2: e24
V5-V4: e45
V2-V5: e25
V3-V6: e36
V2-V6: e26
V5-V6: e56
V2-V2: e22
```

$$
\begin{matrix}
&v[1]&v[2]&v[3]&v[4]&v[5]&v[6]\\
v[1]&0&1&0&1&0&0\\
v[2]&1&0&0&1&1&1\\
v[3]&0&0&0&0&0&1\\
v[4]&1&1&0&0&1&0\\
v[5]&0&1&0&1&0&1\\
v[6]&0&1&1&0&1&0\\
\end{matrix}
$$
- **loop**: an edge between a vertex and itself.
- This is symmetric in the undirected case (may or my not be symmetric in digraph)
- if its not just 0's and 1's-> we call the graph "weighted".


## CARDINALITY
- $$ |V| $$ = # of elements in $$V$$, cardinality of $$V$$.
- # of bits is $$|V|^2$$ so, in general graph G has $$O{(|V|^2)}.

when $$|E|$$ is a lot less than $$|V|^2$$. we call the graph, sparse.


## LINKED LIST REPRESENTATION
 every vertix has a list of vertices that are adjust to it.

 ``` sequence
v1->x1
x1->x2
x2->x3
v1->v2
v2->y1
y1->y2
```

one(directed) or two (undirected) nodes for each edge.
- # of nodes: $$\Theta{(|E|)}$$
overall = # of nodes + # of edges
- $$\Theta{(|V|+|E|)}$$

usually $$|E|\geq|V|-1$$


- example: undigraph
``` sequence
V1-V2: e12
V3-V2: e23
V4-V2: e24
V5-V4: e45
V2-V5: e25
V3-V6: e36
V2-V6: e26
V5-V6: e56
V2-V2: e22
```

```sequence
1->[2a]:
[2a]->[4a]:
[4a]->hat:
2->[1b]:
[1b]->[4b]:
[4b]->[6b]:
[6b]->[5b]:
[5b]->hat
3->[6c]:
[6c]->jat
4->[5d]:
[5d]->[1d]:
[1d]->[2d]:
[2d]->jat
5->[2e]:
[2e]->[6e]:
[6e]->[4e]:
[4e]->jat
6->[2f]:
[2f]->[3f]
[3f]->[5f]
[5f]->jat
```





