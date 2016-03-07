# [algorithm]LRBexp


> #### ALGORITHM `LeftRightBinaryExponentiation`($$a,\:b(n)$$)
```
//Computes an by the left-to-right binary exponentiation algorithm
//Input:	A number a and a list b(n) of binary digits b_I,...,b)0
//		in the binary expansion of a positive integer n
//Output:	The value of a^n
```
> $$\text{product}\leftarrow{a}$$
> **for** $$i\leftarrow{I}-1$$ **downto** $$0$$ **do**
>> $$\text{product}\leftarrow\text{product}*\text{product}$$
>> **if** $$b_i=1$$
>>> $$\text{product}\leftarrow\text{product}*a$$

> **return** $$\text{product}$$
