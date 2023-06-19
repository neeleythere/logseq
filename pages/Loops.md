- ## Different types of loops #cpp
- `while`
- `do-while`
- `for`
- `for-each`
## While loop
```cpp
int count = 1;
while (count <= 5) {
	std::cout << count;
	count++;
}
```
## Do-while loop
```cpp
int price = 300;
do {
	std::cout << "Too expensive!";
} while (price > 500);
```
- ## For loop
  ```cpp
  for (int i = 1, i <= 5, i++) {
  	std::cout << i;
  }
  ```
## For-each
```cpp
int fibonacci[5] = {0, 1, 1, 2, 3};
for (int number : fibonacci) {
	std::cout << number;
}
```

Alternatively, the data type for `number` could also be set to `auto`. Which automatically detects the required datatype for the iterator.