# mt14wtr-c

## 3.
Suppose you wish to store the exact value for $$n!$$. Typically, this will end in lots of zero bits. Rather than store the trailing zeros, you need only store the bits that precede
them, and store the number of trailing zeros. For example, with
$$
18!=10110101111101110110011001010011100110000000000000000
$$
you need only store the significant digits
$$
1011010111110111011001100101001110011
$$
and the number of zeros
$$
10000
$$
(16 in binary, that is). The total number of bits before chopping is $$\left\lfloor\lg{n!}\right\rfloor+1$$, and it turns out that the number of trailing zeros is given exactly by $$n-\text{bitsum}(n)$$, where $$\text{bitsum}(n)$$ denotes the number of 1’s in the binary expression of $$n$$. (For example, $$18=10010$$, so $$\text{bitsum}(18)=2$$.) Let $$f(n)$$ represent the number of bits necessary to store the significant digits of $$n!$$ and let $$g(n)$$ represent the number of bits necessary to store the number of trailing zeros of $$n!$$. (For example, $$f(18)=37$$, and $$g(18)=$$.) Show that
$$
\frac{f(n)}{g(n)}=\Theta{(n)}
$$

