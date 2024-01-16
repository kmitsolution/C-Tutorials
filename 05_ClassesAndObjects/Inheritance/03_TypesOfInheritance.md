# Types of Inheritance

Let's go through each type of inheritance with examples:

### 1. Single Inheritance:

In single inheritance, a class can inherit from only one base class.

```cpp
#include <iostream>

// Base class
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating." << std::endl;
    }
};

// Derived class with single inheritance
class Dog : public Animal {
public:
    void bark() {
        std::cout << "Dog is barking." << std::endl;
    }
};

int main() {
    Dog myDog;
    myDog.eat();  // Accessing the base class member
    myDog.bark(); // Accessing member of the derived class

    return 0;
}
```

### 2. Multi-level Inheritance:

In multi-level inheritance, a derived class is created from another derived class.

```cpp
#include <iostream>

// Base class
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating." << std::endl;
    }
};

// Intermediate class
class Mammal : public Animal {
public:
    void giveBirth() {
        std::cout << "Mammal is giving birth." << std::endl;
    }
};

// Derived class with multi-level inheritance
class Dog : public Mammal {
public:
    void bark() {
        std::cout << "Dog is barking." << std::endl;
    }
};

int main() {
    Dog myDog;
    myDog.eat();       // Accessing the base class member
    myDog.giveBirth(); // Accessing member of the intermediate class
    myDog.bark();      // Accessing member of the derived class

    return 0;
}
```

### 3. Multiple Inheritance:

In multiple inheritance, a class can inherit from more than one base class.

```cpp
#include <iostream>

// First base class
class Shape {
public:
    void display() {
        std::cout << "This is a shape." << std::endl;
    }
};

// Second base class
class Color {
public:
    void setColor() {
        std::cout << "Color set." << std::endl;
    }
};

// Derived class with multiple inheritance
class ColoredShape : public Shape, public Color {
public:
    void displayColoredShape() {
        display();   // Accessing member of the first base class
        setColor();  // Accessing member of the second base class
        std::cout << "This is a colored shape." << std::endl;
    }
};

int main() {
    ColoredShape coloredShape;
    coloredShape.displayColoredShape(); // Accessing members from both base classes

    return 0;
}
```

### 4. Multipath Inheritance:

Multipath inheritance occurs when a class is derived from two or more classes, and these base classes have a common ancestor.

```cpp
#include <iostream>

// Base class
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating." << std::endl;
    }
};

// Intermediate classes
class Mammal : public Animal {
public:
    void giveBirth() {
        std::cout << "Mammal is giving birth." << std::endl;
    }
};

class Reptile : public Animal {
public:
    void layEggs() {
        std::cout << "Reptile is laying eggs." << std::endl;
    }
};

// Derived class with multipath inheritance
class Platypus : public Mammal, public Reptile {
public:
    void swim() {
        std::cout << "Platypus is swimming." << std::endl;
    }
};

int main() {
    Platypus myPlatypus;
    myPlatypus.eat();      // Accessing member from the common ancestor
    myPlatypus.giveBirth(); // Accessing member of the first intermediate class
    myPlatypus.layEggs();   // Accessing member of the second intermediate class
    myPlatypus.swim();      // Accessing member of the derived class

    return 0;
}
```

### 5. Hierarchical Inheritance:

In hierarchical inheritance, multiple derived classes inherit from a single base class.

```cpp
#include <iostream>

// Base class
class Shape {
public:
    void display() {
        std::cout << "This is a shape." << std::endl;
    }
};

// Derived classes with hierarchical inheritance
class Circle : public Shape {
public:
    void displayCircle() {
        std::cout << "This is a circle." << std::endl;
    }
};

class Square : public Shape {
public:
    void displaySquare() {
        std::cout << "This is a square." << std::endl;
    }
};

int main() {
    Circle circle;
    circle.display();        // Accessing member of the base class
    circle.displayCircle();  // Accessing member of the derived class

    Square square;
    square.display();        // Accessing member of the base class
    square.displaySquare();  // Accessing member of the derived class

    return 0;
}
```

### 6. Hybrid Inheritance:

Hybrid inheritance is a combination of two or more types of inheritance. It often involves multiple inheritance and can include any combination of the above types.

```cpp
#include <iostream>

// Base class
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating." << std::endl;
    }
};

// Intermediate class
class Mammal : public Animal {
public:
    void giveBirth() {
        std::cout << "Mammal is giving birth." << std::endl;
    }
};

// Another intermediate class
class Color {
public:
    void setColor() {
        std::cout << "Color set." << std::endl;
    }
};

// Derived class with hybrid inheritance
class ColoredMammal : public Mammal, public Color {
public:
    void displayColoredMammal() {
        eat();        // Accessing member of the first base class
        giveBirth();  // Accessing member of the intermediate class
        setColor();   // Accessing member of the second base class
        std::cout << "This is a colored mammal." << std::endl;
    }
};

int main() {
    ColoredMammal coloredMammal;
    coloredMammal.displayColoredMammal(); // Accessing members from multiple base classes

    return 0;
}
```

These examples demonstrate different types of inheritance in C++. The choice of inheritance type depends on the relationships between the classes and the design goals of your program.
