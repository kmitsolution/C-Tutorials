# Dynamic Polymorphism

In C++, virtual functions play a key role in achieving polymorphism. Polymorphism is the ability of a single interface to represent different underlying types, and it comes in two forms: compile-time polymorphism (achieved through function overloading and templates) and runtime polymorphism (achieved through virtual functions).

Here's a brief explanation of how virtual functions contribute to achieving runtime polymorphism:

1. **Virtual Functions:**
   - A virtual function is declared in a base class using the `virtual` keyword.
   - Virtual functions provide a way for a derived class to provide a specific implementation while adhering to the same interface defined in the base class.
   - The base class declares a virtual function, and the derived classes can override this function with their own implementation.

```cpp
class Base {
public:
    virtual void show() {
        // Base class implementation
    }
};

class Derived : public Base {
public:
    void show() override {
        // Derived class implementation
    }
};
```

2. **Polymorphic Behavior:**
   - When a base class pointer or reference is used to refer to an object of a derived class, and the base class has virtual functions, polymorphism comes into play.
   - The type of the object being referred to is determined at runtime.
   - The appropriate function is called based on the actual type of the object rather than the declared type of the pointer or reference.

```cpp
Base* ptr;
Base baseObj;
Derived derivedObj;

ptr = &baseObj;
ptr->show();  // Calls Base::show()

ptr = &derivedObj;
ptr->show();  // Calls Derived::show()
```

In the example above, the `show()` function is called through a pointer of type `Base*`. The actual function that gets executed is determined at runtime based on the type of the object being pointed to. This behavior allows for dynamic dispatch, enabling more flexible and extensible code.

3. **Dynamic Binding:**
   - The mechanism behind this behavior is known as dynamic binding.
   - Dynamic binding ensures that the correct function is called at runtime, making it possible to achieve polymorphism.

```cpp
Base* ptr;
Base baseObj;
Derived derivedObj;

ptr = &baseObj;
ptr->show();  // Dynamic binding resolves to Base::show()

ptr = &derivedObj;
ptr->show();  // Dynamic binding resolves to Derived::show()
```

## Complete Example
```cpp
#include <iostream>

class Base {
public:
    virtual void show() {
        std::cout << "Base class\n";
    }
};

class Derived : public Base {
public:
    void show() override {
        std::cout << "Derived class\n";
    }
};

int main() {
    Base* basePtr;
    Base baseObj;
    Derived derivedObj;

    basePtr = &baseObj;
    basePtr->show();  // Calls Base::show()

    basePtr = &derivedObj;
    basePtr->show();  // Calls Derived::show()

    return 0;
}

```

In summary, virtual functions and dynamic binding enable runtime polymorphism in C++. They provide a powerful mechanism for building flexible and extensible code by allowing different derived classes to provide their own implementations for the same interface defined in a base class.
