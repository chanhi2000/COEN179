# week09c

## MATRIX MULTIPLICATION
#### MATRIX
$$
A=[a_{i,j}]\:\:\:\:\begin{cases}1\leq{i}\leq{m}\\1\leq{j}\leq{n}\end{cases}
$$

A is an $$m\times{n}$$ matrix
- $$m$$: # of rows
- $$n$$: # of columns

$$
A=
\left[\begin{matrix}
a_{11}&a_{12}&a_{13}&\cdots&a_{1n}\\
a_{21}&a_{22}&a_{23}&\cdots&a_{2n}\\
\vdots&&\ddots&&\\
a_{m1}&a_{m2}&a_{m3}&\cdots&a_{mn}\\
\end{matrix}\right]
$$

#### MATRIX ADDITION
$$\begin{align*}
A+B&=\left[\begin{matrix}
a_{11}&a_{12}&a_{13}&\cdots&a_{1n}\\
a_{21}&a_{22}&a_{23}&\cdots&a_{2n}\\
\vdots&&&\ddots&\\
a_{m1}&a_{m2}&a_{m3}&\cdots&a_{mn}\\
\end{matrix}\right]+
\left[\begin{matrix}
b_{11}&b_{12}&b_{13}&\cdots&b_{1n}\\
b_{21}&b_{22}&b_{23}&\cdots&b_{2n}\\
\vdots&&&\ddots&\\
b_{m1}&b_{m2}&b_{m3}&\cdots&b_{mn}\\
\end{matrix}\right]\\
&=\left[\begin{matrix}
a_{11}+b_{11}&a_{12}+b_{12}&a_{13}+b_{13}&\cdots&a_{1n}+b_{1n}\\
a_{21}+b_{11}&a_{22}+b_{12}&a_{23}+b_{23}&\cdots&a_{2n}+b_{2n}\\
\vdots&&&\ddots&\\
a_{m1}+b_{m1}&a_{m2}+b_{m2}&a_{m3}+b_{m3}&\cdots&a_{mn}+b_{mn}
\end{matrix}\right]
\end{align*}
$$

ijth entry of A+B=a_{ij}+b_{ij}

- $$m\cdot{n}$$ additions to add two $$m\times{n}$$ matrices


#### MATRIX MULTIPLICATION
- if $$A$$ a $$m\times{n}$$ matrix,
    - then $$B$$ must be $$n\times{p}$$ matrix
    - The matrix $$C=AB$$ will going to be $$m\times{p}$$ matrix
$$
\begin{align*}
B&=[b_{j,k}]\:\:\:\:\begin{cases}1\leq{j}\leq{n}\\1\leq{k}\leq{p}\end{cases}\\
C&=AB=[c_{i,k}]\:\:\:\:\begin{cases}1\leq{i}\leq{m}\\1\leq{k}\leq{p}\end{cases}\\
\end{align*}
$$

ijth entry of C
$$
\begin{align*}
c_{ik}=a_{i1}b_{1k}+a_{i2}b_{2k}+a_{i3}b_{3k}+\cdots+a_{in}b_{nk}=\sum_{j=1}^{n}{a_{ij}b_{jk}}
\end{align*}
$$

In the definition, each entry of $$C$$ uses
 - $$n$$ multiplications and
 - $$n-1$$ additions.

All together, this makes
 - $$m\cdot{n}\cdot{p}$$ multiplication and
 - $$m\cdot(n-1)\cdot{p}$$ additions

if $$m=n=p$$:
 - $$n^3$$ multiplications
 - $$n^2(n-1)$$ additions
 - _$$\therefore{\Theta(n^3)}$$

#### SPECIAL CASE: $$2\times2$$ matrices.
$$
\begin{align*}
A\times{B}&=\left[\begin{matrix}
a_{11}&a_{12}\\
a_{21}&a_{22}
\end{matrix}\right]
\left[\begin{matrix}
b_{11}&b_{12}\\
b_{21}&b_{22}
\end{matrix}\right]=
\left[\begin{matrix}
c_{11}&c_{12}\\
c_{21}&c_{22}
\end{matrix}\right]
\end{align*}
$$

$$
\begin{align*}
c_{11}&=a_{11}b_{11}+a_{12}b_{21}\\
c_{12}&=a_{11}b_{12}+a_{12}b_{22}\\
c_{21}&=a_{21}b_{11}+a_{22}b_{21}\\
c_{22}&=a_{21}b_{12}+a_{22}b_{22}\\
\end{align*}
$$

this is 8 multiplications and 4 additions

#### [STRASSEN ALGORITHM](/ref/strassen.md)
$$
\begin{align*}
c_{12}&=x_3+x_5\\
&=a_{11}(b_{12}-b_{22})+(a_{11}-a_{12})b_22\\
&=a_{11}b_{12}-a_{11}b_{22}+a_{11}b_22-a_{12}b_22\\
&=a_{11}b_{12}+a_{12}b_{22}
\end{align*}
$$

#### SPECIAL CASE: $$4\times4$$ matrices.
$$
\begin{align*}
A\times{B}&=\left[\begin{array}{cc|cc}
a_{11}&a_{12}&a_{13}&a_{14}\\
a_{21}&a_{22}&a_{23}&a_{24}\\\hline
a_{31}&a_{32}&a_{33}&a_{34}\\
a_{41}&a_{42}&a_{43}&a_{44}\\
\end{array}\right]
\left[\begin{array}{cc|cc}
b_{11}&b_{12}&b_{13}&b_{14}\\
b_{21}&b_{22}&b_{23}&b_{24}\\\hline
b_{31}&b_{32}&b_{33}&b_{34}\\
b_{41}&b_{42}&b_{43}&b_{44}\\
\end{array}\right]\\
&=\left[\begin{array}{cc|cc}
c_{11}&c_{12}&c_{13}&c_{14}\\
c_{21}&c_{22}&c_{23}&c_{24}\\\hline
c_{31}&c_{32}&c_{33}&c_{34}\\
c_{41}&c_{42}&c_{43}&c_{44}\\
\end{array}\right]
\end{align*}
$$

- split and make quadrant of $$2\times2$$ matrices.
$$
\begin{align*}
A\times{B}&=\left[\begin{array}{c|c}
A'_{11}&A'_{12}\\\hline
A'_{21}&A'_{22}
\end{array}\right]
\left[\begin{array}{c|c}
B'_{11}&B'_{12}\\\hline
B'_{21}&B'_{22}
\end{array}\right]=
\left[\begin{array}{c|c}
C'_{11}&C'_{12}\\\hline
C'_{21}&C'_{22}
\end{array}\right]
\end{align*}
$$

- 7 ($$2\times2$$) multiplication +
- 18 ($$2\times2$$) multiplication

- 49 total multiplication (64 normally)
- $$(7\cdot18)+(18\cdot4)=198$$ addition (48 normally)

How many  multiplications and additions to do using Strassen Method for $$2^k\times2^k$$ matrix?

- $$7^k$$ multiplications (vs. $$8^k$$ normally)

$$
\left\{
\begin{align*}
n&=2^k\\
k&=\log_{2}{n}
\end{align*}
\right\}
$$

$$
7^k=7^{(\log_{2}{n})}=n^{\log_{2}{7}\approx2.81}
$$

#### MASTER THEOREM
$$
n=2^k
$$

$$
\begin{align*}
T(n)&=7T{\left(\frac{n}{2}\right)}+18\left(\frac{n}{2}\right)^2\\
&=7T{\left(\frac{n}{2}\right)}+\frac{9}{2}n^2
\end{align*}
$$

$$
\left\{
\begin{align*}
\\
a=7,\:\:\:\:b=2\:\:\:\:\\
\log_2{7}=2.81\cdots\\\\\end{align*}\right\}
$$

$$
T(n)=\Theta(n^{\log_{2}7})=\Theta(n^{2.81})
$$


## BACK TO POLYNOMIAL..
- we want to choose values for the variable $$x$$ which can lead to lots of recycling when evaluating 
$$
p(x_1),\:p(x_2),\cdots,p(x_k)
$$


