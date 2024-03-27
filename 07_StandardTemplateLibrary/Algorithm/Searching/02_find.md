In C++ STL, the `std::find()` algorithm is used to search for the first occurrence of a value in a sequence (e.g., an array, vector, or list). It returns an iterator to the first occurrence of the value if found, otherwise, it returns an iterator pointing to the end of the sequence.

Here's the syntax of `std::find()`:

```cpp
template< class InputIt, class T >
InputIt find( InputIt first, InputIt last, const T& value );
```

- `first`: Iterator to the beginning of the range.
- `last`: Iterator to the end of the range.
- `value`: Value to search for.

Here's an example demonstrating the usage of `std::find()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    
    // Search for the value 3 in the vector
    auto it = std::find(vec.begin(), vec.end(), 3);
    
    // Check if the value is found
    if (it != vec.end()) {
        std::cout << "Value found at index: " << std::distance(vec.begin(), it) << std::endl;
    } else {
        std::cout << "Value not found" << std::endl;
    }
    
    return 0;
}
```

In this example:

- We have a vector `vec` containing integers.
- We use `std::find()` to search for the value `3` in the vector.
- If the value is found, we print the index of the first occurrence of `3`. Otherwise, we print that the value is not found.

Output:
```
Value found at index: 2
```

Here, `std::distance(vec.begin(), it)` is used to calculate the index of the found value relative to the beginning of the vector.
