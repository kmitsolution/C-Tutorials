# count() in C++ STL

In C++ STL, the `std::count()` algorithm is used to count the occurrences of a specific value in a range. It returns the number of times the value appears in the range.

Here's the syntax of `std::count()`:

```cpp
template< class InputIt, class T >
typename std::iterator_traits<InputIt>::difference_type
    count( InputIt first, InputIt last, const T& value );
```

- `first`: Iterator to the beginning of the range.
- `last`: Iterator to the end of the range.
- `value`: Value to count occurrences of.

It's important to note that `std::count()` requires that the elements in the range support equality comparison with the value being counted.

Here's an example demonstrating the usage of `std::count()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {1, 2, 3, 1, 4, 1, 5};
    
    // Count the occurrences of the value 1 in the vector
    int count = std::count(vec.begin(), vec.end(), 1);
    
    // Print the count
    std::cout << "Count of 1: " << count << std::endl;
    
    return 0;
}
```

In this example:

- We have a vector `vec` containing integers.
- We use `std::count()` to count the occurrences of the value `1` in the vector.
- The result is printed as the count of occurrences of the value `1`.

Output:
```
Count of 1: 3
```

`std::count()` provides a simple and efficient way to count the occurrences of a value in a range. It has a time complexity of O(N), where N is the number of elements in the range.
