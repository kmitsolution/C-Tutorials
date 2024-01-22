# const Member function

A `const` member function in C++ is a member function of a class that is declared with the `const` keyword. The purpose of declaring a member function as `const` is to indicate that this function does not modify the state of the object on which it is called. This is a key aspect of const-correctness in C++, allowing you to use member functions on `const` objects.

Here's a simple example to illustrate the concept of a `const` member function:

```cpp
#include <iostream>

class MyClass {
private:
    int value;

public:
    // Constructor
    MyClass(int val = 0) : value(val) {}

    // Const member function (getter)
    int getValue() const {
        // value = 10;  // Error! Cannot modify 'value' in a const member function
        return value;
    }

    // Non-const member function (setter)
    void setValue(int newVal) {
        value = newVal;
    }
};

int main() {
    // Create an object of MyClass
    MyClass obj(42);

    // Call const member function on a non-const object
    int retrievedValue = obj.getValue();
    std::cout << "Retrieved Value: " << retrievedValue << std::endl;

    // Call non-const member function on a non-const object
    obj.setValue(99);
    std::cout << "Updated Value: " << obj.getValue() << std::endl;

    // Create a const object of MyClass
    const MyClass constObj(23);

    // Call const member function on a const object
    int constValue = constObj.getValue();
    std::cout << "Const Object Value: " << constValue << std::endl;

    // Attempt to call non-const member function on a const object (error)
    // constObj.setValue(77);  // Error! setValue is non-const

    return 0;
}
```

In this example:

- The `getValue` member function is marked as `const`. It is a getter function that retrieves the value of the private member `value` without modifying it.

- The `setValue` member function is not marked as `const` because it modifies the internal state of the object by changing the value of `value`.

- In the `main` function, you can see how both const and non-const member functions are called on both const and non-const objects. Calling non-const member functions on const objects leads to compilation errors, enforcing the principle of const-correctness.

- # Another Example
- Let's consider a more advanced example involving a class representing a geometric point. We'll create a `Point` class with x and y coordinates and demonstrate the use of `const` member functions to access and manipulate the state of the object.

```cpp
#include <iostream>

class Point {
private:
    double x;
    double y;

public:
    // Constructor
    Point(double xCoord = 0.0, double yCoord = 0.0) : x(xCoord), y(yCoord) {}

    // Getter functions (const member functions)
    double getX() const {
        return x;
    }

    double getY() const {
        return y;
    }

    // Setter functions (non-const member functions)
    void setX(double newX) {
        x = newX;
    }

    void setY(double newY) {
        y = newY;
    }

    // Display function (const member function)
    void display() const {
        std::cout << "(" << x << ", " << y << ")" << std::endl;
    }

    // Move the point by specified deltas (non-const member function)
    void move(double deltaX, double deltaY) {
        x += deltaX;
        y += deltaY;
    }
};

int main() {
    // Create a Point object
    Point point(3.0, 4.0);

    // Use const member functions to access the state
    double xValue = point.getX();
    double yValue = point.getY();

    std::cout << "Original Point: ";
    point.display();

    std::cout << "X Coordinate: " << xValue << std::endl;
    std::cout << "Y Coordinate: " << yValue << std::endl;

    // Attempt to modify the point using const member functions (error)
    // point.setX(5.0);  // Error! setX is non-const
    // point.setY(7.0);  // Error! setY is non-const

    // Move the point using a non-const member function
    point.move(2.0, -1.0);

    std::cout << "Point after move: ";
    point.display();

    return 0;
}
```

In this example:

1. The `getX` and `getY` member functions are declared as `const`. These functions allow you to access the x and y coordinates of the point without modifying the state of the object.

2. The `setX` and `setY` member functions are non-const, as they modify the state of the `Point` object by changing its x and y coordinates.

3. The `display` member function is declared as `const` and is used to print the coordinates of the point. It doesn't modify the state of the object.

4. The `move` member function is a non-const function that allows the point to be moved by specified deltas in the x and y directions.

In the `main` function, you can see how const member functions are used to access the state of the `Point` object without modifying it. Attempts to call non-const member functions (like `setX` and `setY`) on a const object would result in compilation errors, enforcing const-correctness in the code. The `move` function, being non-const, modifies the state of the object and can be called on non-const objects.

# const memberfunction with const Object
When you have a `const` object of a class, you can only call member functions that are themselves marked as `const`. This is because calling a non-const member function on a `const` object could potentially modify its internal state, violating the const-correctness principle. Here's an example demonstrating the use of `const` member functions with a `const` object:

```cpp
#include <iostream>

class MyClass {
private:
    int value;

public:
    // Constructor
    MyClass(int val = 0) : value(val) {}

    // Getter function (const member function)
    int getValue() const {
        return value;
    }

    // Display function (const member function)
    void display() const {
        std::cout << "Value: " << value << std::endl;
    }

    // Non-const member function
    void setValue(int newVal) {
        value = newVal;
    }
};

int main() {
    // Create a const object of MyClass
    const MyClass constObj(42);

    // Call const member functions on a const object
    int retrievedValue = constObj.getValue();
    std::cout << "Retrieved Value: " << retrievedValue << std::endl;

    constObj.display();

    // Attempt to call a non-const member function on a const object (error)
    // constObj.setValue(99);  // Error! setValue is non-const

    return 0;
}
```

In this example:

- The `getValue` and `display` member functions are marked as `const` and can be called on a `const` object like `constObj`.
  
- The `setValue` member function is not marked as `const` because it modifies the internal state of the object. Attempting to call `setValue` on a `const` object results in a compilation error.

This ensures that when you have a `const` object, you are restricted to calling only member functions that don't modify the object's state. It helps in preventing accidental modifications to `const` objects and enhances the safety and clarity of your code.
