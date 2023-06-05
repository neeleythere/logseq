# Constructors
 **A constuctor has the same name as the class and no return type (not even `void`.** Constructors are run when an object is instantiated.
 
 ## Default constructor
 A *default constructor* is a constructor that takes no parameters. If the object is created without specifying initialisation values, the *default constructor* will be used.
 
 ```cpp
class House {
private:
	std::string location;
	int rooms;
	
public:
	// default constructor
	House() {
		location = "New York";
		rooms = 5;
	}
};
```

## Constructor with parameters
Constructors can also be declared with parameters.

Adding a constructor with parameters for the `House` class goes as follows:
```cpp
class House {
private:
	std::string location;
	int rooms;
	
public:
	// constructor with parameters
	House(std::string loc, int num) {
		location = loc;
		rooms = num;
	}
};
```

Defaults can also be defined. In the above example, you could modify the `House()` constructor as follows
```cpp
... // class definition
	House(std::string loc = "Amsterdam", int num = 2) {
		// member assignment
	}
...	
```

## Member initializer lists
When dealing with `const` or reference variables, the logic outlined above would raise an error as you are technically reassigning the value of such a variable.

To help with this, a "member initializer list" can be used. The following example uses this logic.
```cpp
class Book {
private:
	const std::string title;
	const int pages;
	
public:
	Book()
		: title("Diary"), pages(100) {} // <- member initializer list
};
```

The member initializer list must be followed by curly braces (`{}`), as this is still a constructor function. You could even place code within the constructor's body if needed.