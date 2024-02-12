In C++, a virtual destructor is a destructor declared as virtual in a base class. When you have a base class with a virtual destructor, it allows derived classes to properly clean up resources allocated by the derived class itself. 

Here's a simple example to illustrate the concept:

```cpp
using namespace std;
#include<iostream>
class Base{
  public:
   Base(){
    cout<<"Base Class constructor"<<endl;
   }
   virtual ~Base(){
    cout<<"Base Class destructor"<<endl;
   }
};
class Child:public Base{
  public:
    Child(){
      cout<<"This is child class Constructor"<<endl;
    }
    ~Child(){
      cout<<"Child class destructor"<<endl;
    }
};
int main(){
  Base *ptr = new Child();
  delete ptr;
  return 0;
}
```

In this example:

- The `Base` class has a virtual destructor. This means that if a pointer to a `Base` object is deleted and it's pointing to a derived class object (in this case, a `Derived` object), the destructor of the derived class will also be called properly.
- The `Derived` class does not need to declare its destructor as virtual explicitly because it inherits the virtual destructor from the `Base` class.
- In the `main()` function, a pointer to a `Base` object is created and assigned to point to a `Derived` object. When this pointer is deleted, both the `Base` destructor and the `Derived` destructor will be called in the correct order due to the virtual destructor in the `Base` class.

Virtual destructors are particularly useful in scenarios where you're managing resources through pointers to base class objects and need to ensure proper cleanup of derived class resources.
