# Interfaces in C++
In C++, interfaces are typically implemented using abstract classes, often with pure virtual functions. An interface defines a contract specifying the behavior that a class must adhere to. Any class that implements an interface must provide concrete implementations for all the methods declared in that interface.

Here's how you can implement interfaces in C++ using abstract classes:

```cpp
using namespace std;
#include <iostream>

// Interface class representing a printable object
class IPrintable {
public:
    virtual void print() const = 0; // Pure virtual function
    virtual ~IPrintable() = default; // Virtual destructor (good practice for polymorphism)
};

// Concrete class implementing the IPrintable interface
class Document : public IPrintable {
public:
    void print() const override {
        cout << "Printing document..." << endl;
    }
};

// Another concrete class implementing the IPrintable interface
class Image : public IPrintable {
public:
    void print() const override {
        cout << "Printing image..." << endl;
    }
};

int main() {
    Document doc;
    Image img;

    // Polymorphic behavior using IPrintable interface
    IPrintable* printable1 = &doc;
    IPrintable* printable2 = &img;

    printable1->print(); // Calls Document's print() method
    printable2->print(); // Calls Image's print() method

    return 0;
}
```

In this example:

- `IPrintable` is an interface represented by the abstract class. It contains a pure virtual function `print()`, defining the common behavior that all printable objects must implement.
- `Document` and `Image` are concrete classes that implement the `IPrintable` interface by providing their own implementations for the `print()` function.
- In the `main()` function, polymorphism is demonstrated by creating pointers of type `IPrintable*` pointing to instances of concrete classes. When calling the `print()` method through these pointers, the appropriate implementation based on the actual object type is invoked, thanks to dynamic dispatch.

This approach allows for designing flexible and extensible code by defining clear interfaces that classes can adhere to while allowing for different implementations to be used interchangeably.
