# [algorithm]height

> #### ALGORITHM `Height`($$T$$)
```
//Computes recursively the height of a binary tree
//Input:    A binary tree T
//Output:   The height of T
```
> **if** $$T=\varnothing$$
>> **return** -1

> **else**
>> **return** **max**{`Height`($$T_\text{left}$$), `Height`($$T_\text{right}$$)}$$+1$$
