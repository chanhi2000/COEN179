# **week03c**

## QUICKSORT
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
    1+\frac{1}{2}+\frac{1}{3}+\cdots+\frac{1}{n}=\ln{(n)}+\epsilon_{n}\\\text{where  }0<\epsilon_n<1\end{align*}
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
