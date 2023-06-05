# Associative Array (map/dictionary)
Otherwise known as a *dictionary*, or even a *hash map*, an associative array allows you to store data as key-value pairs. A key of choice can be the index of a value of choice.

Key-value pairs are stored as `std::pair` objects. A `std::pair` object has two member variables: `.first` (the key), and `.second` (the value).

## Unordered Map vs Ordered Map
The `unordered_map` stores elements in no particular order. This means that searching, inserting and deleting is typically faster.

A `map`, on the other hand, sorts integer keys in ascending order.

## Creating a map
In order to make use of the associative array data structure, the appropriate libraries must first be included:
```cpp
#include <unordered_map>
#include <map>
```
Upon declaration, the data type of the key and value must be provided:
```cpp
std::unordered_map<std::string, int> country_codes
```
It's also possible to initialise an associative array in a single statement, using an initialiser list:
```cpp
std::unordered_map<std::string, int> country_codes{
	{"The Netherlands", 31},
	{"Italy", 39}
};
```
## Map methods
### Adding elements
`.insert()` adds a new key-value pair. There cannot be duplicates in key values, otherwise the entry will not be added to the map.

Alternatively, square brackets `[]` can be used to add new key-value pairs.

The values must match the previously declared types.
```cpp
// .insert() method
country_codes.insert("Australia", 61);
// square brackets
country_codes["Germany"] = 49;
```
### Removing elements
The `.erase()` method removes an element in a map. The key-value pair is referenced by key (duh).
```cpp
country_codes.erase("Germany");
// country_codes is now missing {"Germany", 49}
```
### Checking for elements
`.count()` returns the number of occurences in a map for the specifed key. Since maps do not allow for duplicate keys, this will return `1` if the key is present.
```cpp
if (country_codes.count("Belgium")) {
  std::cout << "There is a code for Belgium";
}
else {
  std::cout << "There isn't a code for Belgium";
}
```
### Accessing elements
Like most other languages, you can use square brackets to index a value using its key. If the key does not exist – the specified value is inserted at that key.

To avoid this, the `.at()` method can be used. This will thow an `out_of_range` exception if nothing has been defined under the given key.

### Size of a map
The `.size()` method returns the number of elements in a map.

`.empty()` returns a boolean indicating whether the map is empty.

## Iterating through a map
A `for-each` loop is best suited for a map. The `.first` and `.second` member variables of the `std::pair` object is also well suited for this.
```cpp
std::unordered_map<std::string, int> country_codes{
	{"The Netherlands", 31},
	{"Italy", 39},
	{"Germany", 49}
};

for (auto country: country_codes){
	std::cout << country.first << country.second << "\n";
}

```