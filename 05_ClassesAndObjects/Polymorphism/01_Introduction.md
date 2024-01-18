# Polymorphism in C++

Polymorphism in C++ is one of the four fundamental principles of object-oriented programming (OOP). It allows objects of different types to be treated as objects of a common base type. This enables you to write more flexible and extensible code. C++ supports two main types of polymorphism: compile-time (static) polymorphism and runtime (dynamic) polymorphism.

1. **Compile-Time Polymorphism:**
   - **Function Overloading:** In C++, you can define multiple functions with the same name but different parameter lists. The appropriate function is selected at compile time based on the arguments passed during the function call.
   
     ```cpp
     class Calculator {
     public:
         int add(int a, int b) {
             return a + b;
         }

         double add(double a, double b) {
             return a + b;
         }
     };
     ```

   - **Operator Overloading:** You can also overload operators for user-defined types, allowing you to define custom behavior for operators.
   
     ```cpp
     class Complex {
     public:
         Complex operator+(const Complex& other) const {
             return Complex(real + other.real, imag + other.imag);
         }
     };
     ```

2. **Runtime Polymorphism:**
   - **Virtual Functions:** Runtime polymorphism is achieved through the use of virtual functions. A virtual function is a member function in a base class that is declared using the `virtual` keyword. Derived classes can provide their own implementation of the virtual function, and the appropriate function is selected at runtime based on the actual type of the object.

     ```cpp
     class Shape {
     public:
         virtual void draw() {
             // Base class implementation
         }
     };

     class Circle : public Shape {
     public:
         void draw() override {
             // Derived class implementation
         }
     };

     class Square : public Shape {
     public:
         void draw() override {
             // Derived class implementation
         }
     };
     ```

   - **Dynamic Dispatch:** When working with pointers or references to base class objects, the actual function called is determined at runtime based on the type of the object being pointed to or referenced. This is known as dynamic dispatch.

     ```cpp
     Shape* shape1 = new Circle();
     Shape* shape2 = new Square();

     shape1->draw(); // Calls draw() in Circle
     shape2->draw(); // Calls draw() in Square

     delete shape1;
     delete shape2;
     ```

   - **Abstract Classes and Pure Virtual Functions:** Abstract classes contain one or more pure virtual functions, which are virtual functions declared with "= 0". Objects of abstract classes cannot be instantiated, but they can serve as base classes for derived classes that provide concrete implementations for the pure virtual functions.

     ```cpp
     class AbstractShape {
     public:
         virtual void draw() const = 0; // Pure virtual function
     };

     class ConcreteCircle : public AbstractShape {
     public:
         void draw() const override {
             // Implementation for ConcreteCircle
         }
     };
     ```

Polymorphism in C++ allows for more flexible and modular code, making it easier to extend and maintain software systems. It enables code to work with objects of different types through a common interface, promoting code reuse and abstraction.
