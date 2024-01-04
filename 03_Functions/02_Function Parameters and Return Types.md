In C++, functions can have parameters and return types, enabling them to accept input values, perform operations, and return results. 

### Function Parameters

Parameters are the values that a function accepts. They are specified within the parentheses following the function name in the function declaration and definition.

#### Example:

```cpp
#include <iostream>
using namespace std;

// Function declaration with parameters
void greet(string name) {
    cout << "Hello, " << name << "!" << endl;
}

int main() {
    string userName = "Alice";
    greet(userName); // Function call with an argument
    return 0;
}

// Function definition with parameters
void greet(string name) {
    cout << "Hello, " << name << "!" << endl;
}
```

- In this example, `greet()` takes a `string` parameter named `name`.
- When calling the `greet()` function from `main()`, you pass a `string` argument (`userName`) that gets assigned to the `name` parameter inside the function.

### Return Types

Functions in C++ can return a value to the calling code using a specified return type. If a function does not return any value, its return type is `void`.

#### Example:

```cpp
#include <iostream>
using namespace std;

// Function declaration with return type
int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(3, 4); // Function call
    cout << "Result: " << result << endl;
    return 0;
}

// Function definition with return type
int add(int a, int b) {
    return a + b;
}
```

- The `add()` function takes two `int` parameters and returns their sum (`int`).
- The `main()` function calls `add(3, 4)`, which returns the result (`7`), and it gets stored in the `result` variable.
- `cout` then prints the result.

Understanding function parameters and return types is crucial as they allow functions to interact with the rest of the program, passing data in and out of the function.
