# week09b

## COMPUTATION ALGORITHM
- multiply polynomials
- multiply matrices,
- etc.


## POLYNOMIALS:
$$
\begin{cases}
&p(x)=a_nx^n+a_{n-1}x^{n-1}+a_{n-2}x^{n-2}+\cdots+a_2x^2+a_1x^1+a_0\\
&a_n\neq0
n:&\text{degree of }p(x);
\end{cases}
$$
- **INPUT**:
    $$x, \underset{\text{array of coefficients}}{a[i]},\:\:\:\:(0\leq{i}\leq{n})$$
- **OUTPUT**:
     $$p(x)$$

How many operations are used to evaluate the polynomial?
$$
\begin{align*}
\#\text{ of multiplications}&=n+(n-1)+(n-2)+\cdots+2+1+0\\
&=\frac{n(n_1)}{2}=\Theta{(n^2)};\\
\#\text{ of additions}&=n;
\end{align*}
$$

In general
$$
\begin{matrix}
x&\\
(x\cdot{x})&=x^2;\\
(x\cdot{x})\cdot{x}&=x^3;\\
(x\cdot{x}\cdot{x})\cdot{x}&=x^4;\\
\vdots&\vdots\\
(x\cdot,\cdots\cdot{x})\cdot{x}&=x^n\\
\end{matrix}
$$

i.e.
- $$n-1$$ multplications (for power of $$x$$)
- $$n$$ multiplications (for coefficients + powers)
- $$n$$ additions

we want to have
- $$2n-1$$ multiplications, so it's

$$
\Theta(n)
$$
- $$n$$ additions

## HORNER'S METHOD
- break down our output $$p(t)$$
$$
\begin{align*}
a_nx^n\\
a_nx^n+a_{n-1}x^{n-1}&=(a_nx+a_{n-1})x^{n-1}\\
a_nx^n+a_{n-1}x^{n-1}+a_{n-2}x^{n-2}&=\left((a_nx+a_{n-1})x\right)x^{n-2}\\
\vdots
\end{align*}
$$

## TECHNIQUE: STRAIGHT LINE PROGRAM
$$
s_i=x\:\text{op}\:y\:\:\:\:\left<\text{op}:\:\text{some opeartion from }+,-,\times,\div\right>
$$

- $$x, y$$ are hard coded constants user input or previous computations

$$
(s_1,\:s_2,\:\cdots,\:s_n)
$$
- there's no conditioning, just a series of steps
$$
\begin{align*}
s_1&=x\times{x}&\\
s_2&=s_1\times{x}\\
s_3&=s_2\times{x}\\
&\vdots\\
s_{n-1}&=s_{n-2}\times{x}\\
s_{n}&=a_1\times{x}\\
s_{n+1}&=a_2\times{s_1}\\
s_{n+2}&=a_3\times{s_2}\\
&\vdots\\
s_{2n-1}&=a_n\times{s_{n-1}}\\
s_{2n}&=a_0+s_n\\
s_{2n+1}&=s_{2n}+s_{n+1}\\
s_{2n+2}&=s_{2n+1}+s_{n+2}\\
&\vdots\\
s_{3n-1}&=S_{3n-2}+s_{2n-1}\\
\end{align*}
$$

To summarize
$$
\begin{align*}
s_1&=a_n\times{x}&\\
s_2&=s_1+a_{n-1}\\
s_3&=a_{2}\times{x}\\
s_4&=s_{3}+a_{n-2}\\
&\vdots\\
s_{n-1}&=s_{n-2}\times{x}\\
s_{n}&=s_{n-1}+a_{n-1}\times{x}\\
&\vdots\\
s_{2n-1}&=s_{2n-2}\times{x}\\
s_{2n}&=+s_{2n-1}+a_0\\
\end{align*}
$$

####**THEOREM**:
any straight line program which computes $$p(x)$$ of degree $$n$$ must have at least $$n$$ multiplications and $$n$$ addition.

#### EXAMPLE:
suppose you have the polynomials as such.
$$
\begin{align*}
p(x)=x^{15}+x^{14}+x^{13}+\cdots+x+1
\end{align*}
$$

**IDEA**:
$$
\begin{align*}
s&=x^{15}+x^{14}+x^{13}+\cdots+x+1\\
xs&=x^{16}+x^{15}+x^{14}+\cdots+x^2+x\\
xs-s&=x^{16}-1\\
s=\frac{x^{16}-1}{x-1}
\end{align*}
$$

**WHAT"S HAPPENING**:
$$
\begin{align*}
s_1&=x\cdot{x}\\
s_2&=s_1\cdot{s_1}\\
s_3&=s_2\cdot{s_2}\\
s_4&=s_3\cdot{s_3}\\
s_5&=s_4-1\\
s_6&=x-1\\
s_7&=s_5\div{s_6}\\
\end{align*}
$$

#### LEMMA
Any straight line program which computes $$x_n+x_{n+1}+\cdots+x_0$$ requires at least $$n$$ addition / substraction.

###### proof:
By induction
$$
\begin{matrix}
\text{base case}:&n=0&x_0&\text{at least 0 additions}
\end{matrix}
$$
**Hypothesis step**:
- Assume the statement is true for $$n-1$$ want to show that it's true for $$n$$.
- Given an arbitrary Straight Line Program that computes, $$x_n+x_{n+1}+\cdots+x_0$$
- Given $$x_n,\:x_{n+1},\:\cdots,\:x_0$$ as input
- **OUTPUT**: $$x_n+x_{n+1}+\cdots+x_0$$
    - (not modified) has at least n addition / substraction before replacement
    - (modified) By hypothesis, modified program has at least $$n-1$$ addition / substraction

$$\therefore\:\text{true}\forall{n}\:\text{ by induction}$$










