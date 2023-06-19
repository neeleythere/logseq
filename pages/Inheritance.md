- ## Inheritance #cpp 
  
  Inheritance is the concept of defining a class in terms of another class. Inheritance allows you to reuse code and and establish hierarchical relationships between classes.
  
  There two forms of inheritance:
- Basic inheritance
- Multilevel inheritance
  
  Multilevel inheritance occurs when a child class inherits members that are already derived from another class. This is otherwise known as an *inheritance chain*. The "basest" constructor is called first, all the way to the most dervived class.
## Basic inheritance

When dealing with inheritance, there are typically two forms to the relationship:
- "Base class" or "parent class": The class being inherited from.
- Derived class or child class: The class that inherits from the base class.
  
  To declare a derived class, place `:` after the class name and then write the access specifier and the name of the base class:
  
  ```cpp
  // Base class
  class Animal {
  public:
    std::string gender;
    int age;
  };
  
  // Derived class
  class Cat: public Animal {
  public:
    std::string breed;
    
    void sound() {
        std::cout << "Meow!\n";
    }
  }
  
  int main() {
    Cat daisy;
    daisy.gender = "girly";
    daisy.age = 3;
    daisy.breed = "tabby and white";
    
    daisy.sound(); // outputs: meow!
    
    return 0;
  }
  
  ```
## Constructor Inheritance

Normally, class attributes would be kept `private` for the sake of encapsulation.

A derived (child) class also inherits the constructors of its base (parent) class. A derived class can set the values of `private` attributes of its parent by using the base class' constructor and a member initializer list.

```cpp
#include <iostream>

// Base class
class Animal {
private:
  std::string gender;
  int age;
  
public:
  Animal(std::string new_gender, int new_age)
      : gender(new_gender), age(new_age) {}
};

// Derived class
class Cat: public Animal {
private:
  std::string breed;
  
public:
  // Call the base class constructor
  Cat(std::string new_gender, int new_age, std::string new_breed)
      : Animal(new_gender, new_age), breed(new_breed) {}
};

int main() {
  // Calls Cat(string, int, string) constructor
  Cat daisy("girly", 3, "tabby and white");
  
  return 0;
}

```
## Types of Inheritance

The access specifier used when inheriting a base class has significance on the availability of its members.
- `public` inheritance: the access specifiers on the base class members stay the same. This is most common.
- `protected` inheritance: `public` and `protected` members of the base class become protected members of the derived class.
- `private` inheritance: All base class members become `private` members of the derived class.
## Cute lil' table

| Access                   | public   | protected | private |
| ------------------------ | -------- | --------- | ------- |
| Inside the class         | yes      | yes       | no      |
| Inside the derived class | yes      | yes       | no      |
| Outside the class        | yes      | no        | no      |