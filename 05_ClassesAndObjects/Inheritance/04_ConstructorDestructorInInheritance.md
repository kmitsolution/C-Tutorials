# Constructor and Destructor invocation in Inheritance
In C++, constructors and destructors play a crucial role in managing the lifecycle of objects. When it comes to inheritance, the base class and derived class may have their own constructors and destructors. Let's explore constructors and destructors in the context of C++ inheritance with examples.

### Constructors in Inheritance:

When you have a base class and a derived class, the constructors are called in a specific order:

1. The base class constructor is called first.
2. Then, the derived class constructor is called.

Here's an example:

```cpp
#include <iostream>

class Base {
public:
    Base() {
        std::cout << "Base class constructor called." << std::endl;
    }
};

class Derived : public Base {
public:
    Derived() {
        std::cout << "Derived class constructor called." << std::endl;
    }
};

int main() {
    Derived derivedObj;
    return 0;
}
```

Output:
```
Base class constructor called.
Derived class constructor called.
```

### Destructors in Inheritance:

The order of destructor calls is the reverse of the constructor calls:

1. The derived class destructor is called first.
2. Then, the base class destructor is called.

Here's an example:

```cpp
#include <iostream>

class Base {
public:
    ~Base() {
        std::cout << "Base class destructor called." << std::endl;
    }
};

class Derived : public Base {
public:
    ~Derived() {
        std::cout << "Derived class destructor called." << std::endl;
    }
};

int main() {
    Derived derivedObj;
    return 0;
}
```

Output:
```
Derived class destructor called.
Base class destructor called.
```

Remember that you don't need to explicitly call the base class constructor or destructor in the derived class; it happens automatically.

### Parameterized Constructors in Inheritance:

You can also have parameterized constructors in both base and derived classes. In such cases, the derived class constructor needs to explicitly call the base class constructor.

Example:

```cpp
#include <iostream>

class Base {
public:
    Base(int value) {
        std::cout << "Base class constructor called with value: " << value << std::endl;
    }
};

class Derived : public Base {
public:
    Derived(int value) : Base(value) {
        std::cout << "Derived class constructor called with value: " << value << std::endl;
    }
};

int main() {
    Derived derivedObj(42);
    return 0;
}
```

Output:
```
Base class constructor called with value: 42
Derived class constructor called with value: 42
```

In summary, constructors and destructors in C++ inheritance follow a specific order, and you can use them to manage the initialization and cleanup of objects in a hierarchy.
