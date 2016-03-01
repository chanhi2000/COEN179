# Strassen's Algorithm
A, B, C  are  $$2\times2$$  matrices.
We compute $$C=AB$$ as follows

$$
\begin{align*}
x_1&=(a_{11}+a_{22})(b_{11}+b_{22})\\
x_2&=(a_{21}+a_{22})b_{11}\\
x_3&=a_{11}(b_{12}-b_{22})\\
x_4&=a_{22}(b_{21}-b_{11})\\
x_5&=(a_{11}+a_{12})b_{22}\\
x_6&=(a_{21}-a_{11})(b_{11}+b_{12})\\
x_7&=(a_{11}-a_{22})(b_{21}+b_{22})\\
\end{align*}
$$

#### Define
$$
\begin{align*}
c_{11}&=x_1+x_4-x_5+x_7\\
c_{21}&=x_2+x_4\\
c_{12}&=x_3+x_5\\
c_{22}&=x_1+x_3-x_2+x_6\\
\end{align*}
$$

This computes $$C$$  with 7 multiplications and 18 additions
