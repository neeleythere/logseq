- ## Destructors #cpp
  Destructors are called when an object is destroyed. **A destructor is defined by the class name preceded with a `~` symbol. It takes no parameters.**
  
  ```cpp
  class House() {
  private:
  	std::string location;
  	int rooms;
  
  public:
  	~House() {
  		std::cout << "Moved away from" << location;
  	}
  };
  ```
-