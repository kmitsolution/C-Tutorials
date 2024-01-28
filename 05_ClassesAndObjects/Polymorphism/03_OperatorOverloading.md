Operator overloading in C++ allows you to define how operators behave when applied to user-defined types. This enables you to provide a natural and intuitive syntax for operations involving objects of your class. Here's an example of operator overloading:

```cpp
using namespace std;
#include <iostream>

class Complex {
private:
    double real;
    double imag;

public:
    // Constructors
    Complex() : real(0.0), imag(0.0) {}
    Complex(double r, double i) : real(r), imag(i) {}

    // Overloading the '+' operator
    Complex operator+(const Complex& other) const {
        Complex result;
        result.real = real + other.real;
        result.imag = imag + other.imag;
        return result;
    }

    // Overloading the '-' operator
    Complex operator-(const Complex& other) const {
        Complex result;
        result.real = real - other.real;
        result.imag = imag - other.imag;
        return result;
    }

    // Overloading the '*' operator
    Complex operator*(const Complex& other) const {
        Complex result;
        result.real = (real * other.real) - (imag * other.imag);
        result.imag = (real * other.imag) + (imag * other.real);
        return result;
    }

    // Overloading the '==' operator
    bool operator==(const Complex& other) const {
        return (real == other.real) && (imag == other.imag);
    }

    // Overloading the '<<' operator for output
    friend ostream& operator<<(ostream& os, const Complex& c) {
        os << c.real << " + " << c.imag << "i";
        return os;
    }
};

int main() {
    Complex a(2.0, 3.5);
    Complex b(1.5, 4.2);

    // Using overloaded operators
    Complex sum = a + b;
    Complex difference = a - b;
    Complex product = a * b;

    // Using overloaded '==' operator
    bool isEqual = (a == b);

    // Using overloaded '<<' operator for output
    cout << "a: " << a << endl;
    cout << "b: " << b << endl;
    cout << "a + b: " << sum << endl;
    cout << "a - b: " << difference << endl;
    cout << "a * b: " << product << endl;
    cout << "a == b: " << boolalpha << isEqual << endl;

    return 0;
}
```

In this example:

- The `Complex` class represents complex numbers with real and imaginary parts.
- The `+`, `-`, `*`, and `==` operators are overloaded to provide custom implementations for these operations on `Complex` objects.
- The `<<` operator is overloaded as a friend function to provide a custom output format for `Complex` objects.

The `main` function demonstrates the use of these overloaded operators and how they enhance the readability and expressiveness of operations involving `Complex` objects.
