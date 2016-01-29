# week04c

## HEPASORT 
###### big-O: 2nd (bottom-up)
- **worst case**:
every new entry rises up and falls to the bottom

$$
2^k\leq{n}<2^{k-1}
$$
- \# of parents: $$\left\lfloor\frac{n}{2}\right\rfloor$$
- \# of grandparents: $$\left\lfloor\frac{\left\lfloor\frac{n}{2}\right\rfloor}{2}\right\rfloor$$
- \# of great-grandparents: 
$$\left\lfloor\frac{\left\lfloor\frac{\left\lfloor\frac{n}{2}\right\rfloor}{2}\right\rfloor}{2}\right\rfloor$$
- in general, **the worst case # of swaps**
$$
    \begin{align*}
    n&=\left\lfloor\frac{n}{2}\right\rfloor+ \left\lfloor\frac{\left\lfloor\frac{n}{2}\right\rfloor}{2}\right\rfloor+\left\lfloor\frac{\left\lfloor\frac{\left\lfloor\frac{n}{2}\right\rfloor}{2}\right\rfloor}{2}\right\rfloor+\cdots
    \end{align*}
$$
$$
    \vdots\\
    \left\{\begin{align*}
    n&=b_k+b_{k-1}+\cdots+b_2+b_1;\\
    \left\lfloor\frac{n}{2}\right\rfloor&=b_k+b_{k-1}+\cdots+b_2+0;\\
    \left\lfloor\frac{\left\lfloor\frac{\left\lfloor\frac{n}{2}\right\rfloor}{2}\right\rfloor}{2}\right\rfloor&=b_k+b_{k-1}+\cdots+b_3+0;
    &\vdots
    \end{align*}\right\}\\\vdots
$$
$$
    \begin{align*}
    n&=(b_k)\left(2^{k-1}-1\right)+(b_{k-1})\left(2^{k-2}-1\right)+\cdots+b_2(2-1)+b_1(1-1)\\
    &=b_k(2^{k-1})+\cdots+b_{2}2^{1}+b_{1}2^{0}
    \end{align*}
$$
    - repeatedly decapitate the heap
    - repair the heap on one fewer entry
    - swap if it's out of order.
    - repeat this process
$$
    \begin{align*}
    n&=\log_{2}{n}+\log_{2}{(n-1)}+\log_{2}{(n-2)}+\cdots+\log_{2}{(2)}+\log_{2}{(n)}\\
    &=\log_{2}{(n!)}=\Theta{(n\log{n})}
    \end{align*}
$$


## SEARCH AN ARRAY
 - **problem**: given an array $$a[n]$$ and a key and dictionary of the key is in the array.
 - **input**: array, valuey=key
 - **output**: $$i$$ where 
$$
    \begin{cases}a[i]=\text{key}&\text{if found}\\\text{sorry}&\text{otherwise}\end{cases}
$$

#### SEQUENTIAL SEARCH
 - **worst-case**: $$n$$ comparison
 - **best-case**: $$1$$ comparison
 - **average-case**: 
    - **[1]**: the key is equally likely to appear in any of the array 
    - **[2]**: The probability of the no-found case is known. 
        - call $$p$$ the probability that key will be found
        - call $$1-p$$ the probability that key will NOT be found.
$$
    \begin{matrix}
    \text{entry}&P(X)&\#\text{ of steps}\\
    \hline
    a[1]&\frac{p}{n}&1\\
    a[2]&\frac{p}{n}&2\\
    a[3]&\frac{p}{n}&3\\
    \vdots&\vdots&\vdots\\
    a[n]&\frac{p}{n}&n\\
    \text{sorry}&1-p&n
    \end{matrix}
$$
$$
    \begin{align*}
    E(X)&=\sum_{i=1}^{n}{x(P(X))}+(1-p)n\\
    &=\frac{p}{n}(1)+\frac{p}{n}(2)+\frac{p}{n}(3)+\cdots+\frac{p}{n}(n)+(1-p)n\\
    &=\frac{p}{n}\left(1+2+\cdots+n\right)+(1-p)n\\
    &=\frac{p}{n}\frac{(n)(n+1)}{2}+(1-p)n\\
    &=\frac{p(n+1)}{2}+(1-p)n
    \end{align*}
$$
Can we do better than this? IF the array is sorted... 

#### BINARY SEARCH
 - pick what's in the middle 
 - do recursive search on one-half of the array
    - $$T(n)=1+T\left(\left\lceil\frac{n-1}{2}\right\rceil\right)=1+T\left(\left\lceil\frac{n}{2}\right\rceil\right)$$
    - master theorem...
$$
    T(n)=T\left(\frac{n}{2}\right)+1\\
    \log_{b}{a}=\log_{2}{1}=0;\\
    T(n)=\Theta{\left(n\log{(n)}\right)}=\Theta{\left(\log{(n)}\right)}
$$
 - do the other likewise.