# Partial Sort in C++

In C++ STL, you can perform partial sorting using the `std::partial_sort()` algorithm. This algorithm partially sorts the elements in a range such that the first `n` elements are in sorted order, while the remaining elements are in an unspecified order.

The syntax of `std::partial_sort()` is as follows:

```cpp
template<class RandomIt>
void partial_sort(RandomIt first, RandomIt middle, RandomIt last);

template<class RandomIt, class Compare>
void partial_sort(RandomIt first, RandomIt middle, RandomIt last, Compare comp);
```

- `first`: Iterator to the beginning of the range.
- `middle`: Iterator to the element one past the last element of the sorted sequence. After the operation, the elements `[first, middle)` are sorted.
- `last`: Iterator to the end of the range.
- `comp`: A binary predicate function object used for comparison (optional). If not provided, the default comparison function (`operator<`) is used.

Here's an example demonstrating how to use `std::partial_sort()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {5, 2, 7, 1, 9, 3};
    const int n = 3; // Number of elements to partially sort

    // Partially sort the first 'n' elements in the vector
    std::partial_sort(vec.begin(), vec.begin() + n, vec.end());

    // Print the partially sorted elements
    std::cout << "Partially sorted elements: ";
    for (int i = 0; i < n; ++i) {
        std::cout << vec[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

In this example, the first three elements of the vector are partially sorted using `std::partial_sort()`. After the operation, these three elements are sorted, while the remaining elements are not necessarily in any particular order.
