- ## Summary #cpp
- A *memory address* is where the value is stored by the computer.
- A *pointer* stores a memory address of another value.
	- To fetch the memory address of a value (which is subsequently stored as the pointer value), the `&` symbol is used.
	- If you print the value of a pointer, the memory address is displayed.
- *Dereferencing* is typically performed on a pointer, using the `*` asterisk symbol.
	- This "unpacks" the memory address to "reveal" what is stored at the memory address.
	- *Deferencing* allows you to manipulate the value which is stored at the *memory address* of the pointer.
- A *reference variable* does not need to be *"dereferenced"* in order to "unpack" the referenced value.
	- It is commonly used in the context of function parameters: where the provided argument should not be copied, but instead modified directly.
- ## Memory Address #cpp
  You can reference the *memory address* of a variable using the `&` symbol as well.
  ```cpp
  std::string message = "Hello World!";
  
  // Print the memory address of message (0x7ffee9b21af0)
  std::cout << &message << std::endl
  ```
- ## Pointers #cpp
  A pointer is used to store a *memory address* as its value. It is declared using a `*` between the data type and the variable name. By accessing the *memory address* using `&`, you can set the value of a pointer like so:
  ```cpp
  std::string day = "Monday";
  
  // Use memory address of day
  std::string* ptr = &day;
  ```
- ## Dereference #cpp
  The `*` symbol is known as the *dereference operator*. Other than for pointers, the `*` symbol is used to fetch the actual value pointed to by a pointer variable.
  
  This is achieved by preceding the name of a pointer variable with `*` like so:
  ```cpp
  std::string day = "Monday";
  
  // Declare a pointer variable
  std::string* ptr = &day;
  
  // Reference: print the memory address of day (0x7ffd1d8306c4)
  std::cout << ptr << std::endl;
  
  // Dereference: print the value of day (Monday)
  std::cout << *ptr << std::endl;
  
  *ptr = "Friday";
  
  // Print: Friday
  std::cout << day << std::endl;
  
  ```
- ### Null Pointer #cpp
  It is dangerous to leave a pointer variable uninitialised (idk why lol). If you are unsure where to point, assign that variable to `nullptr`, which is a keyword that provides a typesafe pointer value representing an empty pointer.
  ```cpp
  int* ptr = nullptr;
  
  ```
  **Note:** In older C/C++ code, `NULL` was used for this purpose. `nullptr` is meant as a modern replacement to `NULL`.
- ## Reference Variable #cpp
  A reference is an alias (link) to an existing variable. It is declared using a `&` symbol between the data type and the variable name. Like so:
  ```cpp
  int exam_grade = 85;
  int& score = exam_grade;
  ```
  
  References always need to be assigned a variable to "track". Therefore, if you change the value of `exam_grade`, the value of `score` will change as well. You cannot declare them empty.
  
  References cannot be reassigned (well you can, but it will fuck things up).
  
  **References are used for the purpose of parameters in a function.**