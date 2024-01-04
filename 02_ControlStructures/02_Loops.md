# Loops in C++
Loops in C++ allow you to execute a block of code repeatedly based on certain conditions. Here are some common types of loops in C++:

### 1. **for Loop**

The `for` loop is commonly used when you know the number of iterations required.

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "Iteration: " << i << endl;
    }

    return 0;
}
```

### 2. **while Loop**

The `while` loop executes a block of code as long as the specified condition is true.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 5) {
        cout << "Iteration: " << i << endl;
        i++;
    }

    return 0;
}
```

### 3. **do-while Loop**

The `do-while` loop is similar to the `while` loop, but it ensures that the block of code executes at least once before checking the condition.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    do {
        cout << "Iteration: " << i << endl;
        i++;
    } while (i < 5);

    return 0;
}
```

### Loop Control Statements

Additionally, C++ offers loop control statements to modify the behavior of loops:

- `break`: Terminates the loop and transfers control to the next statement after the loop.
- `continue`: Skips the current iteration and moves to the next iteration of the loop.
- `goto`: Transfers the control of the program to a specified label.

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        if (i == 2) {
            continue; // Skips iteration 2
        }
        if (i == 4) {
            break; // Terminates the loop at iteration 4
        }
        cout << "Iteration: " << i << endl;
    }

    return 0;
}
```

Loops provide a way to iterate through code blocks efficiently, allowing for repetitive tasks or operations based on certain conditions in C++.
