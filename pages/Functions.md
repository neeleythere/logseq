- ## Creating a function #cpp 
  title:: Functions
  When declaring a function, the return type, name, and parameters should be defined.
  
  Functions which return no value should have their return type set to `void`. For example:
  ```cpp
  void doSomething() {
  	std::cout << "Yippe we're working!\n";
  }
  ```
## Return type
The function **must** return a value which matchws the function's return type.
```cpp
double valueOfPi() {
return 3.1415;
}

int main() {
double pi = valueOfPi();
std::cout << pi;  // Output: 3.1415
}
```
## Parameters & Arguments
Parameters are defined in the declaration and are assigned a data type like regular variables. Arguments are placed within the brackets when calling a function.
```cpp
int feetToInches(int ft) {
	return ft * 12;
}

int main() {
	std::cout << feetToInches(6); // ouputs 72
}
```
## Default Parameters
By using default parameters, you no longer make it mandatory to provide an argument for each parameter.
```cpp
void message(std::string language = "C++") {
	std:cout << "I like to code with " << language << "\n";
}

int main() {
// Function call without an argument
message();    // Output: I like to code with C++

// Function call with an argument
message("Java");    // Output: I like to code with Java
}
```
## Pass by Reference
When *passing by reference*, you directly pass through variables as arguments. This allows functions to modify data outside the delcarative scope of the function.
```cpp
void swap(int &i, int &j) {
int temp = i;
i = j;
j = temp;
}

int main() {
int first = 10;
int second = 20;

std::cout << "Before swap: " << first << " " << second << "\n";

// Call the function and swap the values of first and second
swap(first, second);

std::cout << "After swap: " << first << " " << second << "\n";
}
```