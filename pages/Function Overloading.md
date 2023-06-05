## Function Overloading
In C++, it is possible to have two functions with the same name. In such cases, functions are differentiated by the **type of the parameters & the number of inputs**.

In the following example, the `add()` function is overloaded two use different types:
```cpp
// Adds two int values
int add(int a, int b) {
	return a + b;
}

// Adds two double values
double add(double a, double b) {
	return a + b;
}
```

Additionally, you could have a **third** function, as long as the function **does not** accept 2 arguments. For example:
```cpp
// Adds three int values
int add(int a, int b, int c) {
  return a + b + c;
}
```

## Overload Resolution
The compiler will attempt to match the function call to a matching function based upon the number of arguments and the type of said arguments.