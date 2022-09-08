# C++

## Lessons Learned

1. If the `.h` file is encapsolated in a namespace, it is best to encapsolate the `.cpp` file in the same namespace (and not just say `using namespace <name>`).
2. Declare `friend` functions in the `.h` file and their implementation in the `.cpp` file without the `friend` keyword. They are given access to private variables even though `friend` functions are not considered member variables.
3. Returning a read-only reference `const &` does not allow the value to be updated (e.g. `std::string const &getValue()`).
4. Having `const` on the return value makes it `read-only` (`string const getValue()`). Having `const` in front of the function makes the return value need to be a `const` (`string getValue() const`).
5. Is there a reason to have reference member variables?
6. Template classes/functions cannot be separated in the `.h` and `.cpp` files. Unless you can declare all the types (`int`, `string`, etc) that the class/function could accept (that declaration happens somewhere at the bottom of the `.cpp` file). This is because a `templated` class/function is not an actual class/function. It just tells the compiler how the generated the class/function.
7. Template function explicit instantiation in .cpp: `template vector<string> const Reader::readFile<string>();`
8. Template class explicit instantiation in .cpp: `template class Reader<int>;`
9. Interfaces are `Abstract Classes` with `Pure Virtual Functions`: `virtual void getValue() = 0`
