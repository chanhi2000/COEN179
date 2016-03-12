# [algorithm]dijkstra


> #### ALGORITHM  `Dijkstra`($$G,\:s$$)
```
//Dijkstra’s algorithm for single-source shortest paths
//Input:	A weighted connected graph G = ⟨V , E⟩ with nonnegative weights 
//		and its vertex s
//Output:	The length dv of a shortest path from s to v
//		and its penultimate vertex pv for every vertex v in V 
```

> //initialize priority queue to empty
> Initialize(Q) 

> **for** every vertex $$v$$ in $$V$$
>> dv ←∞; pv ←null
Insert(Q, v, dv) //initialize vertex priority in the priority queue
ds ← 0; Decrease(Q, s, ds) //update priority of s with ds VT ←∅
for i ← 0 to |V | − 1 do
u∗ ← DeleteMin(Q) //delete the minimum priority element VT ←VT ∪{u∗}
for every vertex u in V − VT that is adjacent to u∗ do
ifdu∗ +w(u∗,u)<du
du ←du∗ +w(u∗,u); pu ←u∗ Decrease(Q, u, du)