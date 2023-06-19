- # Arrays #cpp 
  Arrays can be used to store multiple values under a single identifier.
  
  In C++, items within an array must be of the same type. Additionally, the size of the array must be specified.
## Declaring an Array
To declare an array, state the data type and specify the size of the array like so:
```cpp
char grade[5];
```

It is better practice to initialise the values of an array upon declaration as follows. It is also possible to omit the length if you initialise the follows upon declaration. This is preferred:
```cpp
// length explicitly stated
char grade[5]{ "A", "B", "B", "B", "C" };
// length will automatically be calculated
char grade[]{ "A", "B", "B", "B", "C" };
```
## Accessing Values
As with other languages, you access elements by using square brackets `[i]`.
```cpp
std::cout << grade[4] // output: "C"
```
## Multidimensional Arrays
Multiple dimensions can be declared like so:
```cpp
int table[2][3]
{
	{ 1, 2, 1 },
	{ 4, 2, 4 }
};
```
In such a scenario, the length of the 2nd dimension **must** be provided.
## Iterating Through Arrays
Iterating through arrays is typically performed with either a `for` loop or a `for-each` loop.

A `for` loop is implemented as follows:
```cpp
int fibonacci[5]{ 0, 1, 1, 2, 3 };
for (int i; i < 5; i++) {
	std::cout << fibonacci[i];
}
```
Perhaps more convenient, a `for-each` loop. Note that a `for-each` loop traverses an array by the value of each element, not by a numeric iterator. It is implemented like so:
```cpp
int fibonacci[5]{ 0, 1, 1, 2, 3 };
for (int element: fibonacci) {
	std::cout << ;
}
```