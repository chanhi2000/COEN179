# week07c

#### backval of node
![fig01](week05/[COEN179]week07c-fig01.png)

- $$\text{val}(v)=\text{order when encountered by DFS}$$
$$
\begin{align*}
\text{backval}(v)&=\text{min}\left(\text{val}(w),\:\text{val}(w),\:\text{val}(w)\right)\\
&=\text{min}\left(\text{val}(v),\:\text{val}(w),\:\text{backval}(c)\right)\:\:\:\:c\:\text{is a child of }v
\end{align*}
$$
- Suppose there is some child $$c$$ such that \text{backval}(c)\geq\text{val}(p)
- Then deleting $$P$$ separates $$C$$ from the root, so $$P$$ is an articulation node.
- if no child $$C$$ satisfies this that all children of $$P$$ satisfies $$\text{backval}(C)<\text{val}(P)$$, then $$P$$ is not an articulation node.
- if $$P\neq\text{root}$$


## BREATH-FIRST SEARCH TREE
![fig02](week05/[COEN179]week07c-fig02.png)
![fig03](week05/[COEN179]week07c-fig03.png)

## LAYERED TREE
![fig04](week05/[COEN179]week07c-fig03.png)

- the distance between the root of the BFS and any other vertex is simply the generation of the vertex in the BFS tree
- **Shortest path problem**:
given a weighted graph, find the cheapest path from any vertx to any other vertex.
	- what if the weights are non-negative, can we approach this more simply?