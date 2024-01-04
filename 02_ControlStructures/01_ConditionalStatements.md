# Conditional Statements in C++
Conditional statements in C++ help execute code based on certain conditions. Here are some examples:

### 1. **if Statement**

The `if` statement executes a block of code if a specified condition is true.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 10;

    if (num > 0) {
        cout << "Number is positive." << endl;
    }

    return 0;
}
```

### 2. **if-else Statement**

The `if-else` statement executes one block of code if the condition is true and another block if the condition is false.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = -5;

    if (num >= 0) {
        cout << "Number is non-negative." << endl;
    } else {
        cout << "Number is negative." << endl;
    }

    return 0;
}
```

### 3. **else-if ladder**

The `else-if` ladder allows checking multiple conditions.

## Example 1

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 0;

    if (num > 0) {
        cout << "Number is positive." << endl;
    } else if (num < 0) {
        cout << "Number is negative." << endl;
    } else {
        cout << "Number is zero." << endl;
    }

    return 0;
}
```
## Example 2
using namespace std;
#include<iostream>
#include<conio.h>
```c
 int marks;
    cout<<"Enter the marks"<<endl;
    cin>>marks;
    if(marks>=80)
      cout<<"Grade A Student";
    else if(marks>=70 )  
      cout<<"Grade B Student";
    else if(marks>=60 )  
      cout<<"Grade C Student";
    else
       cout<<"Kuch padee karolo ";
```

### 4. **Nested if Statements**

You can have `if` statements inside other `if` statements, creating nested conditions.

## Example 1

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 10;

    if (num >= 0) {
        if (num == 0) {
            cout << "Number is zero." << endl;
        } else {
            cout << "Number is positive." << endl;
        }
    } else {
        cout << "Number is negative." << endl;
    }

    return 0;
}
```

## Example 2

```c
using namespace std;
#include<iostream>
#include<conio.h>
int main() {
   
   char nationality;
   int age;
   cout<<"Enter the Nationality(Single Char I for Indians)"<<endl;
   nationality=getche();
   cout<<endl<<"Enter the age of voter" <<endl;
   cin>>age;
   if(nationality=='I' ){
      if(age>=18)
        cout<<" YES, you can vote!!"<<endl;
      else
        cout<<" Because your age is <18 so you Cannot vote"<<endl;
   }
   else
     cout<< "Because your nationality is not indian so you cannot vote"<<endl;

    return 0;
}
```

These conditional statements help control the flow of the program based on different conditions, allowing for more dynamic and responsive code execution in C++.
