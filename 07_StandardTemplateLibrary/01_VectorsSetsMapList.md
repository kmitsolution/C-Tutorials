In C++, there are several container classes provided by the Standard Template Library (STL) that allow you to store and manipulate collections of data efficiently. Here's an overview of some commonly used containers:

1. **Vectors (std::vector)**:
   Vectors are dynamic arrays that can resize themselves automatically when elements are added or removed. They provide random access to elements and can efficiently insert or remove elements at the end of the container.

   ```cpp
   #include <vector>
   #include <iostream>

   int main() {
       std::vector<int> vec = {1, 2, 3, 4, 5};
       
       // Accessing elements
       std::cout << "First element: " << vec[0] << std::endl;
       
       // Adding elements
       vec.push_back(6);
       
       // Iterating over elements
       for (int elem : vec) {
           std::cout << elem << " ";
       }
       std::cout << std::endl;
       
       return 0;
   }
   ```

2. **Lists (std::list)**:
   Lists are doubly linked lists. They allow constant time insertions and removals of elements anywhere in the container, but they do not provide random access to elements like vectors.

   ```cpp
   #include <list>
   #include <iostream>

   int main() {
       std::list<int> lst = {1, 2, 3, 4, 5};
       
       // Adding elements
       lst.push_back(6);
       lst.push_front(0);
       
       // Iterating over elements
       for (int elem : lst) {
           std::cout << elem << " ";
       }
       std::cout << std::endl;
       
       return 0;
   }
   ```

3. **Maps (std::map)**:
   Maps are associative containers that store key-value pairs. They are typically implemented as binary search trees, allowing efficient lookups, insertions, and deletions based on the keys.

   ```cpp
   #include <map>
   #include <iostream>

   int main() {
       std::map<std::string, int> ages;
       ages["Alice"] = 30;
       ages["Bob"] = 25;
       ages["Charlie"] = 35;
       
       // Accessing elements
       std::cout << "Bob's age: " << ages["Bob"] << std::endl;
       
       // Iterating over elements
       for (const auto& pair : ages) {
           std::cout << pair.first << ": " << pair.second << std::endl;
       }
       
       return 0;
   }
   ```

4. **Sets (std::set)**:
   Sets are containers that store unique elements in a sorted order. They do not allow duplicate elements.

   ```cpp
   #include <set>
   #include <iostream>

   int main() {
       std::set<int> s = {3, 1, 4, 1, 5, 9};
       
       // Adding elements
       s.insert(2);
       
       // Iterating over elements
       for (int elem : s) {
           std::cout << elem << " ";
       }
       std::cout << std::endl;
       
       return 0;
   }
   ```

These are just brief examples of how to use these containers. The Standard Template Library provides many more functionalities for each of these containers, such as iterators, algorithms, and customization options.
