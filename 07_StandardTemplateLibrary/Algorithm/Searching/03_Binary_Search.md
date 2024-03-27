# binary_search() in STL

In C++ STL, the `std::binary_search()` algorithm is used to check if a value exists in a sorted sequence. It returns `true` if the value is found, and `false` otherwise.

Here's the syntax of `std::binary_search()`:

```cpp
template< class ForwardIt, class T >
bool binary_search( ForwardIt first, ForwardIt last, const T& value );
```

- `first`: Iterator to the beginning of the sorted range.
- `last`: Iterator to the end of the sorted range.
- `value`: Value to search for.

It's important to note that `std::binary_search()` requires the sequence to be sorted beforehand. If the sequence is not sorted, the behavior is undefined.

Here's an example demonstrating the usage of `std::binary_search()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    
    // Check if the value 3 exists in the sorted vector
    bool found = std::binary_search(vec.begin(), vec.end(), 3);
    
    // Print the result
    if (found) {
        std::cout << "Value found" << std::endl;
    } else {
        std::cout << "Value not found" << std::endl;
    }
    
    return 0;
}
```

In this example:

- We have a sorted vector `vec` containing integers.
- We use `std::binary_search()` to check if the value `3` exists in the vector.
- If the value is found, we print "Value found". Otherwise, we print "Value not found".

Output:
```
Value found
```

`std::binary_search()` uses the binary search algorithm, which has a time complexity of O(log N), where N is the number of elements in the range. It's an efficient way to search for elements in sorted containers.
