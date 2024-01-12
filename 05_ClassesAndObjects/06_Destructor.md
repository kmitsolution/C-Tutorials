# Destructor in C++
In C++, a destructor is a special member function of a class that is called automatically when an object goes out of scope or is explicitly deleted. The primary purpose of a destructor is to perform cleanup tasks, such as releasing resources (e.g., memory, file handles) acquired by the object during its lifetime.

Here's the syntax for a destructor:

```cpp
class MyClass {
public:
    // Constructor
    MyClass() {
        // Constructor code
    }

    // Destructor
    ~MyClass() {
        // Destructor code
    }
};
```

A destructor is named with the same name as the class, preceded by a tilde (`~`). It does not take any parameters and has no return type. You can only have one destructor in a class.

Here's an example to illustrate the use of a destructor:

```cpp
#include <iostream>

class MyClass {
public:
    // Constructor
    MyClass() {
        std::cout << "Constructor called" << std::endl;
    }

    // Destructor
    ~MyClass() {
        std::cout << "Destructor called" << std::endl;
    }
};

int main() {
    // Creating an object
    MyClass obj; // Constructor called

    // Object goes out of scope, and the destructor is automatically called
    // Output: Destructor called

    return 0;
}
```

In this example, when the object `obj` goes out of scope at the end of the `main` function, the destructor is automatically called. You can also explicitly delete an object using the `delete` keyword, which will also trigger the destructor.

It's essential to note that if a class does not provide its own destructor, the compiler generates a default destructor automatically. The default destructor does nothing special in terms of cleanup. However, when a class involves dynamic memory allocation or resource management, it's common to define a custom destructor to release those resources properly.
