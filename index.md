# Const keyword in C++

Const keyward in C++ is attached with any variable, pointer variable and methods.

### - Const variable
There are a certain set of rules for the declaration and initialization of the constant variables: 
- **The const variable cannot be left un-initialized at the time of the assignment.**
- **It cannot be assigned value anywhere in the program.**
- **Explicit value needed to be provided to the constant variable at the time of declaration of the constant variable.**

![This is an image](https://media.geeksforgeeks.org/wp-content/uploads/20201223212505/t1.png)

Below is the C++ program to demonstrate the above concept:
```c++
#include <iostream>
using namespace std;
 
// Driver Code
int main()
{
 
    // const int x;  CTE error
    // x = 9;   CTE error
    const int y = 10;
    cout << y;
 
    return 0;
}
```


Output:
```
10
```
### - Const Keyword With Pointer Variables
Pointers can be declared with a const keyword. So, there are three possible ways to use a const keyword with a pointer,
which are as follows:
- **When the pointer variable point to a const value** \
Below is the C++ program to implement the above concept:

```c++
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x{ 10 };
    char y{ 'M' };

    const int* i = &x;
    const char* j = &y;

    // Value of x and y can be altered,
    // they are not constant variables
    x = 9;
    y = 'A';

    // Change of constant values because,
    // i and j are pointing to const-int
    // & const-char type value
    // *i = 6;
    // *j = 7;

    cout << *i << " " << *j;
}
```
Output:
```
9 A
```
- **When the const pointer variable point to the value** \
Below is the C++ program to implement the above concept:

```c++
#include <iostream>
using namespace std;
 
// Driver Code
int main()
{
    // x and z non-const var
    int x = 5;
    int z = 6;
 
    // y and p non-const var
    char y = 'A';
    char p = 'C';
 
    // const pointer(i) pointing
    // to the var x's location
    int* const i = &x;
 
    // const pointer(j) pointing
    // to the var y's location
    char* const j = &y;
 
 
    // The values that is stored at the memory location can modified
    // even if we modify it through the pointer itself
    // No CTE error
    *i = 10;
    *j = 'D';
 
    // CTE because pointer variable
    // is const type so the address
    // pointed by the pointer variables
    // can't be changed
    // *i = &z;
    // *j = &p;
 
    cout << *i << " and " << *j
        << endl;
    cout << i << " and " << j;
 
    return 0;
}
```
Output:
```
9 and D
0x7ffd1ff8f830 and DC
```
- **When const pointer pointing to a const variable** \
Below is the C++ program to implement the above concept:
```c++
#include <iostream>
using namespace std;
 
// Driver code
int main()
{
    int x{ 9 };
 
    const int* const i = &x;
   
    // *i=10;  
    // The above statement will give CTE
    // Once Ptr(*i) value is
    // assigned, later it can't
    // be modified(Error)
 
    char y{ 'A' };
 
    const char* const j = &y;
   
    // *j='B';
    // The above statement will give CTE
    // Once Ptr(*j) value is
    // assigned, later it can't
    // be modified(Error)
 
    cout << *i << " and " << *j;
 
    return 0;
}
```
Output:
```
9 and A
```

### - Constant Methods
Like member functions and member function arguments, the objects of a class can also be declared as const.
An object declared as const cannot be modified and hence, can invoke only const member functions as these functions
ensure not to modify the object. \

Syntax:
```
const Class_Name Object_name;
```

# Usage of & symbol in c++
The & symbol is used as an operator in C++. It is used in 3 different places, one as a bitwise and operator,
one as a pointer address of operator and one as logical AND.

- **bitwise AND** \
The bitwise AND operator (&) compares each bit of the first operand to that bit of the second operand. If both bits
are 1, the bit is set to 1. Otherwise, the bit is set to 0. Both operands to the bitwise AND operator must be
of integral types. \


Example:
```c++
#include <iostream>  
using namespace std;
 
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  

   cout << hex << ( a & b ) << endl;
}
```
Output:
```
0
```

- **pointer address** \
C++ provides two-pointer operators, which are Address of Operator (&) and Indirection Operator (*). \
A pointer is a variable that contains the address of another variable or you can say that a variable that contains
the address of another variable is said to "point to" the other variable. A variable can be any data type
including an object, structure or again pointer itself.\
The address of Operator (&), and it is the complement of *. It is a unary operator that returns the address
of the variable(r-value) specified by its operand.\
Example:
```c++
#include <iostream>
using namespace std;

int main () {
   int  var;
   int  *ptr;
   int  val;

   var = 3000;

   // take the address of var
   ptr = &var;

   // take the value available at ptr
   val = *ptr;
   cout << "Value of var :" << var << endl;
   cout << "Value of ptr :" << ptr << endl;
   cout << "Value of val :" << val << endl;

   return 0;
}
```
Output:
```
Value of var :3000
Value of ptr :0xbff64494
Value of val :3000
```
- **Logical AND** \
True only if all the operands are true.\
Syntax:
```
expression1 && expression2
```


