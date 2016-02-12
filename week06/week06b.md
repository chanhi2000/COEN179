# week06b 

## GRAPHS

- Secondary Graph
    - depth-first serach (DFS)
    	- [example](http://web.cse.ohio-state.edu/~gurari/course/cis680/cis680Ch14.html)
    	- looking for the new place to go
    - breadth-first search
    	- looking for the neighbors nearby
	- *path*: list of pairwise adjacent vertices
	- *cycle*: a path that ends where it begins.
	- cycle-free graph that includes all vertices of a connected graph is called *tree*.
	- disconnected  -> forest
	- *r*: path connecting some pair == disconnected.

	- DFS -> recursion


	$$DFS(\:G(V,E),\:v_0)$$
	 - mark $$v_0$$ as visited.
	 - find an unvisited vertex adjecent to $$v_0$$
	 - if find , $$DFS(\:G(V,E),\:v_1)$$
	 - otherwise, return (go back)



## MIDTERM
- big(O), Theta, Omega
- master theorem
- 
