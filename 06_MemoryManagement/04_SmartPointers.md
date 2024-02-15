Smart pointers and RAII (Resource Acquisition Is Initialization) are modern C++ programming techniques used for memory management, especially in managing dynamically allocated memory. They help to automate memory management tasks, reducing the risk of memory leaks and dangling pointers.

1. **Smart Pointers**:
    - Smart pointers are objects that act like pointers but provide automatic memory management.
    - They automatically handle memory deallocation when they go out of scope, making them safer than raw pointers.
    - The three main types of smart pointers in C++ are `std::unique_ptr`, `std::shared_ptr`, and `std::weak_ptr`.
    - `std::unique_ptr`: It represents exclusive ownership of a dynamically allocated object. When a `std::unique_ptr` goes out of scope or is explicitly reset, it releases the memory it owns.
    - `std::shared_ptr`: It allows multiple pointers to share ownership of the same dynamically allocated object. Memory is automatically deallocated when the last `std::shared_ptr` pointing to the object is destroyed.
    - `std::weak_ptr`: It is used in conjunction with `std::shared_ptr` to break potential cycles in ownership and prevent memory leaks.
    - Smart pointers help to avoid many common pitfalls associated with manual memory management, such as forgetting to deallocate memory or deallocating memory prematurely.
## Example 1:
```cpp
using namespace std;
#include<iostream>
#include<memory>
class TestClass{
  public:
   TestClass(){
       cout<<"Constructor is invoked"<<endl;
   }
   ~TestClass(){
       cout<<"Destructor is invoked"<<endl;
   }
};
int main(){
  //create a unique Pointer
  //unique_ptr<TestClass>objTest(new TestClass());
  unique_ptr<TestClass>objTest1 = make_unique<TestClass>(); // for Runtime exception
  return 0;
}


```

## Example2
```cpp
using namespace std;
#include<iostream>
#include<memory>
class TestClass{
  public:
   TestClass(){
       cout<<"Constructor is invoked"<<endl;
   }
   ~TestClass(){
       cout<<"Destructor is invoked"<<endl;
   }
};
int main(){
  shared_ptr<TestClass>objtest = make_shared<TestClass>();
  shared_ptr<TestClass> obj1 =objtest;
  cout<<"Strong Reference count="<<objtest.use_count()<<endl;//2
  shared_ptr<TestClass> obj2 = objtest;
  cout<<"Strong Reference count="<<objtest.use_count()<<endl;//3
  return 0;
}


```

2. **RAII (Resource Acquisition Is Initialization)**:
    - RAII is a programming idiom in C++ where resource management is tied to object lifetime.
    - Resources, such as dynamically allocated memory, file handles, or locks, are acquired during object construction and released during object destruction.
    - By utilizing RAII, resource cleanup becomes automatic, eliminating the need for explicit calls to deallocate resources.
    - RAII is often implemented using smart pointers to manage dynamically allocated memory.
    - Example of RAII in C++:
      ```cpp
      class File {
      private:
          FILE* file;
      public:
          File(const char* filename) {
              file = fopen(filename, "r");
              if (!file) {
                  // Handle error
              }
          }
          ~File() {
              if (file) {
                  fclose(file);
              }
          }
          // Other methods for file operations...
      };
      ```
    - In this example, the file resource is acquired (opened) during object construction and released (closed) during object destruction, ensuring proper resource cleanup even in the presence of exceptions or early returns.
    
Smart pointers and RAII are powerful techniques in C++ for managing resources and memory, contributing to safer and more maintainable code. They help prevent memory leaks, improve code readability, and reduce the likelihood of errors associated with manual memory management.
