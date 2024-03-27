# search() in STL

In C++ STL, the `std::search()` algorithm is used to search for the first occurrence of one sequence within another sequence. It returns an iterator to the beginning of the first occurrence if found, otherwise, it returns the end iterator of the first sequence.

Here's the syntax of `std::search()`:

```cpp
template< class ForwardIt1, class ForwardIt2 >
ForwardIt1 search( ForwardIt1 first1, ForwardIt1 last1,
                   ForwardIt2 first2, ForwardIt2 last2 );
```

- `first1`, `last1`: Iterators defining the range of elements in the first sequence.
- `first2`, `last2`: Iterators defining the range of elements to search for in the second sequence.

It's important to note that `std::search()` requires both sequences to be valid and of appropriate lengths. It performs a linear search, comparing elements sequentially.

Here's an example demonstrating the usage of `std::search()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> haystack = {1, 2, 3, 4, 5, 6};
    std::vector<int> needle = {3, 4, 5};
    
    // Search for the first occurrence of the needle sequence in the haystack sequence
    auto it = std::search(haystack.begin(), haystack.end(), needle.begin(), needle.end());
    
    // Check if the needle sequence is found
    if (it != haystack.end()) {
        std::cout << "Needle found at index: " << std::distance(haystack.begin(), it) << std::endl;
    } else {
        std::cout << "Needle not found" << std::endl;
    }
    
    return 0;
}
```

In this example:

- We have two vectors, `haystack` and `needle`, containing integers.
- We use `std::search()` to search for the first occurrence of the `needle` sequence in the `haystack` sequence.
- If the `needle` sequence is found, we print the index of its first occurrence in the `haystack` sequence. Otherwise, we print that the needle is not found.

Output:
```
Needle found at index: 2
```

`std::search()` provides a flexible way to search for one sequence within another sequence and is commonly used in text processing and data analysis applications.
