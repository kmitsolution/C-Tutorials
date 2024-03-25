# Stable Sort in C++ STL
In C++ STL, you can perform a stable sort using the `std::stable_sort()` algorithm. Unlike `std::sort()`, which does not guarantee the preservation of the original order of equal elements, `std::stable_sort()` ensures that the relative order of equal elements remains unchanged after sorting.

The syntax of `std::stable_sort()` is similar to `std::sort()`:

```cpp
template<class RandomIt>
void stable_sort(RandomIt first, RandomIt last);

template<class RandomIt, class Compare>
void stable_sort(RandomIt first, RandomIt last, Compare comp);
```

- `first`: Iterator to the beginning of the range.
- `last`: Iterator to the end of the range.
- `comp`: A binary predicate function object used for comparison (optional). If not provided, the default comparison function (`operator<`) is used.

Here's an example demonstrating how to use `std::stable_sort()`:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = {5, 2, 7, 1, 9, 3};

    // Sort the vector using std::stable_sort()
    std::stable_sort(vec.begin(), vec.end());

    // Print the sorted elements
    std::cout << "Sorted elements: ";
    for (int num : vec) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
## Stable sort vs Sort Algorithm
Let's compare `std::sort()` and `std::stable_sort()` with an example to understand the difference between them:

Consider a vector of pairs where each pair consists of a name and its corresponding age. We want to sort this vector based on the ages. However, if two or more people have the same age, we want to maintain the original order of these individuals (i.e., sort them by age while preserving the order of appearance in the original vector).

Let's see how both `std::sort()` and `std::stable_sort()` behave in this scenario:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <string>

int main() {
    std::vector<std::pair<std::string, int>> people = {
        {"Alice", 25},
        {"Bob", 30},
        {"Charlie", 25},
        {"David", 20},
        {"Emily", 30}
    };

    // Using std::sort() to sort the vector by age
    std::sort(people.begin(), people.end(), [](const auto& a, const auto& b) {
        return a.second < b.second; // Sort by age
    });

    std::cout << "Using std::sort():" << std::endl;
    for (const auto& person : people) {
        std::cout << person.first << " (" << person.second << ")\n";
    }

    std::cout << std::endl;

    // Resetting the vector
    people = {
        {"Alice", 25},
        {"Bob", 30},
        {"Charlie", 25},
        {"David", 20},
        {"Emily", 30}
    };

    // Using std::stable_sort() to sort the vector by age while preserving the original order of people with the same age
    std::stable_sort(people.begin(), people.end(), [](const auto& a, const auto& b) {
        return a.second < b.second; // Sort by age
    });

    std::cout << "Using std::stable_sort():" << std::endl;
    for (const auto& person : people) {
        std::cout << person.first << " (" << person.second << ")\n";
    }

    return 0;
}
```

Output:

```
Using std::sort():
David (20)
Alice (25)
Charlie (25)
Bob (30)
Emily (30)

Using std::stable_sort():
David (20)
Alice (25)
Charlie (25)
Bob (30)
Emily (30)
```

- With `std::sort()`, the vector is sorted by age, but the original order of people with the same age may not be preserved. In this case, Alice and Charlie both have the same age (25), but their relative order is changed after sorting.

- With `std::stable_sort()`, the vector is sorted by age, and the original order of people with the same age is preserved. In this case, Alice and Charlie both have the same age (25), and their relative order remains the same after sorting.

In summary, `std::sort()` is faster but doesn't guarantee stability, while `std::stable_sort()` is slightly slower but preserves the original order of elements with the same key. Use `std::stable_sort()` when you need stability in sorting, and use `std::sort()` when stability is not required, and you prioritize performance.
In this example, the vector `vec` is sorted using `std::stable_sort()`. After the operation, the elements are sorted in ascending order, and the relative order of equal elements is preserved. If the original vector had equal elements, their relative order remains unchanged after sorting.
