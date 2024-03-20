# Sorting Algorithms in C++ STL

In C++ STL, sorting algorithms are provided by the `<algorithm>` header. Here's an overview of commonly used sorting algorithms along with examples of how to use them:

**`std::sort()`**:
   - Sorts the elements in the range `[first, last)` in ascending order by default, using the less-than operator (`<`).
   - Can be overloaded to use custom comparison functions or function objects for sorting in different orders.
   - Complexity: O(N log N) comparisons on average.
   - The std::sort() algorithm in C++ STL typically uses an introsort, which is a hybrid sorting algorithm combining quicksort, heapsort, and insertion sort.
   
 ### Ascending Order with sort()
   ```cpp
   //Ascending order
   #include <iostream>
   #include <vector>
   #include <algorithm>

   int main() {
       std::vector<int> vec = {5, 2, 7, 1, 9, 3};
       std::sort(vec.begin(), vec.end());

       for (int num : vec) {
           std::cout << num << " ";
       }
       std::cout << std::endl;

       return 0;
   }
   ```
 ### Descending Order with sort()
   ```cpp
   //Descending order
   #include <iostream>
   #include <vector>
   #include <algorithm>

   int main() {
       std::vector<int> vec = {5, 2, 7, 1, 9, 3};
       std::sort(vec.begin(), vec.end(),greater<int>());

       for (int num : vec) {
           std::cout << num << " ";
       }
       std::cout << std::endl;

       return 0;
   }
   ```
## sort() with custom Comparison function
`std::sort()` can be overloaded to use custom comparison functions or function objects for sorting in different orders. Here's an example demonstrating how to use a custom comparison function to sort a vector of strings in descending order of length:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

// Custom comparison function for sorting strings by length in descending order
bool compareByLength(const std::string& a, const std::string& b) {
    return a.length() > b.length();
}

int main() {
    std::vector<std::string> vec = {"apple", "banana", "orange", "strawberry", "kiwi"};

    // Sorting the vector using the custom comparison function
    std::sort(vec.begin(), vec.end(), compareByLength);

    // Printing the sorted vector
    for (const auto& str : vec) {
        std::cout << str << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

In this example, `compareByLength()` is a custom comparison function that compares strings by their lengths in descending order. This function is passed as the third argument to `std::sort()`, which causes `std::sort()` to use this comparison function to determine the order of elements in the vector.


## sort() using function Objects 

Instead of using a simple comparison function, you can use function objects (also known as functors) for sorting in different orders. Functors are classes that define the `operator()` function, allowing them to be called as if they were functions.

Here's an example using a functor to sort a vector of integers in descending order:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

// Functor for sorting integers in descending order
struct CompareDescending {
    bool operator()(int a, int b) const {
        return a > b;
    }
};

int main() {
    std::vector<int> vec = {5, 2, 7, 1, 9, 3};

    // Sorting the vector using the functor
    std::sort(vec.begin(), vec.end(), CompareDescending());

    // Printing the sorted vector
    for (int num : vec) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

In this example:

- `CompareDescending` is a functor with the `operator()` overloaded to compare integers in descending order.
- We create an instance of `CompareDescending` and pass it as the third argument to `std::sort()`.
- `std::sort()` uses the functor's `operator()` to compare elements while sorting the vector.

Using function objects gives you more flexibility, as you can define more complex behavior within the functor, including stateful operations and even custom constructor arguments if needed.

## lambda expression with sort()

You can use lambda expressions with `std::sort()` to provide custom comparison logic inline without defining a separate comparison function or functor. Lambda expressions allow you to define anonymous functions directly at the call site.

Here's an example of using `std::sort()` with a lambda expression to sort a vector of strings in descending order of length:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<std::string> vec = {"apple", "banana", "orange", "strawberry", "kiwi"};

    // Sorting the vector in descending order of string length using a lambda expression
    std::sort(vec.begin(), vec.end(), [](const std::string& a, const std::string& b) {
        return a.length() > b.length();
    });

    // Printing the sorted vector
    for (const auto& str : vec) {
        std::cout << str << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

In this example:

- We use a lambda expression `[](const std::string& a, const std::string& b) { return a.length() > b.length(); }` as the third argument to `std::sort()`.
- The lambda expression defines a custom comparison function inline. It compares two strings based on their lengths in descending order.
- `std::sort()` then uses this lambda expression to sort the vector of strings accordingly.

Lambda expressions are concise and allow you to define custom behavior directly within the call site of a function, making your code more readable and expressive.
