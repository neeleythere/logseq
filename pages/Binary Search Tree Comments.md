## Assumptions 
- The BST does not accept duplicate `key` values.
	- New additions must be smaller to result in left traversal, and larger to result in right traversal. Otherwise, new additions are discarded.
- However, existing nodes *accomodate* for the addition of a single string value (which would otherwise be a duplicate) by storing it as a `value`.
- In cases where a `std::string` value is not stored on a node, returning the `key` int value is a suitable response.
- The input file is stored in the `.txt` file format.
	- Each individual entry within the `.txt` file is seperated by whitespace.
- Formatting followed the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) where possible.
	- Function comments are left mainly on the declaration.

## Shortcomings & Potential Improvements
- Each node only has the capacity to store a single `std::string` value.
	- To improve this, a `std::vector` or `std::set` could be utilised to store multiple values.
	- The `insert_` and `remove_` member functions would have to be reworked to support this.
- Because of the above, `std::vector<std::string> find()` will only ever return a vector with a single element.
- Some best practices are missing.
	- Relatively new to C++ & constrained by time.
	- No deconstructor, template class, header guards, unclear with constexpr vs const.
- No formal error handling.
	- Investigate alternative methods to raise exceptions, instead of just printing messages to the console using `std::cout`.
- No validation on the supplied file name within the BST constructor.
	- The program crashes when an invalid (or no) text file is passed.
	- Additional validation should be applied within the constructor, which at a minimum should perform a presence check.
