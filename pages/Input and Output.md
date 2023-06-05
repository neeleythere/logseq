## General
The `iostream` library is used to input and output information.

It is imported (like other libraries) with the following:
```cpp
#include <iostream>
```

## Output
`std::cout` is used to print information. It stands for "character output".

This is used together with `<<`  (*insertion operator*) to print values to the terminal:
```cpp
std::cout << "Hello World!";
```

You could use multiple *insertion operators* together like so:
```cpp
// prints: "Neeley is 23 years old."
std::cout << "Neeley is " << 23 << " years old.";
```

## Input
`std::cin` is used to collect input. It stands for "character input".

This is used together with `>>` (*extraction operator*) to store the eventual input.
```cpp
int x;
std::cin >> x;
```

Combine this with output to the terminal and you end up with proper interactive user communication:
```cpp
int age;  // the variable to hold the input value
std::cout << "Enter your age: ";  // asks the user for age
std::cin >> age;  // get user input and store it in variable name
std::cout << "You are " << age << " years old.";  // print the user's age
```