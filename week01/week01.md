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
- $$u=\log_{b}{n};\:\:\:\:b^u =n$$;
- $$u\cdot\ln{(b)}=\ln{(b^u)}=\ln(n)$$
- $$u=\frac{ln(n)}{ln(b)}=\frac{\log_{10}{\left(n\right)}}{\log_{10}{\left(b\right)}}=\frac{\log_{2}{\left(n\right)}}{\log_{2}{\left(b\right)}};$$
- $$O(1)$$ is better than $$O(\log_{b}{(n)})$$

#### PROPOSITION
- in the following list, any function $$f(n)$$ to the left of any function $$g(n)$$ satisfies $$f(n)=O(g(n))$$ but $$g(n)\neq{O}(f(n)$$:
    - **bounded**: $$1$$
    - **logarithmic**:  $$log_b{(n)}$$
    - **polynomial**: $$n^a\:\:(a>0)$$
    - **exponential**: $$c^n\:\:(c>1)$$
    - **factorial**: $$n!$$

- If
$$
    \lim_{x\to\infty}{\frac{f(x)}{g(x)}}=L
$$
- and $$0<L<\infty$$, then
    - $$f(n)=O(g(n)),\:\:\:\:\text{i.e. }f(n)=\Theta{(g(n))};$$
    - $$g(n)=O(f(n)),\:\:\:\:\text{i.e. } f(n)=\Omega{(g(n))};$$


- and $$L=0$$, then
    - $$f(n)=O(g(n)),$$ but
    - $$g(n)\neq{O}(f(n))$$


- and $$L=\infty$$, then
    - $$f(n)\neq{O}(g(n)),$$ but
    - $$g(n)=O(f(n))$$

$$
\frac{1}{C}=\frac{f(n)}{g(n)}
$$

- ###### EXAMPLE#1:
$$
\begin{align*}
\lim_{x\to\infty}\frac{\log_b{x}}{x^{a}}&\underset{\text{L'H}}{=}\lim_{x\to\infty}\frac{\left(\frac{1}{x}\right)\left(\frac{1}{\ln{b}}\right)}{ax^{a-1}}\\&=\lim_{x\to\infty}\frac{1}{a(\ln{b})(x^a)}=0;
\end{align*}
$$


- ###### EXAMPLE#2:
$$
\begin{align*}
c^{x}&=e^{x\ln{c}};\\e^{ln{\left(c^{x}\right)}}&=e^{x\ln{c}}\\\\d\left(\right)
\end{align*}
$$

$$
\begin{align*}
\lim_{x\to\infty}\frac{x^{a}}{c^{x}}&\underset{\text{L'H}}{=}\lim_{x\to\infty}\frac{ax^{a-1}}{c^x\ln{c}}\\&\underset{\text{L'H}}{=}\lim_{x\to\infty}\frac{a(x-1)x^{a-2}}{\left(c^x\ln{c}\right)^2}\\&\vdots\\&\underset{\text{L'H}}{=}\lim_{x\to\infty}\frac{a(x-1)(x-2)\cdots x^{a-K}}{\left(c^x\ln{c}\right)^K}=0
\end{align*}
$$

- ###### EXAMPLE#3
$$
e^{c}=\sum_{n=0}^{\infty}\frac{c^n}{n!}=1+c+\frac{c^2}{2!}+\frac{c^3}{3!}+\cdots
$$

$$
\left<\lim_{x\to\infty}\frac{c^{n}}{n!}=0;\right>
$$

$$
n!\geq\left(\frac{n}{2}\right)^{\frac{n}{2}}=\left(\left(\frac{n}{2}\right)^K\right)^n>\left(2c\right)^n=2^n\cdot c^n
$$

## HOW BAD IS n!
- split the half way of $$n$$
- $$n!$$ is a lot bigger than any power (very BAD)
