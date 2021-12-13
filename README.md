# CMP2241_Task 3 --> Const and & Report

## Name: Yasmin Yasser Ali

## Sec: 2

## B.N.: 53

## Github Page Link: 

### Const keyword usage in c++:
 const’ keyword stands for constant value. In C++, if we make an artifact of a C++ program as constant then its value cannot be changed during the program execution.
####There are many uses of const key word in c++:
##### (1)Constant variables
Once we declare the variable with const then we can never change this value later in the program.
######code example:
```cpp
void main(){
	const int n = 5;
	cout << n << endl
	n==6;
	cout<< n<< endl;
//in this code we will get an error saying that we cannot assign to a variable that is const
}
``` 

#### (2)Constant Pointers
We can also use ‘const’ keyword with pointers. It can be used in two possible ways:
#######pointer constant at time of declaration.
ust like constant variable, the value of constant pointer is initialized at the time of declaration and once declared then we can change the pointer variable.
We can also say that if we want that a pointer variable must always point to the same variable then we can make it constant.
######code example:
```cpp
void main(){
    int a = 5;
	int* const p=&a; 
	cout<< *p << endl;
//As the pointer variable ‘p’ is declared as const so it will always point to variable a.
    int b=4;
    p=&y;
//we tried to change the value of pointer variable ‘p’ which will lead to a compilation error
    cout<< *p << endl;
}
``` 
#######The value constant that the pointer is pointing to.
A pointer to const means that we can access the value of the variable through pointer variable but cannot change the value of the pointed variable through the pointer variable
######code example:
```cpp
void main(){
    int a = 5;
	int* const p=&a; 
	cout<< *p << endl;
//As the pointer variable ‘p’ is declared as const so it will always point to variable a.
    a=a+4;    //this is ok
    &p=&p+4;    //error
//we tried to change the value of pointer variable ‘p’ which will lead to a compilation error
    cout<< *p << endl;
}
``` 
It is important to note that the variable to what the pointer is pointing to is not constant itself which means that its value can be changed itself but cannot be changed through the pointer variable.

#### (3)Constant Function Arguments
We can use the const keyword with the arguments of a function. If an argument is declared as const then the function will not be allowed to change its value.
######code example:
```cpp
    int experiment(const int variable){
        variable=variable+9;     //an error cannot assign to a variable that is const 
        return variable;
    }
    void main(){
    cout<<experiment(1)<<endl;
}
```

#### (4)Constant Data Members of a Class
The keyword ‘const’ can also be used with the data members of a class. If we define a const data member of a class then we must have to initialize that data member through the constructor of the class. The value of const data members cannot be changed through the object of the variable.
######code example:
```cpp
class constructor{
 public:
    const double value1;
    constructor(double value2): value1(value2){};
};
void main(){
    constructor object(10.5);
    cout<<object.value1<<endl;
    object.value1=15.8;    //Error we cannot change the constant value of the variable value1.
    cout<<object.value1<<endl;
}        
```

#### (5)Constant Objects of a Class
If we declare an object of class as const then the values of data members cannot be changed later on. If we try to change the values of data members then compiler will generate an error.
######code example:
```cpp
class constructor{
 public:
    const double value1;
    constructor(double value2): 
    {
        value1=value2;
    }
};
void main(){
    const constructor object(10.5);
    cout<<object.value1<<endl;
    object.value1=15.8;    //Error we cannot change the constant value of the constant object
    cout<<object.value1<<endl;
} 
```


### & usage in c++:
The & symbol is used as an operator in C++.
####There are many uses of const key word in c++:

#### (1)Bitwise AND
The bitwise AND operator (&) compares each bit of the first operand to that bit of the second operand. If both bits are 1, the bit is set to 1. Otherwise, the bit is set to 0. Both operands to the bitwise AND operator must be of integral types.
######code example:
```cpp
int main() {  
   unsigned short x = 0x5555;      // pattern 0101 ...  
   unsigned short y = 0xAAAA;      // pattern 1010 ...  

   cout << hex << ( x & y ) << endl;
//This gives the output 0   
}
```

#### (2)Address Of operator
C++ provides two-pointer operators, which are Address of Operator (&) and Indirection Operator (*).
A pointer is a variable that contains the address of another variable or you can say that a variable that contains the address of another variable is said to "point to" the other variable. A variable can be any data type including an object, structure or again pointer itself.
######code example:
```cpp
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
The output will be:
```
Value of var :3000
Value of ptr :0xbff64494
Value of val :3000
```
