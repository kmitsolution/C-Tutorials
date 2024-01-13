
# Access Modifiers
In C++, access modifiers (`public`, `private`, `protected`) are keywords used within classes to control the visibility of class members (methods and variables). They define how these members can be accessed from within the class itself and from external code (such as functions outside the class or derived classes).

### Public Access Modifier:
- `public` members are accessible from anywhere: within the class, outside the class through objects, and in derived classes.
- Public members represent the interface to interact with the class.

Example:

```cpp
class Example {
public:
    int publicVar;

    void publicFunction() {
        // Code accessible from anywhere
    }
};
```

### Private Access Modifier:
- `private` members are accessible only within the class itself.
- They cannot be accessed directly from outside the class or from derived classes.

Example:

```cpp
class Example {
private:
    int privateVar;

    void privateFunction() {
        // Code accessible only within the class
    }
};
```

### Protected Access Modifier:
- `protected` members are accessible within the class and by derived classes.
- They are not accessible from outside the class, except by derived classes.

Example:

```cpp
class Base {
protected:
    int protectedVar;

    void protectedFunction() {
        // Code accessible within the class and its derived classes
    }
};
```

### Accessing Members:

- Public members can be accessed directly by objects of the class.
- Private and protected members cannot be accessed directly by objects from outside the class; instead, public member functions can be used to access or modify them indirectly.

```cpp
int main() {
    Example obj;
    obj.publicVar = 10;   // Accessing public member

    // obj.privateVar = 5;  // Error: private member inaccessible
    // obj.privateFunction(); // Error: private member function inaccessible

    return 0;
}
```
### Example

```c++
#include <iostream>
using namespace std;
class Car{
   
  private:
   string brand;
   string model;
   int year;
  public:
   void setBrand(string brand){
      this->brand=brand;
   }
   void setModel(string model){
      this->model=model;
   }
   void setYear(int year){
      this->year=year;
   }
   void display();
};
void Car:: display(){

      cout<<"Model="<<model<<endl;
      cout<<"Brand="   <<brand<<endl;
      cout<<"Year="<<year<<endl;;
   }

int main() {
   //raman's car
   Car ramancar;
   cout<<"---Raman's Car Details---"<<endl;
   ramancar.setBrand("Hyundai");//ramancar.brand="Hyundai";
   ramancar.setModel("Santro");
   ramancar.setYear(2013);
   
   ramancar.display();
   // anil's car
   cout<<"--Anil's Car Details----"<<endl;
   Car anilcar;
   anilcar.setBrand("Maruti");
   anilcar.setModel("Wagnor");
   anilcar.setYear(2022);
   anilcar.display();

   return 0;
}

```
### Importance:
Access modifiers enforce encapsulation, a fundamental principle of object-oriented programming. Encapsulation restricts direct access to certain parts of a class, providing control over how data is manipulated and protecting the internal state of an object. It allows for better maintainability, flexibility, and security in the codebase.
