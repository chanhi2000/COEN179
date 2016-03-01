# hw01a

## custom.01
Consider the following nested loops:
```c
for(int i=1; i<=N; i++)
	for(int j=1; j <= i; j++)
		for(int k=1; k <= i*sqrt(j); k++)
			x=i+j+k;
```
Using a timer or counting steps, calculate runtimes using $$N=10,\:20,\:40,\:100,\:200,\:400,\:1000,\:2000,\:4000,\:10000$$.
Based on the results, conjecture the complexity of the number of assignments performed. Prove your conjecture.


