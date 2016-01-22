# **week03c**

## QUICKSORT
- pick a pivot entry
- place all smaller entries to the left
- place all larger entries to the right
- place the pivot
- quicksort to the left
- and 
- quick sort to the right
- [see here](http://math.scu.edu/~bwalden/alg/quick.html) to see the process


```c
void quicksort(char a[], int left, int right)
{
    int i,j;  char v;
    if (right > left) {
	    v = a[right]; i = left-1; j = right;
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


