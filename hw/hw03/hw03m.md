# hw03m

## custom.01.
Give the state of the disjoint-sets data structure after the following sequence of operations, starting from singleton sets $$\{a\},\:\{b\},\:\{c\},\:\{d\},\:\{e\},\:\{f\},\:\{g\},\:\{h\},\:\{i\},\:\{j\}$$ Use path compression.  In case of ties, always make the lower-numbered node point to the higher-numbered node.
$$
\begin{matrix}
\text{union}(a,b),&\text{union}(c,d),&\text{union}(e,f),\\
\text{union}(g,h),&\text{union}(i,j),&\text{union}(a,d),\\
\text{union}(f,g),&\text{union}(b,i),&\text{union}(d,e),\\
\text{find}(a).
\end{matrix}
$$

