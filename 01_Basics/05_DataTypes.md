# Datatypes in C++
In C++, data types determine the type of data that a variable can hold. C++ provides several built-in data types, each with its own characteristics. Here are some of the commonly used data types:

<img src="https://github.com/kmitsolution/C_plus_plus-Tutorials/blob/main/images/Datatypesc%2B%2B.jpg.png" width=1200 height=600 />

### Primitive Data Types:
1. **Integer Types**:
   - `int`: Represents integers.Memory size 4 Bytes
   - `short`: Represents short integers.Memory size 2 Bytes
   - `long`: Represents long integers. Memory size 4 Bytes
   - `long long`: Represents longer integers. Memory size 8Bytes

2. **Floating-Point Types**:
   - `float`: Represents single-precision floating-point numbers. Memory size 4 Bytes
   - `double`: Represents double-precision floating-point numbers. Memory size 8 Bytes
   - `long double`: Represents extended-precision floating-point numbers. Memory size 12 Bytes

3. **Character Types**:
   - `char`: Represents a single character. Memory size 1 Byte
   - `char16_t` and `char32_t`: Unicode characters. Memory size 2 Bytes and 4 Bytest respectively.
   - `wchar_t`: Wide character type. 2 Bytes

4. **Boolean Type**:
   - `bool`: Represents Boolean values (either `true` or `false`). Memory size 1 Byte

### Derived Data Types:
1. **Arrays**: A collection of elements of the same data type.
2. **Pointers**: Variables that store memory addresses.
3. **References**: Provides an alias to an existing variable.


### User-Defined Data Types:
1. **Structures (struct)**: Groups different data types under one name.
2. **Classes**: Advanced structures that can include functions and data.
3. **Unions**: Similar to structures but share the same memory location for all its members.
4. **Enumerations (enums)**: User-defined data type with a set of named constants.

   
### Type Modifiers:
C++ provides type modifiers that can modify the properties of basic types:
- `signed` and `unsigned`: Modifiers used with integer types to declare whether they can hold negative values (`signed`) or only non-negative values (`unsigned`).
- `const`: Defines constants that cannot be modified.
- `volatile`: Indicates that a variable's value can be changed by something external (e.g., hardware).

### Examples:
```cpp
int age = 30;
double height = 5.8;
char grade = 'A';
bool isStudent = true;

int numbers[5] = {1, 2, 3, 4, 5}; // Array of integers
int* pointer = &age; // Pointer to an integer variable
```

Understanding data types in C++ is crucial for effectively managing memory, performing operations, and ensuring data integrity within your programs. Each data type has its range of values and occupies a specific amount of memory in the system, which affects program efficiency and behavior.
