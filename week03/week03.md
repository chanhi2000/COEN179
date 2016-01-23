# **week03**

## Last time
- #### master theorem:
$$
    
    T(n)=aT\left(\frac{n}{b}\right)+f(n)\\
    T(n)=\underset{\Theta(n^{\left(\log_{a}{b}\right)})}{\underline{\left[a^kT\left(\frac{n}{b^k}\right)\right]}}+\underset{?}{\underline{f(n)+af\left(\frac{n}{b}\right)+a^2f\left(\frac{n}{b^2}\right)+\cdots+a^{k-1}f\left(\frac{n}{b^{k-1}}\right)}}\\
    \\

    b^k\leq{n}<b^{k+1}\\
    k=\left\lfloor\log_{b}{n}\right\rfloor
$$

- #### case#1:
if 
$$
    \begin{align*}
    f(n)&=O\left(n^{\log_{b}{a-\epsilon}}\right),&&\epsilon>0.\\
    f\left(\frac{n}{b}\right)&=O\left(\left(\frac{n}{b}\right)^{\log_{b}{a-\epsilon}}\right)=O\left(\frac{n^{\log_{b}{a-\epsilon}}}{b^{\log_{b}{a-\epsilon}}}\right)\\
    &=O\left(\frac{n^{\log_{b}{a-\epsilon}}}{a\cdot{b}^{-\epsilon}}\right)\\
    af\left(\frac{n}{b}\right)&=O\left(\frac{n^{\log_{b}{a-\epsilon}}}{b^{-\epsilon}}\right)=O\left(n^{\log_{b}{a-\epsilon}}\cdot{b^\epsilon}\right)
    \end{align*}
$$

$$
    O(n^{\log_{b}{a-\epsilon}})=(1+b^\epsilon+\left(b^\epsilon\right)^2+\left(b^\epsilon\right)^3)+\cdots+\left(b^\epsilon\right)^{k-1})
$$

GEOMETRIC SERIES
$$
    \begin{align*}
    S&=1+r+r^2+r^3+\cdots+r^{k-1}\\
    rS&=r+r^2+r^3+\cdots+r^{k}\\
    rS-S&=r^k-1;\\
    S(r-1)=r^k-1\\
    S&=\frac{r^k-1}{r-1},&&\left<r=b^{\epsilon}\right>\\
    &=\frac{(b^\epsilon)^k-1}{(b^\epsilon)-1}=\Theta(n^\epsilon)
    \end{align*}
$$
- #### case#2
if 
$$
    \begin{align*}
    f(n)&=O\left(n^{\log_{b}{a}}\right),&&\epsilon>0.\\
    f\left(\frac{n}{b}\right)&=O\left(\left(\frac{n}{b}\right)^{\log_{b}{a}}\right)=O\left(\frac{n^{\log_{b}{a}}}{b^{\log_{b}{a}}}\right)\\
    &=O\left(\frac{n^{\log_{b}{a-\epsilon}}}{a}\right)\\
    af\left(\frac{n}{b}\right)&=\Theta\left(n^{\log_{b}{a}}\right)
    \end{align*}
$$

- #### case#3
if 
$$
    \begin{align*}
    f(n)&=O\left(n^{\log_{b}{a+\epsilon}}\right),&&\epsilon>0.\\
    f\left(\frac{n}{b}\right)&=O\left(\left(\frac{n}{b}\right)^{\log_{b}{a+\epsilon}}\right)=O\left(\frac{n^{\log_{b}{a+\epsilon}}}{b^{\log_{b}{a+\epsilon}}}\right)\\
    &=O\left(\frac{n^{\log_{b}{a+\epsilon}}}{a\cdot{b}^{\epsilon}}\right)\\
    af\left(\frac{n}{b}\right)&=O\left(\frac{n^{\log_{b}{a+\epsilon}}}{b^{\epsilon}}\right)=O\left(n^{\log_{b}{a+\epsilon}}\cdot{b^\epsilon}\right)
    \end{align*}
$$

Automatically
$$
    T(n)=\Omega(f(n))=\Omega(n^{\log_{b}{a}+\epsilon});
    
$$
in order to calculate taht
$$
    T(n)=\Theta(f(n))
$$
We use what's known as a **regularity condition**

if there is some constant $$c<1$$ such that,
$$
    af\left(\frac{n}{b}\right)\ll{c}{f}(n)\\
     a^2f\left(\frac{n}{b^2}\right)<cf\left(\frac{n}{b}\right)<c^2f(n)\\
     \therefore{T}(n)=\Theta{(f(n))}
$$
because the second term is bound by some c that are folowing f(n)*()


- #### example#1
use the master theorem to solve the following recur:

    1. $$T(n)=8T(\frac{n}{2})+5n^2\log{n}$$
    2. $$T(n)=8T(\frac{n}{2})+5n^3$$
    3. $$T(n)=8T(\frac{n}{2})+5n^4$$

**ex1.1** case#1
$$
    \log_{b}{a}=\log_{(2)}{(8)}=3;\\
    f(n)=O(n^{3-\epsilon})\\
    n^2\log{n}=O(n^{2.1})\:\:\:\epsilon=0.9;\\
    \therefore{T}(n)=\Theta{(n^3)}
    
$$

**ex1.2**
case 2
$$
    T(n)=\Theta(n^3\log{n})
$$

**ex1.3**
case 3
$$
    f(n)=5\cdot{n^4};\\
    af(\frac{n}{b})=8\cdot5\left(\frac{n}{2}\right)^4=\frac{1}{2}(5\cdot{n^4})=\frac{1}{2}f(n),\:\:c=\frac{1}{2}\\
    f(n)=5\cdot{n^4};
    \therefore{T}(n^4)=\Omega{(n^3)}
$$

## QUICKSORT

#### description: QUICKSORT
- let's figure out what goes in the middle.
- then put smallest and biggest on the both side.
- then sort the smallest group and biggest group.
- **backward "merge sort"**

> **Q1**: what goes in the middle?
- go through everything
- order $$n$$ comparison

> **Q2**: if $$n\gg{c}$$
- smaller ones are okay, but the number of targest become bigger, it's impossible to do it any quicker way.

- **LET'S GET LUCKY** and hope that one we pick randomly will be our middle.

> **Q3**: can we do the sorting while comparing with our "arbitrary middle value"?
* Yes. we might as well.

- worst-case: $$O(n^2)$$
- best-case: $$O(n\log{n})$$
- average-case: ??

#### algorithm: QUICKSORT
1. pick a pivot entry
2. place all smaller entries to the left
3. place all larger entries to the right
4. place the pivot
5. quicksort to the left and 
6. quick sort to the right

```c
void quicksort(char a[], int left, int right)
{
    int i,j;  char v;
    if (right > left) {
	    v = a[right]; 
	    i = left-1; 
	    j = right;
	    for (;;) {
	        while (a[++i] < v);
	        while (a[--j] > v);
	        if (i >= j) break;
	        swap(a, i, j);
	    }
	    swap(a, i, right);
	    quicksort(a, left, i-1);
	    quicksort(a, i+1, right);
    }
}
```
>[see here](http://math.scu.edu/~bwalden/alg/quick.html) to see the example process.
- right: sentinel pivot
- left: cursor

#### worst case: QUICKSORT
- start with array in **reverse** order 
- $$O(n^2);$$
- not quick.

#### average case: QUICKSORT
- how m
- $$X_n$$ as a the number of comparisons to "quicksort" an array of $$n$$ entries.
$$
    \begin{align*}
    E(X_n)&=
    \begin{matrix}\text{expected }\#\text{ of}\\\text{comparisons}\\\text{to place the pivot}\end{matrix}+\begin{matrix}\text{expected }\#\text{ of}\\\text{comparisons}\\\text{to quicksort the left}\end{matrix}+\begin{matrix}\text{expected }\#\text{ of}\\\text{comparisons}\\\text{to quicksort the right}\end{matrix}\\
    \end{align*}
$$
- assume any entry can be in the right most slot with probability $$\frac{1}{n}$$.
$$
    \begin{align*}
    E(X_n)&=n+1+\left[\frac{2}{n}\left(E(x_1)+E(x_2)+\cdots+E(x_{n-1})\right)\right];\\
    nE(X_n)&=n(n+1)+\left[2\left(E(x_1)+E(x_2)+\cdots+E(x_{n-1})\right)\right];\\
    (n-1)E(X_{n-1})&=(n-1)n+\left[2\left(E(x_1)+E(X_2)+\cdots+E(x_{n-2})\right)\right];\\
    nE(X_n)-(n-1)E(X_{n-1})&=2n+2E(X_{n-1});\\
    nE(X_n)-(n+1)E(X_{n-1})&=2n\\
    nE(X_n)&=(n+1)E(X_{n-1})+2n;\\
    \end{align*}
$$
- for comparison
$$
    \left\{
    \begin{align*}
    nE(X_n)&=(n+1)E(X_{n-1})\\
    E(X_n)&=\frac{n+1}{n}E(X_{n-1})\\
    E(X_{n-1})&=\frac{n}{n-1}E(X_{n-2})\\
    E(X_{n-2})&=\frac{n-1}{n-2}E(X_{n-3})\\
    &\vdots
    \end{align*}\right\}
$$
$$
    \begin{align*}
    E(X_n)&=\frac{n+1}{n}E(X_{n-1})\\
    &=\frac{n+1}{n}\frac{n}{n-1}E(X_{n-2})\\
    &=\frac{n+1}{n}\frac{n}{n-1}\frac{n-1}{n-2}E(X_{n-3})\\
    &\vdots
    \end{align*}
$$
$$
    \begin{align*}
    \left(\frac{1}{n(n+1)}\right)nE(X_n)&=\left(\frac{1}{n(n+1)}\right)\left[(n+1)E(X_{n-1})+2n\right];\\
    \frac{E(X_n)}{n+1}&=\frac{2}{n+1}+\frac{E(X_{n-1})}{n};\\
    \end{align*}
$$
$$
    \left\{
    \begin{align*}
    \frac{E(X_{n-1})}{n}&=\frac{2}{n}+\frac{E(X_{n-2})}{n-1};\\
     \frac{E(X_{n-2})}{n-1}&=\frac{2}{n-1}+\frac{E(X_{n-3})}{n-2};\\
    &\vdots
    \end{align*}\right\}
$$
$$
    \begin{align*}
    \frac{E(X_n)}{n+1}&=\frac{2}{n+1}+\frac{E(X_{n-1})}{n}\\
    &=\frac{2}{n+1}+\frac{2}{n}+\frac{E(X_{n-2})}{n-1}\\
    &=\frac{2}{n+1}+\frac{2}{n}+\frac{2}{n-1}+\frac{E(X_{n-3})}{n-2}\\
    &\vdots\\
    \end{align*}
$$
in [Euler–Mascheroni constant](https://en.m.wikipedia.org/wiki/Euler%E2%80%93Mascheroni_constant)
$$
    \left\{
    \begin{align*}
    1+\frac{1}{2}+\frac{1}{3}+\cdots+\frac{1}{n}=\ln{(n)}+\epsilon_{n}\\\text{where  }0<\epsilon_n<1
    
    \end{align*}
    \right\}
$$
$$
    \begin{align*}
    &\vdots\\
    \frac{E(X_n)}{n+1}&=\frac{2}{n+1}+\frac{2}{n}+\frac{2}{n-1}+\cdots+\frac{2}{3}+\frac{E(X_{2})}{3}\\
    &=2\ln{(n)}+C\\
    &=2\ln{(n)}+O(1)\\
    nE(X_n)&=2n\ln{(n)}+O(n);
    \end{align*}
$$

