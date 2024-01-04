# Functions

In C++, functions are blocks of code that perform specific tasks and can be called and reused within a program. They consist of three main parts: declaration, definition, and calling.

### Declaration of a Function

The function declaration tells the compiler about the function's name, return type, and parameters (if any). It's usually placed in a header file or at the beginning of the code.

```cpp
// Function declaration
int add(int a, int b); // Return type is int, and it takes two int parameters
```

### Definition of a Function

The function definition contains the actual code that defines what the function does. It includes the function's return type, name, parameters, and the code block inside curly braces `{}`.

```cpp
// Function definition
int add(int a, int b) {
    return a + b;
}
```

### Calling a Function

To use a function, you call it by its name and pass the required arguments (if any). You can call the function from within other functions or from the `main()` function.

```cpp
#include <iostream>
using namespace std;

int add(int a, int b); // Function declaration

int main() {
    int result = add(3, 4); // Function call
    cout << "Result: " << result << endl;
    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

- In the example above, `add()` is declared at the top, defined later in the code, and then called from the `main()` function.
- Arguments are passed to the function (`add(3, 4)`), and the result is stored in the variable `result`.

Remember:
- Declarations provide a function's signature (return type, name, and parameters), while definitions contain the actual implementation.
- Function names must be unique within their scope.
- Functions allow for code modularity and reusability, making programs easier to understand and maintain.
