# mt15(winter)

##1.
Prove or disprove:

**(a)** $$\log_2{(n)}=O(\log_2\log_2{(n)})$$

**(b)** The number of decimal digits in $$n^n=O(\text{the number of decimal digits in }n!)$$


##2.
An array initially contains the entries $$\text{S}\:\:\text{W}\:\:\text{I}\:\:\text{T}\:\:\text{C}\:\:\text{H}\:\:\text{A}\:\:\text{R}\:\:\text{O}\:\:\text{U}\:\:\text{N}\:\:\text{D}$$

**(a)** How many compariosns are done before the $$\text{D}$$ is moved in selecttion sort?

**(b)** How many swaps are done before the $$\text{A}$$ is moved in insertion sort?

**(c)** What is the state of the array in mergesort, just after the $$\text{O}$$ is first moved?

**(d)** What is the state of the array in heapsort (buttom-up version), just after the heap is built?

**(e)** What is the state of the array in quicksort after the $$\text{I}$$ is properly placed?


##3.
Use the master theorem to determine the order of $$T(n)$$ for the following recurrences.

**(a)** $$T(n)=12T\left(\frac{n}{3}\right)+10n^2\log{(n)}$$

**(b)** $$T(n)=9T\left(\frac{n}{3}\right)+n^2+10\log{(n)}$$

**(c)** $$T(n)=6T\left(\frac{n}{3}\right)+\frac{1}{10}n^2$$


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

**(b)** If you apply the algorithm to the output from part (a) *i.e.*, running the algorithm a second time, do you get a properly sorted list?

**(c)** Show that in general, if you repeatedly run the algorithm on a list of $$n$$ entries, it wouuld take $$\Omega(\log{(n)})$$ attempts to hope to sort the list.


##5.
Suppose an array $$A$$ of $$2n$$ entries contain $$2$$ different entries for $$n$$ distinct values. (For example, if $$n=8$$, the contents might be $$\text{CDACABBD}$$).  If we define a transposition to be an instance of $$A[i]>A[j]$$ when $$i<j$$ (so duplicate pairs cannot form a transposition), then find the expected number of transpositions in the $$2n$$-entry array with $$n$$ duplicates (Assume any entry appears at any location in the array with equal probability).

