# **week01**

## FIBONACCI NUMBER
- $$F_0=0$$,     $$F_1=1$$
- $$\begin{align*}F_n=F_{n-1}+F_{n-2}    ,&&n\geq2\end{align*}$$
- 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, …
- **problem (recursive)**: bad, because of redundancy, high latency
- **solution (iterative)**: temporary storage


## ALGORITHM 
- **define**: a finite sequence of steps(?) which solves a problem
- it seeks PLATFORM / TIME DURATION independence
- *does steps have to be more than 1?* **NO** 
- *does algorithm needs to stop?* **YES**


#### THE SIZE OF THE ALGORITHM
- number of steps
- speed
- how to measure your efficiency of algorithm?


#### BIG O
- $$\begin{align*}f(n)=O(g(n)),&&{n}\geq{N}\end{align*}$$
    - $$n$$: size of the input    
- **define**:
    - there exist constant $$C$$ and $$N$$ such that
$$
    \begin{align*}
    f(n)\geq{C}\cdot{g(n)},&&\forall{n}\geq{N}.
    \end{align*}
$$
        - “$$f(n)\geq{C}\cdot{g}(n)$$”: **essentially**.
        - “$$\forall{n}\geq{N}$$“: **eventually**.
    * we need to make a **tradeoff** for the worst case, but it still does NOT matter.


#### FUNCTION 1
- 1 step, not many 
- $$O(1)$$:
    - there exist constant C and N such that 
$$
    \begin{align*}
    f(n)\geq{C}\cdot{1},&&\forall{n}\geq{N}.
    \end{align*}
$$
    - BOUNDED
    - fastest algorithm


#### LOG B of n
- u = logbn;  bu =n
* u ln(b)=ln(bu)=ln(n)
* n=\frac{ln(n)}{ln(b)}=\frac{\log_{10}{\left(n\right)}}{\log_{10}{\left(b\right)}}=\frac{\log_{2}{\left(n\right)}}{\log_{2}{\left(b\right)}}
* O(1) is better than O(log n)