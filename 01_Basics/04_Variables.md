In C++, variables are containers used to store data values. Each variable has a specific data type that determines the type of data it can hold. Variables also have a name that uniquely identifies them within the program. Here's how you declare and use variables in C++:

### Syntax for declaring variables:
```cpp
data_type variable_name;
```

### Examples:

#### Integer Variable:
```cpp
int age; // Declaration of an integer variable named 'age'
age = 25; // Assigning a value to 'age'
```

#### Floating-Point Variable:
```cpp
double salary = 55000.5; // Declaration and initialization of a double variable named 'salary'
```

#### Character Variable:
```cpp
char grade = 'A'; // Declaration and initialization of a character variable named 'grade'
```

#### Boolean Variable:
```cpp
bool isStudent = true; // Declaration and initialization of a boolean variable named 'isStudent'
```

### Rules for naming variables in C++:
- Variable names can consist of letters, digits, and underscores.
- The first character must be a letter or an underscore.
- C++ is case-sensitive, so `age`, `Age`, and `AGE` would be considered different variables.
- Variable names cannot be a C++ keyword (like `int`, `double`, `if`, `while`, etc.).

### Initializing Variables:
Variables can be initialized (assigned an initial value) at the time of declaration or later in the program.

### Example of Declaration and Initialization:
```cpp
int quantity = 10; // Declaration and initialization of an integer variable named 'quantity' with a value of 10
```

### Changing Variable Values:
Variables can have their values changed during program execution:

```cpp
int x = 5; // Initialize 'x' with 5
x = 10; // Change the value of 'x' to 10
```

Understanding variables and their data types is essential in programming, as they allow you to store and manipulate different types of data within your C++ programs.
