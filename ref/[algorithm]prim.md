# [algorithm]prim

> #### ALGORITHM `Prim`($$G$$)
```
//Prim’s algorithm for constructing a minimum spanning tree
//Input:    A weighted connected graph G=⟨V ,E⟩
//Output:   E_T , the set of edges composing a minimum spanning tree of G
```
> $$V_T\leftarrow\{v_0\}$$
//the set of tree vertices can be initialized with any vertex

> $$E_T\leftarrow\varnothing$$

> **for** $$i\leftarrow1$$ **to** $$|V|-1$$ **do**
>> find a minimum-weight edge $$e^∗=(v^∗,\:u^∗)$$ among all the edges $$(v,\:u)$$ such that $$v$$ is in $$V_T$$, and $$u$$ is in $$V-V_T$$

>> $$V_T\leftarrow{V}_T\cup\{u^∗\}$$
>> $$E_T\leftarrow{E}_T\cup\{e^∗\}$$

> **return** $$E_T$$
