## Defining Classes
Classes are defined by the `class` keyword. Like so:
```cpp
class School {
	
};
```
Note the trailing semicolon.

## Attribute and Method Definition
Attributes (member variables) and methods (member functions) are defined as follows. `public` denotes that the attributes and methods are available from outside of the eventual object.
```cpp
class School {
	public:
		std::string name;
		int age;
	
		void banner() {
			std::cout << name << " is " << age << "years old.\n";
		}
};
```

## Defining a Method Outside of a Class
It is common to see method definition outside of the class. In such a case, the `banner` method from above would be defined like so:
```cpp
void School::banner() {
	std::cout << name << " is " << age << "years old.\n";
}
```

Keep in mind that the original declaration still has to occur **within the class** definition.

## Objects
Objects are created similar to variable declaration (they use the same underlying logic).

Specify the class name (in our case `School`), and give the new object a reference (name). You can modify attributes and call methods using the dot operator `.`. 

```cpp
School university;

// modify attributes of the university object 
university.name = "University of Amsterdam";
university.age = 520;

// call the banner() method
university.banner();
```

## The `private` Keyword
By default, members of a class are declared as `private`. This means they are not directly accessible from outside of the class.

## The `public` Keyword
Members that are defined following a `public:` statement, are accessible from anywhere in the program.

This is most commonly used for the purpose of methods.

## Encapsulation
*Encapsulation* is the concept that information pertaining to an object isn't openly accessible to the entire program.

By using mutator & accessor functions (setters and getters) you can safely modify members of a class.

## Mutator & Accessor Functions (setters & getters)
An *accessor function* enables the visibility of a member without directly exposing it. A *mutator function* allows the modification of members, but by shielding operations in a dedicated function, control is still held on how a value is modified.  

```cpp
class Clock {
private:
	int time = 1200;
	
public:
	int getTime() {
		return time;
	}

	void setTime(int new_time) {
		time = new_time;
	}
}

int main() {
	Clock alarm;
	
	// print the time
	std::cout << alarm.getTime();
	
	// set the time to 930
	alarm.setTime(930);
	
}