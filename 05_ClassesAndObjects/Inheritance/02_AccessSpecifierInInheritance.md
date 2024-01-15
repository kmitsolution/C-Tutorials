# Access Specifiers in Inheritance 

In C++, when deriving a class from a base class, you can choose from three access specifiers: `public`, `protected`, and `private`. The choice of the access specifier determines the visibility of the base class members in the derived class. Here's a brief explanation of each:

1. **Public Inheritance:**
   - Syntax: `class Derived : public Base {...}`
   - Public members of the base class remain public in the derived class.
   - Protected members of the base class remain protected in the derived class.
   - Private members of the base class remain inaccessible in the derived class.

```cpp
class Base {
public:
    int publicMember;
protected:
    int protectedMember;
private:
    int privateMember;
};

class Derived : public Base {
    // publicMember is public
    // protectedMember is protected
    // privateMember is not accessible
};
```

2. **Protected Inheritance:**
   - Syntax: `class Derived : protected Base {...}`
   - Public members of the base class become protected in the derived class.
   - Protected members of the base class remain protected in the derived class.
   - Private members of the base class remain inaccessible in the derived class.

```cpp
class Base {
public:
    int publicMember;
protected:
    int protectedMember;
private:
    int privateMember;
};

class Derived : protected Base {
    // publicMember is protected
    // protectedMember is protected
    // privateMember is not accessible
};
```

3. **Private Inheritance:**
   - Syntax: `class Derived : private Base {...}`
   - All members of the base class become private in the derived class.
   - Regardless of their original access specifiers, all members are treated as private in the derived class.

```cpp
class Base {
public:
    int publicMember;
protected:
    int protectedMember;
private:
    int privateMember;
};

class Derived : private Base {
    // publicMember is private
    // protectedMember is private
    // privateMember is private
};
```

In your case, if you want the derived class `MarutiCar` to have access to the public members of the base class `Car`, you should use `public` inheritance:

```cpp
class MarutiCar : public Car {
    // Your implementation here
};
```
