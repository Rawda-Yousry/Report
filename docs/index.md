<u><h2 style="color:lightblue;">Const Usage in Code:</h2></u></br>

<b><p style="color:lightgreen;"> Constant Variables:</p></b>

When we declare a variable as const it must be initialized firstly then we cannot change its value later on as shown below.

```
{
 #include<iostream>
 using namespace std;

int main()
{
     const double pi = 3.14;
     pi = 2.1;
     cout<< pi <<endl;
}

}
```
if we tried the above code, compiling error will appear "you cannot assign to a variable that is const".</br></br>

<b><p style="color:lightgreen;"> Constant Pointers:</p></b>

if we want a pointer variable always point to the same variable then we can make it constant. Moreover, once we declared the pointer as constant and intializing it, we cannot change the pointer variable as shown below.

```
{
 #include<iostream>
 using namespace std;

 int main()
 {
     int x = 1;
     int* const p = &x;

     cout << *p <<endl;
     int z = 2;
     p  = &z;
     cout<< *p <<endl;

 }

}
```
So, if we tried the above code an error will appear while compiling "you cannot assign to a variable that is const".</br></br>

<b><p style="color:lightgreen;"> Pointer To Constant Variables:</p></b>
A pointer to const means that we can access through pointer variable (the value itself of the variable can be changed but the reference cannot be changed) as shown in the code below.
```
{
#include<iostream>
using namespace std;

int main()
{
      int x = 1;
      int* const p = &x;

      x=x+5; //No Error
      *p = *p+10; //Error

     cout << *p <<endl;

}

}
```
So, if we tried the above code a compiling error will appear "illegal, right operand has type ‘const int *"
</br></br>

<b><p style="color:lightgreen;">Constant Function Arguments:</p></b>

We can use the const keyword with the arguments of a function. If an argument is declared as const then the function will not be allowed to change its value. The same is explained in the following code.
```
{
 #include<iostream>
 using namespace std;
int test(const int b)
{
    a+=11; //Error
    return a;

}

 int main()
 {
     cout<< test(10) <<endl;
 }

}
```
So, if we tried the above code a compiling erroe will appear" you cannot assign to a variable that is const", as we cannot change the value of a as it declared as const.</br></br>

<b><p style="color:lightgreen;">Constant Data Members of a Class:</p></b>

The keyword ‘const’ can also be used with the data members of a class. If we define a const data member of a class then we must have to initialize that data member through the constructor of the class. The value of const data members cannot be changed through the object of the variable as shown in the code below.
```
{
 #include<iostream>
 using namespace std;

class Test
{
public: 
  const int a;
  Test(int b) : a(b) {} ;
};

int main()
{
    Test t(10);
    cout<<t.a<<endl;
    t.a=20;  //Error
    cout << t.a << endl;
}

}
```
in the above code ,the value of the constant data member is accessed by the object of the class but when we tried to change the value a compiling error appears.</br></br>

<b><p style="color:lightgreen;"> Constant in static array:</p></b>

when implementing a static array, the size of the array must be constant.so, we can make it as the following 

```
{
 #include<iostream>
 using namespace std;
 const int a=5;

 void main()
 {
    int arr[a]={1,2,3,4,5};
    for(int i = 0 ;i < a ; i++)
    {
        cout<<arr[i];
    }
 }

}
```

<b><p style="color:lightgreen;">Constant Objects of a Class:</p></b>

when we declare an object of class as const then the values of data members cannot be changed later on. If we try to change the values of data members then compiler will generate an error as shown in the following code.

```
{
 #include<iostream>
 using namespace std;

class Test
{
public: 
  int a;
  Test(int x)
  {
      a=x;
  }
};

 void main()
 {
    const Test t(10);
    cout<<t.a<<endl;
    t.a=20;   //Error
    cout<<t.a<<endl;
 }

}
```
Once we declared the object as const, we cannot change the values of its data members. And if we tried to do so a compiling error as in the above code.</br></br></br></br>

<u><h2 style="color:lightblue;">Ampersand Usage In Code:</h2></u>

<b><p style="color:lightgreen;">& to declare a reference to a type(local variables, class members, method parameters):</p></b>

If you use & in the left-hand side of a variable declaration, it means that you expect to have a reference to the declared type

```
{
 #include<iostream>
 using namespace std;

void main()
{
    int x=10;
    int &y= x;
}

}
```
This doesn't just mean that both x and y will have the same value, but they will actually point to the same place in the memory.</br></br>

<b><p style="color:lightgreen;">& to get the address of a variable:</p></b>

When using it on the right-hand side of a variable, it's also known as the "address-of operator",it'll return its address in the memory instead of the variable's value itself. It is useful for pointer declarations.

```
{
 #include<iostream>
 using namespace std;

void main()
{
    int*y;
    int x;
    y=&x;
}

}
```
</br></br>

<b><p style="color:lightgreen;"> & as a bitwise operator:</p></b>
It is the bitwise AND. an infix operator taking two numbers as inputs and doing an AND on each of the bit pairs of the inputs. Here is an example. 14 is represented as 1110 as a binary number and 42 can be written as 101010. So 1110 (14) will be zero filed from the left and then the operation goes like this.


![bitwise &](bitwise&.png)
</br></br>

<b><p style="color:lightgreen;">&& in logical expression:</p></b>

It is just a style of writing and operation in code.
</br></br>

<b><p style="color:lightgreen;">&& for declaring rvalue references:</p></b>

 An lvalue is an expression e that may appear on the left or on the right hand side of an assignment, whereas an rvalue is an expression that can only appear on the right hand side of an assignment,For example:

 ```
{
 #include<iostream>
 using namespace std;

void main()
{
  int a = 42;
  int b = 43;

  // a and b are both l-values:
  a = b; // ok
  b = a; // ok
  a = a * b; // ok

  // a * b is an rvalue it cannot appear in the left side:
  a * b = 42 //Error
}

}
```
Although rvalues can only appear on the right-hand side, still one can capture references to them. Those "captures" are called rvalue references and such variables have to be declared with double ampersands (&&).
</br></br>

<b><p style="color:lightgreen;">&= operator:</p></b>

The following example uses the &= operator to concatenate two String variables and assign the result to the first variable.
```
{
 #include<iostream>
 #include<string>
 using namespace std;

void main()
{
    string var1  = "Hello "
    string var2 = "World!"
    var1 &= var2
    //The value of var1 is now "Hello World!".
}

}
```
