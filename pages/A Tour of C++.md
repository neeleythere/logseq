- ### Initialization #cpp 
  Prefer curly-brace initialization, you can even continue using the `=` sign:
  ```cpp
  double d1 {2.3};
  double d2 = {2.3}; // both good
  ```
  Use `auto` when there is not a specific reason to mention the type. Wanting to be clear is a valid reason to include the type.
- ### Initializing Objects #cpp 
  An object is initialized by the `new` keyword and deleted by the `delete` keyword.
- ### Constants #cpp
  C++ offers two forms of *immutability*. Immutability is an important design choice as it is able to enhance stability and certainty.
	- `const` is primarily used to enforce behaviour. The value of a `const` can be computed at run time. This is typically used in conjunction with [[Pointers & Reference Variables]] to pass data into functions with a guarantee that it will not be modified.
	- `constexpr` is more literal, the value of which must be known at compile time. Consequently, data is stored in read-only memory.
- ### Pass by Reference #cpp
  It is more efficient to pass a *reference* of a variable instead of *copying* a value of a variable in its entirety. Especially for *string* data types, for example. A `const` is used to guarantee that the referenced value is not modified within the scope of the function. An example:
  ```cpp
  void printByReference(const int& ref) {
    std::cout << ref << "\n"; // all good hosé
    ref = 2 // bro no
  }
  
  int main() {
    
    printByReference(my_int);
  }
  ```
-