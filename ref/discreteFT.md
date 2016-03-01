# Discrete Fourier Transform

## $$P(z)$$
$$
\begin{align*}
p(z)&=a_7z_3+a_5z_2+a_3z+a_1\\
p(z)&=z\cdot{p}_O(z^2)+pE(z^2)\\
\\
p_O(z)&=a_7z+a_3;
p_E(z)&=a_5z+a_1;
\end{align*}
$$

## $$p_O(z)$$ RECURSIVE CALL

$$
\begin{align*}
p_O(z)&=a_7z+a_3\\\\
\text{RETURN}&\:\:a_7+a_3\\
&\:\:a_3-a_7
\end{align*}
$$

## $$p_E(z)$$ RECURSIVE CALL

$$
\begin{align*}
p_O(z)&=a_5z+a_1;\\\\
\text{RETURN}&\:\:a_5+a_1\\
&\:\:a_1-a_5
\end{align*}
$$



