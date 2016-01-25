# week04a

## COUNTING COMPARISONS: QUICKSORT
How to find the best case of quicksort?
#### APPROACH (growing like a binary tree)
- 1st COMPARISON
 - IF LESS, do this
    -  2nd COMPARISON (1)
        -  IF LESS,  do this
            -  ... [1]
        -  IF GRATER, do that
            -  ... [2]
 - IF GREATER, do that
    - 2nd COMPARISON (2)
        -  IF LESS,  do this
            -  ... [3]
        -  IF GRATER, do that
            -  ... [4]


#### DISCRETION
 - have **all the leaves** to cover all the possibilities.
 
|#COMPARISON|#ACTIONS  |
|-----------|----------|
|     1     |    2     |
|     2     |    4     |
|     3     |    8     |
|$$\vdots$$ |$$\vdots$$|
|   $$k$$   |  $$2^k$$ |

- in order to sort an array of $$n$$ entries with $$k$$ comparisons, we must have $$2^k\geq{n!}$$, or equivalently, 
$$
    k\geq\log_{2}{(n!)}
$$
note (less precise)
$$
\log_{2}{(n!)}=\Theta{(n\log_{2}{n})}
$$
note (more precise)
$$
\ln{(n!)}=\sum_{i=1}^{n}{\ln{i}}
$$
in graph we can see that
$$
\begin{align*}
\ln{(n!)}&=\sum_{i=1}^{n}{\ln{i}}=\int_{1}^{n}{\ln{(x)}dx}+\text{error};\\
&\left<\begin{matrix}u=\ln{(x)}&&dv=dx\\du=\left(\frac{1}{x}\right)dx&&v=x\end{matrix}\right>\\
&=\left.x\ln{(x)}\right|_{1}^{n}-\int_{1}^{n}{x\left(\frac{1}{x}\right)dx}+\text{error}\\
&=n\ln{(n)}-n+1+\text{error}\\
&=n\ln{(n)}-n+O{(\ln{(n)})}
\end{align*}
$$
since,
$$
    \lim_{n\to\infty}{\frac{\ln{(n!)}}{n\ln{(n)}}}=1
$$
back to note
$$
\therefore\log_{2}{(n!)}=n\log_{2}{(n)}-n+O(\log_{2}{n})
$$
"**perfect**" algorithm takes at least $$n\log_{2}{(n)}+O{(n)}$$ comparisons.
$$
    \Omega{(n\log_{2}{(n)})};
$$
compare perfect to average
$$
    \begin{align*}
    \lim_{n\to\infty}{\frac{2n\ln{n}}{n\log_{2}{(n)}}}&=\lim_{n\to\infty}\frac{2\frac{\log_2{(n)}}{\log_{2}{(e)}}}{\log_{2}{(n)}}\\
    &=\lim_{n\to\infty}\frac{2}{\log_{2}{e}}\\
    &=2\ln{(2)}\approx2(0.6931)\approx1.3862
    \end{align*}
$$
- #### Golf comparison
maintaining average of good strokes (68) and sometimes you get 120 strokes.
- #### In quicksort.
    - Most of the time, you are doing SO well that perfect algorithm isn't good compared to it.
    - in **perfect algorithm**, you can NEVER do the half amount of the steps of **average case**. (perfect, as in cutting the things in half exactly.)

#### SUMMARY: QUICKSORT
 - worst-case: $$\Theta(n^2)$$ 
 - average-case: $$2n\ln{n}+O(n)$$
 - best-case: $$n\log_{2}(n)+O(n)$$


## [HEAPSORT](https://www.cs.usfca.edu/~galles/visualization/HeapSort.html)
 - heap is a **data structure** organized into a (partial) binary tree
    1. all generations prior to the last have both children
    2. a
    3. if the node . if a left child.
 - used for building a priority
 - each node has a data element that can be compared with other nodes.