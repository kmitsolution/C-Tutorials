# Inheritance in C++ - Introduction

In C++, inheritance is a fundamental concept that allows you to create a new class based on an existing class, inheriting its properties and behaviors. The existing class is referred to as the base class or parent class, and the new class is called the derived class or child class.

Here's a basic example to illustrate the concept of inheritance:

```cpp
using namespace std;
#include <iostream>

// Base class
class Animal {
public:
    void eat() {
        cout << "Animal is eating." << endl;
    }

    void sleep() {
        cout << "Animal is sleeping." << endl;
    }
};

// Derived class
class Dog : public Animal {
public:
    void bark() {
        cout << "Dog is barking." << endl;
    }
};

int main() {
    // Create an instance of the derived class
    Dog myDog;

    // Accessing base class methods
    myDog.eat();
    myDog.sleep();

    // Accessing derived class method
    myDog.bark();

    return 0;
}
```

In this example, `Dog` is derived from the `Animal` class using the `public` access specifier. This means that the public members of the base class are accessible in the derived class. The `Dog` class inherits the `eat()` and `sleep()` methods from the `Animal` class and adds a new method `bark()`.

When an instance of `Dog` is created, it can access both the methods inherited from the `Animal` class and its own unique method. This is the essence of inheritance in C++. It promotes code reuse and allows you to create a hierarchy of classes with a shared set of functionalities.
