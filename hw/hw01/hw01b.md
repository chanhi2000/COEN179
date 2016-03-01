# hw01b

## custom.02
Consider this program :
```cpp
#include<iostream.h>
#include<math.h>
#include<iomanip.h>

double fcn(double x, double a) {
    return (x+a/x)/2;
}

int main() {
	double epsilon = 1e-3; // 3-digit precision
	double  a, b=1;

	cout.setf(  ios::fixed  );
	cout.setf(  ios::showpoint  );
	cout.precision(3);     // 3-digit precision

	cout << "Input number ";
	cin >> a;

	while(  fabs(fcn(b,a)-b) > epsilon  )
		b=fcn(b,a);

	cout << b << endl;

	return 0;
}
```
What does the outputted value signify? By timing or counting steps using several different inputs, conjecture the complexity of this algorithm. Can you prove your answer? Would your answer change if the value of 3 in the two commented lines changed to 6 or 9?

