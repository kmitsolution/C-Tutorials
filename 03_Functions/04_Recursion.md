# Recursion in C++
Recursion is a programming technique where a function calls itself to solve smaller instances of a problem, repeating this process until it reaches a base case where the solution is known.

### Example - Factorial using Recursion:

```cpp
#include <iostream>
using namespace std;

// Recursive function to calculate factorial
int factorial(int n) {
    if (n <= 1) {
        return 1; // Base case: factorial of 0 and 1 is 1
    } else {
        return n * factorial(n - 1); // Recursive call
    }
}

int main() {
    int num = 5;
    cout << "Factorial of " << num << " is: " << factorial(num) << endl;
    return 0;
}
```

- In this example, the `factorial()` function calculates the factorial of a number `n`.
- The base case is when `n` is 0 or 1, where the factorial is known to be 1.
- For other values of `n`, the function calls itself with `factorial(n - 1)` to solve a smaller instance of the problem.
- It keeps calling itself recursively until it reaches the base case, and then returns the result back up the chain of function calls.


Recursion is elegant for certain problems but might not be as efficient as iterative approaches due to the overhead of function calls and stack usage. However, it offers a clear and concise way to solve problems that have a natural recursive structure.
