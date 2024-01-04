# Switch Statement in C++
The `switch` statement in C++ provides a way to perform different actions based on the value of a variable. It's particularly useful when you have a single variable and want to execute different code blocks depending on its value.

Here's an example:

```cpp
#include <iostream>
using namespace std;

int main() {
    int choice;
    cout << "Enter a number between 1 and 3: ";
    cin >> choice;

    switch (choice) {
        case 1:
            cout << "You entered 1." << endl;
            break;
        case 2:
            cout << "You entered 2." << endl;
            break;
        case 3:
            cout << "You entered 3." << endl;
            break;
        default:
            cout << "Invalid choice." << endl;
    }

    return 0;
}
```

- The `switch` statement evaluates the value of `choice`.
- If `choice` matches a `case` value, it executes the code block under that `case`.
- `break` is used to exit the `switch` block after executing the corresponding case.
- `default` is optional and used when none of the `case` values match the variable's value.

Remember, after executing the code in a `case`, if you don’t include `break`, the control will continue to the next `case`. This is called "falling through," and it can be used intentionally for certain scenarios.

Switch statements are efficient when dealing with a large number of cases compared to multiple `if-else` statements, but they have some limitations, such as only allowing constant integral expressions in case labels.
