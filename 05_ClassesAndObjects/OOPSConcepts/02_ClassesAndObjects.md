# Classes and Objects in C++!

### Classes:
In C++, a class is a blueprint for creating objects. It defines a data type by grouping related data members (variables) and member functions (methods). Here's a simple example:

```cpp
// Class declaration
using namespace std;
#include <iostream>
class Car {
private:
    // Data members
    string brand;
    int year;

public:
    // Member functions
    void setBrand(string b) {
        brand = b;
    }

    void setYear(int y) {
        year = y;
    }

    void displayInfo() {
        cout << "Brand: " << brand << ", Year: " << year << std::endl;
    }
};
```

### Objects:
An object is an instance of a class. It's created using the class blueprint and can access the data members and member functions defined within that class.

```cpp
int main() {
    // Creating objects of the Car class
    Car car1, car2;

    // Accessing member functions using objects
    car1.setBrand("Toyota");
    car1.setYear(2020);
    car1.displayInfo();

    car2.setBrand("BMW");
    car2.setYear(2018);
    car2.displayInfo();

    return 0;
}
```

In this example:
- `Car` is the class that defines the blueprint.
- `car1` and `car2` are objects of the `Car` class.
- `setBrand`, `setYear`, and `displayInfo` are member functions accessed by objects to manipulate or display data.

### Class Members Access:
- `Private`: Data members and functions declared as private are accessible only within the class. They cannot be accessed directly from outside the class.
- `Public`: Data members and functions declared as public are accessible from outside the class through objects.


Classes and objects in C++ facilitate the organization and encapsulation of data and functionalities, making code more manageable and reusable.
