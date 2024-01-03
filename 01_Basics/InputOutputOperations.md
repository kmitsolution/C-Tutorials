# Input Output (I/O) Operations in C++
In C++, input and output operations can be performed using the `<iostream>` header, which provides classes like `std::cin` and `std::cout` for handling input from the user and output to the console, respectively. Here's a basic example:

```cpp
#include <iostream>

int main() {
    // Output to the console
    std::cout << "Enter a number: ";

    // Input from the user
    int number;
    std::cin >> number;

    // Output the entered number
    std::cout << "You entered: " << number << std::endl;

    return 0;
}
```

In this example:
- `std::cout` is used to output the message "Enter a number: " to the console.
- `std::cin` is used to read the user's input, which is stored in the variable `number`.
- Finally, `std::cout` is again used to display the entered number along with a message.

Remember to include the `<iostream>` header at the beginning of your code to use these functionalities. Additionally, `std::endl` is used to insert a newline character and flush the output buffer.

Namespaces like `std` help prevent naming collisions by providing a way to group related code under a specific name. Using `std::cin` and `std::cout` means you're accessing the `cin` and `cout` objects within the `std` namespace, which is the standard namespace for C++ standard library components like input/output streams.

If you prefer, you can also use the `using` directive to avoid typing `std::` repeatedly:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Enter a number: ";

    int number;
    cin >> number;

    cout << "You entered: " << number << endl;

    return 0;
}
```

However, be cautious when using `using namespace std;` as it brings all the names from the `std` namespace into the current scope, which might lead to naming conflicts in larger programs.
