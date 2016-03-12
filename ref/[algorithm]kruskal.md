# [algorithm]kruskal

> #### ALGORITHM `Kruskal`($$G$$)
```
//Kruskal’s algorithm for constructing a minimum spanning tree
//Input:    A weighted connected graph G=⟨V , E⟩
//Output:   the set of edges composing a minimum spanning tree of G sort E in nondecreasing order of the edge weights w(e_i_1)≤...≤ w(e_i_|E|)
```
> // initialize the set of tree edges and its size
> $$E_T\leftarrow\varnothing$$;
> $$\text{encounter}\leftarrow0;	

> //initialize the number of processed edges
> $$k\leftarrow0;$$ 

> **while** $$\text{encounter}<|V|-1$$ **do**
>> $$k\leftarrow{k}+1;
>> **if** $$E_{T}\cup\{e_{i_k}\}$$ is acyclic
>>> E_T\leftarrow{E}_T\cup\{e_{i_k}\};

> **return** $$E_T$$
