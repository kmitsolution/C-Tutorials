# Object Oriented Programming System(OOPS)
Object-Oriented Programming (OOP) in C++ is a paradigm that structures a program around objects, data, and methods. Here's an introduction to key OOP concepts in C++:

### Classes and Objects:
- **Class**: It's a blueprint or a template for creating objects. It defines the attributes (data) and behaviors (methods/functions) that objects of that class will have.
  
  ```cpp
  class Car {
  public: // Access specifier
      // Attributes
      string brand;
      string model;
      int year;
      
      // Methods
      void displayInfo() {
          cout << "Brand: " << brand << ", Model: " << model << ", Year: " << year << endl;
      }
  };
  ```

- **Object**: An instance of a class. It's created using the class blueprint and represents a real-world entity.
  
  ```cpp
  Car myCar; // Creating an object of class Car
  myCar.brand = "Toyota";
  myCar.model = "Corolla";
  myCar.year = 2022;
  myCar.displayInfo(); // Calling a method on the object
  ```

### Encapsulation:
- **Encapsulation**: It's the bundling of data (attributes) and the functions (methods) that operate on the data within a single unit (class). It hides the internal state of objects from the outside world and only exposes the necessary functionalities through methods.

### Abstraction:
- **Abstraction**: It involves displaying only essential information to the user and hiding the details. Classes use abstraction by providing interfaces that define the behavior without exposing the underlying implementation.

### Inheritance:
- **Inheritance**: It's a mechanism where a class inherits properties and behavior (attributes and methods) from another class. It supports the concept of reusability.

  ```cpp
  class ElectricCar : public Car { // ElectricCar inherits from Car
  public:
      int batteryCapacity;
      // Additional methods specific to ElectricCar
  };
  ```

### Polymorphism:
- **Polymorphism**: It means having multiple forms. In C++, polymorphism is achieved through function overloading and virtual functions. Function overloading allows defining multiple functions with the same name but different parameters, while virtual functions enable runtime polymorphism.

### Example demonstrating OOP concepts in C++:

```cpp
#include <iostream>
#include <string>
using namespace std;

// Class declaration
class Circle {
private:
    double radius;
public:
    // Constructor
    Circle(double r) : radius(r) {}

    // Method to calculate area
    double area() {
        return 3.14159 * radius * radius;
    }
};

int main() {
    // Creating an object of class Circle
    Circle myCircle(5.0);

    // Accessing attributes and methods of the object
    cout << "Area of the circle: " << myCircle.area() << endl;

    return 0;
}
```

Understanding these core concepts is fundamental to leveraging the power and flexibility of object-oriented programming in C++. They facilitate better code organization, maintenance, and reusability.
