# [algorithm]horner

> #### ALGORITHM `Horner`($$P[0\cdots{n}],\:x$$)
```
//Evaluates a polynomial at a given point by Horner’s rule
//Input: 	An array P[0..n] of coefficients of a polynomial of degree n,
//		    stored from the lowest to the highest and a number x
//Output:   The value of the polynomial at x
```
> $$p\leftarrow{P}[n]$$
> **for** $$i\leftarrow{n}-1$$ **downto** $$0$$ **do**
>>  $$p\leftarrow{x}*p+P[i]$$
> **return** $$p$$
