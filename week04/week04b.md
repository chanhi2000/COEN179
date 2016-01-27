# **week04b**

## HEAPSORT
Given an array of $$n$$ elements
$$
    a[1],\:a[2],\:\cdots,a[n]
$$
it goes in the order as such.
$$
a[1]\\
a[2]\:\:\:\:\:\:\:\:\:\:\:\:a[3]\\
a[4]\:\:\:\:a[5]\:\:\:\:a[6]\:\:\:\:a[7]\\
\vdots
$$
so it's fair to say, in general, our tree would looks like
$$
a\left[\left\lfloor\frac{i}{2}\right\rfloor\right]\\
\vdots\\
a[i]\\
a[2i]\:\:\:\:\:\:\:a[2i+1]\\
\vdots
$$
We want to engineer the ordering such that
$$
    \begin{matrix}
    a[i]\geq{a}[2i]\\
    \text{and}\\
    a[i]\geq{a}[2i+1]
    \end{matrix}
    \:\:\:\:\forall{i}
$$
#### EXAMPLE#1: RANDOM
$$
    R\\
    O\:\:\:\:\:\:\:\:\:\:\:\:A\\
    N\:\:\:\:\:\:D\:\:\:\:\:\:M\:\:\:\:\:\:
$$
there are many valid choices for heap construction. It's good for us.

###### 1ST APPROACH: **top-down approach**

- let's look at the first entry $$a[1]$$. This one particular entry by itself is a heap.
- I want the first two entries $$a[1],\:\:a[2]$$ to be a heap where, you continue to the next step if
$$
    a[1]\geq{a}[2]
$$
- add new one more entry *e.g.* $$a[3]$$ where you continue to the next step if 
$$
    a[1]\geq{a}[3]
$$
otherwise swap $$a[1]$$ with $$a[1]$$.
- add another new entry *e.g.* $$a[4]$$ where you continue to the next step if 
$$
    a[4]\geq{a}[2]
$$
otherwise swap $$a[2]$$ with $$a[4]$$.

- ANALOGY: BOXING CHAMPIONSHIPS
 - WBA, WBC,
 - heavy-weight, light-weight.
 - *Mike Tyson* who's better than anybody, comes up to the top.
 - Once he heads up in one direction and is already on the top, he wouldn't bother to battle anymore. (i.e. no reason to fight the bottoms)


- all we need to do is 
    - maintain $$a[1],\:\:a[2],\:\:\cdots,a[n]$$ as a heap, 
    - repeatedly add entry $$a[i+1]$$ by comparing parent to child
    - swap parent and child when necessary.
    - repeat until, either the new element loses a comparison, or if it reaches the top.  

###### 2nd approach: bottom-up approach
- full of *children* initially. (individual heap, whose size is 1).
- tournament style of building heap.
- **bad side**: one that loses the comparison can move its way down A LOT.  There are comparisons with sub-heaps waiting to contend.


###### big-O: 1st vs 2nd
 - result:  bottom-up is better.  fewer steps of O(2nd).
 - top-down: $$O(n)$$
 - binary tree: a lot of stuff is going on at the bottom.  
 - **top-down**: doing a lot of activities at the bottom at the end. 
 - **bottom-up**:  fewer things to swap later on, although there's a lot of activities in the beginning.

###### big-O: 1st (top-down)
steps diagram
$$
0\\
1\:\:\:\:\:\:\:\:\:\:\:\:1\\
2\:\:\:\:2\:\:\:\:2\:\:\:\:2\\
\vdots
$$
let $$k$$ as depth of the tree. Then the # of steps, $$n$$ in terms of $$k$$ will be.
$$
    2^k\leq{n}<2^{k+1}\\
    k\leq\log_{2}{n}<k+1\\
    k=\left\lfloor\log_{2}{n}\right\rfloor
$$
$$
    \begin{align*}
    &\sum_{i}^{k-1}{i\cdot2^i+\#\text{ of leftover }k\text{'s}}\\
    =&\sum_{i}^{k-1}{i\cdot2^i+k(n-2^k+1)}
    \end{align*}
    
$$

| $$k$$ bits| equivalent |
|-----------|------------|
|11111110   | $$2^k-2$$  |
|11111100   | $$2^k-4$$  |
|11111000   | $$2^k-8$$  |
|$$\vdots$$ | $$\vdots$$ |
|10000000   | $$2^k-2^{k-1}$$|
$$
    \begin{align*}
    &\sum_{i}^{k-1}{i\cdot2^i+\#\text{ of leftover }k\text{'s}}\\
    =&\sum_{i}^{k-1}{i\cdot2^i+k(n-2^k+1)}\\
    =&(k-1)2^k-(2^k-2)+k(n-2^k+1)\\
    =&2^k-2^k+2+kn+k=kn-2\cdot2^k+k+2=\Theta(n\log{n}){}
    \end{align*}
$$