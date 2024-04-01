In C++, the Standard Template Library (STL) provides a rich set of containers and algorithms to manipulate data efficiently. Here's a brief overview of how you can manipulate data using STL containers and algorithms:

1. **Containers:**

   STL provides various container classes like vectors, lists, sets, maps, etc., which can be used to store and manipulate data efficiently.

   ```cpp
   #include <iostream>
   #include <vector>
   #include <algorithm>

   int main() {
       // Vector container
       std::vector<int> vec = {3, 1, 4, 1, 5, 9, 2, 6};

       // Sorting
       std::sort(vec.begin(), vec.end());

       // Iterating and printing
       for (int num : vec) {
           std::cout << num << " ";
       }
       std::cout << std::endl;

       return 0;
   }
   ```

2. **Algorithms:**

   STL provides a wide range of algorithms for common operations like sorting, searching, modifying, etc.

   ```cpp
   #include <iostream>
   #include <vector>
   #include <algorithm>

   int main() {
       // Vector container
       std::vector<int> vec = {3, 1, 4, 1, 5, 9, 2, 6};

       // Sorting
       std::sort(vec.begin(), vec.end());

       // Iterating and printing
       for (int num : vec) {
           std::cout << num << " ";
       }
       std::cout << std::endl;

       // Find
       auto it = std::find(vec.begin(), vec.end(), 5);
       if (it != vec.end()) {
           std::cout << "Found 5 at index " << std::distance(vec.begin(), it) << std::endl;
       } else {
           std::cout << "5 not found" << std::endl;
       }

       return 0;
   }
   ```

3. **Iterators:**

   Iterators provide a way to traverse through containers and can be used with algorithms for data manipulation.

   ```cpp
   #include <iostream>
   #include <vector>
   #include <algorithm>

   int main() {
       // Vector container
       std::vector<int> vec = {3, 1, 4, 1, 5, 9, 2, 6};

       // Using iterators
       for (auto it = vec.begin(); it != vec.end(); ++it) {
           *it *= 2; // Double each element
       }

       // Iterating and printing
       for (int num : vec) {
           std::cout << num << " ";
       }
       std::cout << std::endl;

       return 0;
   }
   ```

These are just some basic examples. STL provides many more containers and algorithms that can be used to manipulate data effectively in C++.
