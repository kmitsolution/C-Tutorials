# Constructor Overloading
In C++, constructor overloading refers to the ability to define multiple constructors within a class, each with a different set of parameters. This allows objects of the class to be initialized in different ways. The compiler selects the appropriate constructor based on the number and types of arguments provided during the object creation.

Here's a simple example demonstrating constructor overloading in C++:

```cpp
#include <iostream>

class MyClass {
private:
    int x;
    int y;

public:
    // Default constructor
    MyClass() {
        x = 0;
        y = 0;
    }

    // Constructor with one parameter
    MyClass(int value) {
        x = value;
        y = 0;
    }

    // Constructor with two parameters
    MyClass(int valueX, int valueY) {
        x = valueX;
        y = valueY;
    }

    // Member function to display values
    void display() {
        std::cout << "x: " << x << ", y: " << y << std::endl;
    }
};

int main() {
    // Creating objects using different constructors
    MyClass obj1;           // Calls the default constructor
    MyClass obj2(5);        // Calls the constructor with one parameter
    MyClass obj3(3, 7);      // Calls the constructor with two parameters

    // Displaying values
    obj1.display();         // Output: x: 0, y: 0
    obj2.display();         // Output: x: 5, y: 0
    obj3.display();         // Output: x: 3, y: 7

    return 0;
}
```

In this example, the `MyClass` class has three constructors: a default constructor with no parameters, a constructor with one parameter, and a constructor with two parameters. Depending on how an object of the class is created, the appropriate constructor is called to initialize the object.
