- ## Compiling #cpp 
  When compiling, the `-o` argument allows for the definition of the eventual output.
  
  ```zsh
  g++ greeting.cpp -o greeting
  ```
  
  You'd then execute the program with:
  ```zsh
  ./greeting
  ```
- ## CLI Arguments
  To pass arguments through to the program, they should be seperated by spaces like so:
  ```zsh
  ./greeting arg1 arg2
  ```
- ### Using CLI Arguments
  In order to make use of any CLI arguments passed through, the `int main()` function needs to be adapted like so:
  ```cpp
  int main(int argc, char *argv[])
  ````
  `argc` (argument count) the number of CLI arguments passed. `argc` is at least 1 because the name of the program is seen as an argument.`
  
  `argv` (argument vector) is an array containing the values of the CLI arguments passed.
  
  The following example prints the values of all CLI arguments passed:
  ```cpp
  #include <iostream>
  
  int main(int argc, char* argv[]) {
  for (int i = 0; i < argc; i++) {
    std::cout << "arg " << i << ": " << argv[i] << "\n";
  }
  return 0;
  }
  ```