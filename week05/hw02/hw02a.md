# hw02a

## custom.01. 
In class, we found that the solution to the mergesort recurrence
$$
T(n)=T\left(\left\lfloor\frac{n}{2}\right\rfloor\right)+T\left(\left\lfloor\frac{n}{2}\right\rfloor\right)+n;\:\:\:\:T(1)=0;
$$
satisfied $$f(n)=\Theta{(n\:\log{(n)})}$$. Find an expression for the exact value of $$T(n)$$. (Hint: generate the first 20 to 40 values and find a pattern.  You may prove your conjecture by induction on the number of bits required to express $$n$$.)