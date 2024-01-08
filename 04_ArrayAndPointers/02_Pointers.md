# Pointers in C++

Pointers in C++ are variables that store memory addresses. They are powerful but can be a bit tricky to handle. Here are some key points about pointers:

1. **Memory Address**: Pointers store the memory address of another variable, allowing you to indirectly manipulate that variable.

2. **Declaration**: Declaring a pointer is done by appending an asterisk (*) to the variable type. For instance, `int *ptr;` declares a pointer to an integer.

3. **Initializing Pointers**: Initialize pointers by assigning them the address of another variable. For example:
    ```cpp
    int num = 10;
    int *ptr = &num; // ptr now holds the memory address of num
    ```

4. **Dereferencing**: Access the value a pointer is pointing to using the dereference operator (*). For instance:
    ```cpp
    int value = *ptr; // value is now 10 (the value that ptr is pointing to)
    ```

5. **Null Pointers**: Pointers can be set to null (`nullptr` in modern C++) to indicate that they're not pointing to any valid memory address. It helps avoid "wild" pointers.
    ```cpp
    int *ptr = nullptr; // Null pointer
    ```

6. **Pointer Arithmetic**: C++ allows arithmetic operations on pointers (e.g., incrementing/decrementing). This can be used to traverse arrays or manipulate memory.
    ```cpp
    int arr[5] = {1, 2, 3, 4, 5};
    int *p = arr; // Points to the first element of the array
    cout << *p << endl; // Prints the value at arr[0]
    p++; // Moves to the next element
    cout << *p << endl; // Prints the value at arr[1]
    ```

7. **Dynamic Memory Allocation**: Pointers are commonly used with `new` and `delete` keywords to dynamically allocate and deallocate memory:
    ```cpp
    int *ptr = new int; // Allocates memory for an integer
    *ptr = 5; // Assigns 5 to the memory location
    delete ptr; // Deallocates the memory
    ```

8. **Pointers and Functions**: Pointers are often used in passing arguments to functions by reference, allowing functions to modify the original data.
    ```cpp
    void modify(int *ptr) {
        *ptr = 20;
    }
    int value = 10;
    modify(&value); // Passes the address of value to modify function
    ```

9. **Pointer to Pointer**: A pointer can also store the address of another pointer. This is known as a pointer to a pointer.
    ```cpp
    int num = 5;
    int *ptr = &num;
    int **ptrToPtr = &ptr; // Pointer to a pointer
    ```

## Some Examples

### Exmaple 1
```c
#include <iostream>
using namespace std;

int main() {
  int i=10;
  int *ptr =&i;//Declare a pointer + Initialize
  int a[5]={1,2,3,4,5};
  cout<<"Address of i=" << &i<<endl;
  cout<<"Address stored in the pointer"<<ptr<<endl;
  i=20;
  cout<<"Value of inside ptr="<<*ptr<<endl;
  cout<<"Address of ptr="<<&ptr;
  *ptr=30;
  cout<<"Value of inside ptr="<<*ptr<<endl;
  cout<<"Value of i="<<i<<endl;
   }
```
### Example 2
```c
#include <iostream>
using namespace std;

int main() {
   //Array with Pointers
   int *ptr;
   int a[5]={1,2,3,4,5};
   ptr=a;
   cout<<"First Element in pointer="<<*ptr;
   ptr++;
   cout<<"Sec Element in pointer="<<*ptr;
   return 0;
}
```

### Example 3
```c
#include <iostream>
using namespace std;
void swap(int *x,int *y){
   int temp=*x;
   *x=*y;
   *y=temp;
}
int main() {
   int a=2,b=3;
   cout<<"Values before swapping A="<<a<<",B="<<b<<endl;
   swap(&a,&b);
   cout<<"Values after swapping A="<<a<<",B="<<b<<endl;
   return 0;
}
```

Remember, while pointers can be powerful, improper use can lead to memory leaks or undefined behavior. It's essential to manage them carefully, especially when dealing with memory allocation and deallocation.
