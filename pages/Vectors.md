- # Vectors #cpp
  Vectors are similar to arrays, however they are able to grow and shrink in size.
  
  In order to use the `vector` data type, you must include the vector library like so:
  ```cpp
  #include <vector>
  ```
## Declaring a `vector`
A vector containing `char` elements is declared like so:
```cpp
std::vector<char> alphabet;
```
You cannot change the data type of the elements once a vector is declared. Better practice, as always, is to initialise upon declaration.

It is also possible to forego the data type from C++17 onwards:
```cpp
std::vector<char> alphabet { "a", "b", "c" };
// this will also be accepted by the compiler
std::vector alphabet { "a", "b", "c" };
```
- ## Methods #card
	- `.push_back()`
	- `.pop_back()`
	- `.front()`
	- `.back()`
	- `.size()`
	- `.empty()`
## Adding an element
The `.push_back()` method reallocates the memory needed and adds the given value to the end of the vector.
```cpp
std::vector alphabet { "a", "b", "c" };
alphabet.push_back("d");
// alphabet now equals { "a", "b", "c", "d" }
```
## Removing an element
The `.pop_back()` method will remove the last element in a vector.
```cpp
std::vector alphabet { "a", "b", "c", "d" };
alphabet.pop_back();
// alphabet now equals { "a", "b", "c" }
```
## Accessing elements
Just like arays, you access elements using square brackets.
```cpp
std::cout << alphabet[1]; // outputs: "b"
```
Alternatively, you can fetch the first and last element of a vector using `.front()` and `.back()`.
```cpp
std::cout << alphabet.front(); // outputs: "a"
std::cout << alphabet.back(); // outputs: "c"
```
## Loops
```cpp
std::vector<char> vowels { "a", "e", "i", "o", "u"};

// for loop
// output: aeiou
for (int i {0}; i < vowels.size(); i++) {
	std::cout << vowels[i];
}

// for-each loop
// output: aeiou
for (char letter: vowels) {
	std::cout << letter;
}

```