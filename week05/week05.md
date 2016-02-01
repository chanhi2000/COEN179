# week05

## Sequential Search
- worst case: $$n$$
- average case: 

## Binary search
- worst case: $$\Theta{(\log{(n)})}$$.
$$
\begin{align*}
T(n)&=T\left(\left\lfloor\frac{n-1}{2}\right\rfloor\right)+1\\
&=T\left(\left\lfloor\frac{n}{2}\right\rfloor\right)+1\\
\end{align*}
$$
- we want exact solution to this recurrance.
- $$n=b_k, b_{k-1},\cdots,b_1\:\:\:\text{(k-bit expansion)}$$
- So
$$
\begin{align*}
T(n)&=1+T(b_k, b_{k-1},\cdots,b_2)\\
&=1+1+T(b_k, b_{k-1},\cdots,b_3)\\
&=1+1+1+T(b_k, b_{k-1},\cdots,b_4)\\&\vdots\\
&=(1)(k-1)+T(b_k)\\
&=k-1+T(1)=k; 
\end{align*}
$$
- So $$T(n)$$: # of bits in the binary represenation of n.
$$
2^{k-1}\leq{n}<2^k\\
k-1\leq\log_{2}{(n)}<k\\
k-1=\left\lfloor\log_{2}{(n)}\right\rfloor\\
k=1+\left\lfloor\log_{2}{(n)}\right\rfloor
$$
**Proposition**: any algorithm which searches a **sorted** array with comparison takes at least $$1+\left\lfloor\log_{2}{(n)}\right\rfloor$$ comparisons.

$$
a[i]\:?\:key\\
O\:\:\:\:\:\:\:\:\:O\\
O\:\:\:\:O\:\:\:\:O\:\:\:\:O
$$

if $$k$$ is the number of comparisons performed, then we must have 
$$
2^k\geq{n+1}>n
2^k>n
$$
so the binary representation of $$n$$ has at most k bits.

$$
a[end]\:?\:key\\
a[mid]\:?\:key\:\:\:\:\:\:\:\:\:a[mid]\:?\:key\\
O\:\:\:\:O\:\:\:\:O\:\:\:\:O
$$

####EX: 
- n=13
$$
7\\
3\:\:\:\:\:\:\:\:\:10\\
1\:\:\:\:5\:\:\:\:\:\:\:\:8\:\:\:\:12\\
2\:\:\:\:4\:\:\:\:6\:\:\:\:9\:\:\:\:11\:\:\:\:13\\
$$
- **1st level**: $$1/13$$ chance of 1 comparison
- **2nd level**: $$2/13$$ chance of 2 comparisons
- **3rd level**: $$4/13$$ chance of 3 comparisons
- **4th level**:  $$6/13$$ chance of 4 comparisons
$$
\begin{align*}
E[\#\text{ of comparisons}]&=\left(\frac{1}{13}\right)(1)+\left(\frac{2}{13}\right)(2)+\left(\frac{4}{13}\right)(3)+\left(\frac{6}{13}\right)(4)\\
&=\left(\frac{1}{3}\right)(1+4+12+24)=\frac{41}{13}=3\frac{2}{13}
\end{align*}
$$

for a general $$n$$: 
- $$k$$: # of bits
- so $$2^{k-1}\leq{n}<2^k$$
- probability of $$\frac{1}{n}$$ of array 1 comparison.
- probability of $$\frac{2}{n}$$ of array 2 comparisons.
- probability of $$\frac{4}{n}$$ of array 3 comparison.
- $$\vdots$$
- probability of $$\frac{2^{k}}{n}$$ of array $$k-1$$ comparison
- prbability of $$\frac{n-2^{k}+1}{n}$$ of $$k$$ comparison

$$
\begin{align*}
E[\#\text{ of comparisons}]&=\left(\frac{1}{n}\right)(1)+\left(\frac{2}{n}\right)(2)+\cdots+\left(\frac{2^{k-2}}{n}\right)(k-1)+\left(\frac{n-2^{k-1}+1}{n}\right)(k)\\
&=\frac{(k-2)2^{k-1}+1}{n}+\frac{n-2^{k-1}+1}{n}(k)\\
&=\frac{nk-2^k+1+k}{n}\\
&=k-\left[\frac{2^k-k-1}{n}\right];
\end{align*}
$$
$$
\begin{matrix}&&&&1&1\\
&&&10&10&2\\
&&100&100&100&3\\
&&&\vdots&&\\
10\cdots0&100\cdots0&\cdots&\cdots&10\cdots{b}&k-1
\end{matrix}
$$

## RANDOMLY GENERATED TREE
- take the first array and use it for the first comparison
- 