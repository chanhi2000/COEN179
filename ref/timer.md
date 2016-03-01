# Timer

## C++, `timer.h`
```cpp
#include <ctime>

class Timer {
	public:
		Timer();
		void start_timer();
		float read_timer();
	private:
    	clock_t start_time;
};

Timer::Timer() {
	start_time = 0;
}

void Timer::start_timer() {
	start_time = clock();
}

float Timer::read_timer() {
	return (float(clock()-start_time)/CLOCKS_PER_SEC);
}

```

## Java `timer.java`
```java
class Timer	{
	private long start_time;

	public Timer() {
		start_time= 0;
	}
	public void start_timer() {
		start_time = System.currentTimeMillis();
	}
	public float read_timer() {
		return ((float)(((float)
		(System.currentTimeMillis()-start_time))*0.001));
	}
}
```
