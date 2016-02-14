# mt15wtr-d

##4.
The following algorithm attempts to sort an array using a stack:

Given an input list of numbers, push the first element $$k$$ of the remaining input onto the stack if the stack is empty or $$k$$ is smaller than the top element of the stack.  Otherwise, pop the top element of the stack onto the end of the output list.  Repeat until the input list and the stack are empty.

For example, if the input list is $$421365$$, the sequence of step is:
$$
\begin{matrix}
\text{push }4,&\:\text{push }2\:(\text{since }4<2),&\:\text{push }1\:(\text{since }2<1),&\:\text{pop }1\:(\text{since }1<3),\\
\:\text{pop }2\:(\text{since }2<3),&\text{push }3\:(\text{since }4>3),&\:\text{pop }3\:(\text{since }3<6),&\:\text{pop }4\:(\text{since }4<6),\\
\:\text{push }6\:(\text{empty stacks}),&\:\text{push }5\:(\text{since }6<5),&\:\text{pop }5\:(\text{since }6<5),&\:\text{pop }5\:(\text{end of list}),\\
\:\text{pop }6\:(\text{end of list})
\end{matrix}
$$

In this case, the output (as entries are popped in order) is $$123456$$—the sequence sorted in increasing order.

**(a)** Find an ordering of the numbers $$1$$ through $$6$$ that cannot be sorted in one pass this way.

**(b)** If you apply the algorithm to the output from part (a) i.e., running the algorithm a second time, do you get a properly sorted list?

**(c)** Show that in general, if you repeatedly run the algorithm on a list of $$n$$ entries, it wouuld take $$\Omega(\log{(n)})$$ attempts to hope to sort the list.


