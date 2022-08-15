// This is some basic info on c plus plus language for my
// future reference.

--------------------------------------------------------------------------------

                VECTOR

` vector<type> name;`

can by dynamically allocated, no need to put no_of_elem.

```cpp
vector<int> v(no_of_elements);
vector<int> v = {1,2,3,4,.....};

v.size(); // length of the vector
```

--------------------------------------------------------------------------------

            TOKEN ( our own implementation )

A token is a sequence of characters that represents something we consider
a unit such as a number or an operator. Thats the way a C++ compiler 
deals with its source. Actually, "tokenizing" in some form or another 
is the way most analysis of text starts. 

```cpp
class Token {
    public:
        char kind;
        int value;
        Token() {
            // constructor
        }
}

// or make a constructor externally
Token::Token(/* arguments*/) {
    // stuff
}

int main() {
    Token t; // constructor called
}
```

--------------------------------------------------------------------------------

operator << is called the insertion or put to operator. It directs the contents of the variable
on its right to the object on its left.

cout is actually an object. It is predefined in C++ to correspond to the standard output stream. 
A stream is an abstraction that refers to a flow of data.

A preprocessor
directive, on the other hand, is an instruction to the compiler. A part of the compiler called the
preprocessor deals with these directives before it begins the real compilation process.

The keyword cin (pronounced “C in”) is an object, predefined in C++ to
correspond to the standard input stream. This stream represents data coming from the keyboard
(unless it has been redirected). The >> is the extraction or get from operator. It takes the value
from the stream object on its left and places it in the variable on its right

<< and >> operators have been overloaded, otherwise in C they act
as bitshifters.

When two arithmetic operators have the same precedence, the one on the left is executed first, 

Because arithmetic operators have a higher
precedence than relational operators

for loop is appropriate
when you know in advance how many times the loop will be executed. The while and do loops
are used when you don’t know in advance when the loop will terminate (the while loop when
you may not want to execute the loop body even once, and the do loop when you’re sure you
want to execute the loop body at least once).

The break statement causes an exit from a loop, just as it does from a switch statement. The
next statement after the break is executed is the statement following the loop. Figure 3.16
shows the operation of the break statement.

(Strictly speaking, the **continue** takes you to the closing brace of the loop body,
from which you may jump back to the top.)

A structure (as typically used) is a collection of
data, while a class is a collection of both data and functions. 

--------------------------------------------------------------------------------

```cpp
long var = 7678L;
const float PI = 3.14159F; 

float - 7 digit precision
double - 15 digit precision
```

The unsigned types are used when the quantities represented are always positive
unsigned int x;

```cpp
aCharVar = static_cast<char>(anIntVar);
char_var = (type)var; // c lang cast can also be used;
```

do-while loop

```cpp
do {

}
while(condn);
```

`min = (alpha<beta) ? alpha : beta;`

| Operator type | Operators               | Precedence |
| ------------- | ----------------------- | ---------- |
| Unary         | !, ++, ––, +, –         | Highest    |
| Arithmetic    | Multiplicative *, /, %  |            |
| Additive      | +, –                    |            |
| Relational    | Inequality <, >, <=, >= |            |
| Equality      | ==, !=                  |            |
| Logical       | And && Or \|            |            |
| Conditional   | ?:                      |            |
| Assignment    | =, +=, –=, *=, /=, %=   | Lowest     |

Nested struct can be created.

```cpp
struct a {
    str2 b;
};
```

when passed into a function the entire struct is copied
into the argument of the function. (pass by value) 

to access, struct1.struct2.member

Initialize nested structures:
    `Room dining = { {13, 6.5}, {10, 0.0} };`

structures cant be compared, but you can do it by operator
overloading.
However, in C++, structures can in fact hold both data and
functions

=======================================

Enum:

```cpp
enum days_of_week { Sun, Mon, Tue, Wed, Thu, Fri, Sat };
days_of_week day1, day2; 
day1 = Mon; 
day2 = Thu
An enumeration is a list of all possible values.
```

--------------------------------------------------------------------------------

                    REFERENCE

A reference provides an alias—a different name—for a variable. One of the most important
uses for references is in passing arguments to functions.

`function( type& name ) { /* proceed */}`

the argument variable entered into function() will be changed
and not be passed as a copy, thus passing it as a reference.

--------------------------------------------------------------------------------

c++ cast is more secure than c cast. Gives compile-time checking
thus less chances of error.

`static_cast<type>(casting_object);`

--------------------------------------------------------------------------------

Overloaded Function

- performs one type of operation on one type of data
  and another type on other type of data.

you cant overload with different return type.

```cpp
ret_type fxn_name();
ret_type fxn_name(arg_);
ret_type fxn_name(arg_1, arg_2);
```

--------------------------------------------------------------------------------

                            RECURSION !!

- extremely powerful.
- function calls itself.

Every recursive function must be provided with a way to end the recursion. Otherwise 
it will call itself forever and crash the program.

Is it true that many versions of a recursive function are stored in memory while it’s calling
itself? Not really. Each version’s variables are stored, but there’s only one copy of the function’s code. Even so, a deeply-nested recursion can create a great many stored variables, which
can pose a problem to the system if it doesn’t have enough space for them.

We mentioned that functions save memory space because all the calls to the function cause the
same code to be executed; the function body need not be duplicated in memory. When the
compiler sees a function call, it normally generates " a jump to the function ". At the end of the
function it jumps back to the instruction following the call, as shown in Figure 5.1 earlier in
this chapter.

While this sequence of events may save memory space, it takes some extra time. There must
be an instruction for the jump to the function (actually the assembly-language instruction
CALL or something similar), instructions for saving registers, instructions for pushing arguments onto the stack in the calling program and removing them from the stack in the function
(if there are arguments), instructions for restoring registers, and an instruction to return to the
calling program. The return value (if any) must also be dealt with. All these instructions slow
down the program.

```cpp
func() {
    base case;
    func();
}
```

--------------------------------------------------------------------------------

                            INLINE FUNCTION

- generally for short coded functions.
- compiles into inline code instead of a function.
- function body inserted into a program whenever the inline fxn invoked.

```cpp
inline ret_type fxn_name() {}
```

> Sometimes the compiler will ignore the request and compile the function as a normal function.
> It might decide the function is too long to be inline, for instance.

*Its like a macro in C*

--------------------------------------------------------------------------------                            

                            DEFAULT ARGUEMENTS

- work if the caller doesnt supply all necessary arguements.

```cpp
// in declaration, 
void fx(int=8, char='a');

// or (int a=8, char b='a');
```

- They must be missing arguements at the end of the list, because the compiler doesnt know that which arguement is put.

--------------------------------------------------------------------------------                        

                            SCOPE AND STORAGE

scope
: determines what part of the program can access it.

storage
: determines how long it stays in existance.

local scope - visible in a block
file scope - visible throughout the file.

automatic storage - exist until function
static storage - exist until the end of the program.

```cpp
    // global var assigned to 0 when created.
    int gobar;
    int main(){}
```

**static variable** (existant until end of program)
`static type var_name = val;`

> local variables and function arguements are stored in the stack, while global variables
> and static variables are stored in the heap. 
> (part of computer architechture)

--------------------------------------------------------------------------------

                            RETURN REFERENCE

```cpp
int& setx();
int x = 7;
int main() {
    setx() = 8; // sets x to 8
}

int& setx() {
    return x;
}
```

> for big data, passing by reference is better, as only the address is passed.

```cpp
void fun(const int& a);
// now the fxn cant modify it
```

--------------------------------------------------------------------------------

                        CLASSES AND OBJECTS

- object has the same relationship to a class that a variable has to
  a data type.
- An object is said to be an instance of a class.
  
  
  
  private, public - *feature* : data hiding.
 **private:** data within the class can be accessed by the functions of the class only.
**public:** access to all outside.

```cpp
class Car
{
public:
	// preferred initialization
	Car() : number(0), no(1) // member given the value before {executes}
	// to initialize the data with constructor
	{}
	// constructor overload
	Car(int nu) : number(nu)
	{}
	// not recommended initialization
	/*
	Car()
	{
		number = 0;
	}
	*/

	void set_number(int num) {
		number = num;
	}
	~Car(); // destructor
	void add_it(int, int); //declaration
private:
	int number;
	int no;
}; 

void Car::add_it(int x, int y) {

	// define outside class
}


```

- A constructor is a member function that is executed automatically whenever an object is created.

##### Default copy constructor

```cpp
// already built, copies one object into the getting-initialized obj.

	// in main
	Foo foo2(foo1); //  foo1 is already present.
	// copies all data members.

```

On the other hand, contrary to what you may have been led to believe, all the objects in
a given class use the same member functions. The member functions are created and placed in
memory only once—when they are defined in the class definition. This makes sense; there’s
really no point in duplicating all the member functions in a class every time you create another
object of that class, since the functions for each object are identical.



























