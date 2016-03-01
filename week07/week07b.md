# week07b

Graph

- even if we have a connected graph, it may not be robust
- so nuke it... (find the vulnerable place to "attack")

## ARTICULATION NODE & BICONNECTION
- an **articulation node** in a connected graph is  one whose deletion along with associated edge leaves a disconnected subgraph.
- A graph that has no articulation node is called **"biconnected"**.
- biconnected component is a maximal biconnected subgraph.

## MODIFIED DFS
- to find articulate nodes and biconnected components. (i.e. use DFS on a stack)
- let 
$$
\begin{align*}
\text{val}(v)&=\text{value of vertex }v\\
&=\text{order in DFS that }v\text{ is visited}
\end{align*}
$$
- let 
$$
\text{backval}(v)=\text{back value of vertex }v
$$


#### DFS Tree
![fig03](week05/[COEN179]week07b-fig03.png)

- backedges cconnect direct descendants in the tree to an ancestor.
- crossedges  


#### DFS Stack
![fig04](week05/[COEN179]week07b-fig04.png)

$$
\begin{align*}
\text{backval}(v)&=\text{minimum of val}(w)\text{ for all vertices }w\\&\text{that terminate a path of tree edges followed by one backedge}.
\end{align*}
$$

#### backval of node
![fig05](week05/[COEN179]week07b-fig05.png)
- $$\text{backval}(1)=1$$
- $$\text{backval}(2)=1$$
- $$\text{backval}(3)=2$$
- $$\text{backval}(4)=2$$
- ...