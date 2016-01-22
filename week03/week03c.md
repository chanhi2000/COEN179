# **week03c**

## QUICKSORT
1. pick a pivot entry
2. place all smaller entries to the left
3. place all larger entries to the right
4. place the pivot
5. quicksort to the left and 
6. quick sort to the right

```c
void quicksort(char a[], int left, int right)
{
    int i,j;  char v;
    if (right > left) {
	    v = a[right]; 
	    i = left-1; 
	    j = right;
	    for (;;) {
	        while (a[++i] < v);
	        while (a[--j] > v);
	        if (i >= j) break;
	        swap(a, i, j);
	    }
	    swap(a, i, right);
	    quicksort(a, left, i-1);
	    quicksort(a, i+1, right);
    }
}
```
>[see here](http://math.scu.edu/~bwalden/alg/quick.html) to see the example process.

- right: sentinel pivot
- left: cursor
- 
