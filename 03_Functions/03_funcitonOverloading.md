Function overloading in C++ allows you to have multiple functions with the same name but different parameter lists or types. This provides flexibility and allows you to create functions that perform similar operations but on different types or numbers of parameters.

### Example:

```cpp
#include <iostream>
using namespace std;

// Function overloading
void print(int num) {
    cout << "Integer number: " << num << endl;
}

void print(double num) {
    cout << "Double number: " << num << endl;
}

void print(string message) {
    cout << "Message: " << message << endl;
}

int main() {
    print(5);         // Calls print(int)
    print(7.89);      // Calls print(double)
    print("Hello!");  // Calls print(string)

    return 0;
}
```

- In this example, there are three functions named `print`, each with a different parameter type (`int`, `double`, `string`).
- When calling `print`, the compiler determines which function to invoke based on the arguments provided.
- The appropriate `print` function is chosen based on the type of argument passed.

Function overloading can be based on the number of parameters, their types, or both. However, overloading solely based on return type is not allowed in C++. This feature allows for cleaner code by using the same function name for operations that logically belong together but may vary in the type or number of parameters.
