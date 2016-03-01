# hw03a

## 5.3.2
The following algorithm seeks to compute the number of leaves in a binary tree.
#### ALGORITHM `LeafCounter`($$T$$)
> //Computes recursively the number of leaves in a binary tree
> //Input: A binary tree $$T$$
> //Output: The number of leaves in $$T$$

**if** ($$T=\varnothing$$) **return** 0

**else** **return** `LeafCounter`($$T_\text{left}$$)+`LeafCounter`($$T_\text{right}$$)

Is this algorithm correct? If it is, prove it; if it is not, make an appropriate correction.

