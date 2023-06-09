- ## If statement
  Defined like so:
  ```cpp
  if (condition)	{
  	// code to execute if true
  }
  ```
  
  
  
  
  
  ## Else statement
  Defined like so:
  ```cpp
  if (condition)	{
  	// code to execute if true
  }
  else {
  	// code to execute if false
  }
  ```
-
## Else if statement
```cpp
if (condition1) {
	// code
}
else if (condition2) {
	// code
}
```
## Ternary operator (alternate if else)
Useful if you want to do things in a single line:
```cpp
variable = (condition) ? exprIfTrue : exprIfFalse;
```
## Switch statements
More readable and optimised version of else-if statement. As the name suggests the `default` keyword is used if no case evaluates to `true`.

Used like so:
```cpp
switch (speed) {
	case 220:
std::cout << "ICE\n";
break;
	case 180:
std::cout << "IC\n";
break;
	case 140:
std::cout << "RE\n";
break;
	default:
std::cout << "Undetected train type.\n";
break;
}
```