- ## Polymorphism #cpp 
  The term *polymorphism* means "many forms". Polymorphism refers to class methods in an inheritance relationship.
  
  Polymorphism allows derived classes to overrule inherited methods from base classes. C++ will respect methods defined on the derived class.
  
  ```cpp
  #include <iostream>
  
  class Animal {
  public:
  	void action() {
  		std::cout << "does something...\n";
  	}
  };
  
  class Fish: public Animal {
  public:
  	void action() {
  		std::cout << "Swim!\n";
  	}
  };
  
  class Cow: public Animal {
  public:
  	void action() {
  		std::cout << "Moo!\n";
  	}
  };
  
  int main() {
  	Animal newAnimal;
  	Fish newFish;
  	Cow newCow;
  	
  	newAnimal.action(); // output: does something...
  	newFish.action(); // output: Swim!
  	newCow.action(); // output: Moo!
  	
  	return 0;
  }
  ```
  
  In the above example, `action()` has *polymorphed* into three different forms.