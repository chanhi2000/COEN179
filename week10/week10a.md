# week10a

## COMPLEX ARITHMETIC:
$$
\begin{align*}
z_1&=x_1+jy_1\\
z_2&=x_2+jy_2
\end{align*}
$$

- ####  CARTESIAN ARITHMETIC
$$
\begin{align*}
z_1+z_2&=(x_1+jy_1)+(x_2+jy_2)\\
&=x_1+x_2+j(y_1+y_2)\\
z_1z_2&=(x_1+jy_1)(x_2+jy_2)\\
&=x_1x_2+x_1(jy_2)+x_2(jy_1)+(jy_1)(jy_1)\\
&=x_1x_2-y_1y_2+j(x_1y_2+y_1x_2)
\end{align*}
$$

- #### POLAR ARITHMETIC
$$
\begin{align*}
z&=x+jy=r\cos{(\theta)}+jr\sin{(\theta)}\\
&=r(\cos{(\theta)}+i\sin{(\theta)})\\
\end{align*}
$$

$$
\begin{align*}
f(\theta)&=\cos{(\theta)}+j\sin{(\theta)}\\
f'(\theta)&=-sin{(\theta)}+j\cos{(\theta)}\\
&=(i)^2\sin{(\theta)}+j\cos{(\theta)}\\
&=i(\cos{(\theta)}+j\sin{(\theta)})=j(f(\theta))
\end{align*}
$$

- #### DEFINITION
$$
\begin{align*}
e^{j\theta}&=\cos{(\theta)}+j\sin{(\theta)}
e^{j\theta}&=1+j\theta+\frac{(j\theta)^2}{2!}+\frac{(j\theta)^3}{3!}+\cdots\\
&=1+j\theta-\frac{(\theta)^2}{2!}-\frac{(\theta)^3}{3!}+\cdots\\
&\left\{\begin{matrix}
\cos{(\theta)}=1-\frac{\theta^2}{2!}+\frac{\theta^{4}}{4!}+\cdots\\
\sin{(\theta)}=\theta-\frac{\theta^3}{3!}+\frac{\theta^5}{5!}+\cdots
\end{matrix}\right\}\\
&=\cos{(\theta)}+j\sin{(\theta)}
\end{align*}
$$

- #### USE OF IMANGINARY PARTS (ANGLE)
$$
i^2=(e^{j\frac{\pi}{2}})^2=e^{j\pi}=-1;
e^{j\pi}+1=0;
$$


$$
\begin{align*}
z^{n}&=1;\\
z^{3}&=1;\\
(z-1)(z^2+z+1)&=z^3-1=0;\\
z^2+z+1&=0;\\
z&=\frac{-1\pm\sqrt{(1)^2-4(1)(1)}}{2(1)}\\
&=-\frac{1}{2}\pm{j}\frac{\sqrt{3}}{2}\\
\end{align*}
$$

solution:
$$
\begin{align*}
1&=e^{j\cdot0}\\
-\frac{1}{2}+j\frac{\sqrt{3}}{2}&=e^{j\tfrac{2\pi}{3}}\\
-\frac{1}{2}-j\frac{\sqrt{3}}{2}&=e^{j-\tfrac{2\pi}{3}}
\end{align*}
$$


## FAST FOURIER TRANSFORM
Given
$$
\begin{align*}
p(z)&=a_nz^n+a_{n-1}z^{n-1}+\cdots+a_1z+a_0\\
p_E(z)&=a_0+a_2z^2+a_4z^4+\cdots\\
p_O(z)&=a_1z+a_3z^3+a_5z^5+\cdots\\
\end{align*}
$$

EXAMPLE
$$
\begin{align*}
p(z)&=a_7z^7+a_6z^6+\cdots+a_1z+a_0\\
&\left\{\begin{matrix}
p_E(z)=a_6z^6+a_4z^4+a_2z^2+a_0\\
p_O(z)=a_7z^7+a_5z^5+a_3z^3+a_1z\\\\
p_E(z^2)=a_6z^(3)+a_4z^(2)+a_2z^(1)+a_0\\
zp_O(z^2)=a_7z^(3)+a_5z^(2)+a_3z^(1)+a_1\\\end{matrix}\right\}\\
p(z)&=zp_O(z)+p_E(z)\\
\end{align*}
$$


