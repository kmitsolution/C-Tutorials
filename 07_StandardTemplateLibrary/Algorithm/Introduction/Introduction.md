In C++, the Standard Template Library (STL) provides a rich set of algorithms for sorting, searching, and manipulating data. These algorithms are implemented as template functions in the `<algorithm>` header. Here's a brief overview of some commonly used algorithms:

1. **Sorting Algorithms**:
   - `sort()`: Sorts elements in ascending order by default. You can provide a custom comparator function to sort elements in a different order.
   - `partial_sort()`: Sorts the first n elements in a range.
   - `stable_sort()`: Sorts elements while preserving the relative order of equal elements.
   - `nth_element()`: Partially sorts the range so that the element at the nth position is the one that would be in that position if the range was fully sorted.

2. **Searching Algorithms**:
   - `find()`: Searches for an element in a range and returns an iterator to the first occurrence of the element.
   - `binary_search()`: Checks if an element exists in a sorted range using binary search.
   - `lower_bound()`: Returns an iterator to the first element not less than the given value in a sorted range.
   - `upper_bound()`: Returns an iterator to the first element greater than the given value in a sorted range.
   - `equal_range()`: Returns a range containing all elements equivalent to the given value in a sorted range.

3. **Manipulating Algorithms**:
   - `copy()`: Copies elements from one range to another.
   - `move()`: Moves elements from one range to another.
   - `swap()`: Swaps the values of two elements.
   - `transform()`: Applies a function to each element in a range and stores the result in another range.
   - `rotate()`: Rotates the elements in a range.

Here's a simple example demonstrating the usage of some of these algorithms:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {5, 2, 7, 1, 9, 3};

    // Sorting the vector
    std::sort(vec.begin(), vec.end());

    // Searching for an element
    auto it = std::find(vec.begin(), vec.end(), 7);
    if (it != vec.end()) {
        std::cout << "Found 7 at position: " << std::distance(vec.begin(), it) << std::endl;
    } else {
        std::cout << "7 not found in the vector." << std::endl;
    }

    // Copying elements to another vector
    std::vector<int> vec_copy(vec.size());
    std::copy(vec.begin(), vec.end(), vec_copy.begin());

    // Output the copied vector
    std::cout << "Copied vector: ";
    for (int num : vec_copy) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

This code sorts a vector, searches for an element, and copies the elements to another vector using STL algorithms.
