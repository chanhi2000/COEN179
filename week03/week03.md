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

**ex1.1**
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