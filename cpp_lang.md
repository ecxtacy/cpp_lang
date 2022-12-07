// This is some basic info on c plus plus language for my
// future reference.

--------------------------------------------------------------------------------

## Index

1. [token](#token)
2. [type-conversion](#type-conversion)
3. [do while loop](#do-while-loop)

















--------------------------------------------------------------------------------

 #### TOKEN ( our own implementation )

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

##### type-conversion

```cpp
aCharVar = static_cast<char>(anIntVar);
char_var = (type)var; // c lang cast can also be used;
```

##### do-while-loop

```cpp
do {

}
while(condn);
```

`min = (alpha<beta) ? alpha : beta;`

##### operator

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

##### struct

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

##### enum

```cpp
enum days_of_week { Sun, Mon, Tue, Wed, Thu, Fri, Sat };
days_of_week day1, day2; 
day1 = Mon; 
day2 = Thu
An enumeration is a list of all possible values.
```

--------------------------------------------------------------------------------

 ##### REFERENCE

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

##### overloaded-function

- performs one type of operation on one type of data
  and another type on other type of data.

you cant overload with different return type.

```cpp
ret_type fxn_name();
ret_type fxn_name(arg_);
ret_type fxn_name(arg_1, arg_2);
```

```cpp
    // you can do the following
    loop {
        break; // to exit
    }

    void function() {
        return; // to return from void fxn
    }
```

--------------------------------------------------------------------------------

 ##### RECURSION

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

 ##### INLINE FUNCTION

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

   ##### DEFAULT ARGUMENTS

- work if the caller doesnt supply all necessary arguements.

```cpp
// in declaration, 
void fx(int=8, char='a');

// or (int a=8, char b='a');
```

- They must be missing arguements at the end of the list, because the compiler doesnt know that which arguement is put.

--------------------------------------------------------------------------------                        

##### SCOPE AND STORAGE

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

  ##### RETURN REFERENCE

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

   ##### CLASSES AND OBJECTS

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

On the other hand, contrary to what you may have been led to believe, 

***all the objects in a given class use the same member functions.***

The member functions are created and placed in
memory only once—when they are defined in the class definition. This makes sense; there’s
really no point in duplicating all the member functions in a class every time you create another
object of that class, since the functions for each object are identical.

**If a data item in a class is declared as static, only one such item is created for the entire
class, no matter how many objects there are. A static data item is useful when all objects of the
same class must share a common item of information.** 
A member variable defined as static
has characteristics similar to a normal static variable: It is visible only within the class, but its
lifetime is the entire program. It continues to exist even if there are no objects of the class

```cpp
class foo
{
public:
    foo();
    ~foo();
private:
    static int fax; // declare in the class    
};

// but define outside the class
// acts more like a global variable
int foo::fax = 69;
```

- A *<a id="const-member-function">const</a> member function guarantees that it will never modify any of its class’s member data.*
  
  ```cpp
  // in a class
    public:
        void func() const
        {}
  ```

- When an object is declared as const, you can’t modify it. It follows that you can
  use only const member functions with it, because they’re the only ones that guarantee not to
  modify it.

--------------------------------------------------------------------------------

 ##### ARRAY

- using array as argument is same as a reference arguement as array is a pointer to the starting memory address.

`int fxn(array_name);`
// passes original array

- arrays can contain structures.
  to access the member:-
  
                        `arr_name[index].member_name;`

> Stacks are one of the cornerstones of the architecture of the microprocessors used in most modern
> computers. As we mentioned earlier, functions pass their arguments and store their return address on
> the stack. This kind of stack is implemented partly in hardware and is most conveniently accessed in
> assembly language. However, stacks can also be created completely in software. Software stacks offer
> a useful storage device in certain programming situations, such as in parsing (analyzing) algebraic
> expressions.                

> There is no bounds-checking in C++ arrays. If the program inserts something beyond the
> end of the array, neither the compiler nor the runtime system will object. However, the renegade
> data will probably be written on top of other data or the program code itself. This may cause
> bizarre effects or crash the system completely.

--------------------------------------------------------------------------------

   ##### STRING

1. C-STRING
2. String object wali c++ wali

```cpp
// ~~~~~~~~~~~~~~~~ c-string ~~~~~~~~~~~~~~~~~~~~


#include <cstring>
// c-string

char str[max];
cin >> str; // but then cin will not take whitespace
// extraction operator >> space is terminating character

// other init way
char aster[30] = "the string stuff";

// other way
char str[80];
cin.get(str, 80);
/*
    first arg get(address_where_input, max_size, termination_char);
    terminates on that char given as 3rd arg, otherwise default '\n' is taken as 3rd arg
*/
cout << str << endl; // whitespace prob fixed

strlen(str); // returns length of c-string
strcpy(destination, source);
strcat(str1, str2); // concatnates

// string array
char arry[max_element][max_length];
cout << arry[element_index] << endl;
// but some bytes are wasted for words less than max_length.
// optimization can be done by pointers.


// ~~~~~~~~~~~~~~~~~~~ Standard C++ string class ~~~~~~~~~~~~~~~~~~~~~~~

#include <string>

s1 = s2 + s3; // concatnate with +

// to make string
string a = "val";
string b("val_b");
string c;

c = "this one " + "and this one";

s1.swap(s2); // swaps s1 and s2

/* -------- reading input -------- */

string fullname, bio;
getline(cin, fullname); // read blanks
getline(cin, bio, '$'); // stop reading on $


// string class functions
// str_obj.function();

find(string_to_find); // returns index of char from where it starts
find_first_of(string_of_chars); // arg: any chars from which word starts first, finds them
// return -1 if not found

erase(start_indx, end_indx);
replace(strt_ind, end_ind, string_to_replace_with);
insert(start_index, string_obj);
append(no_of_times, char_to_append);

// ==, >, < operators can be used to compare strings.
// >, < sorts alphabetically

substr(start_index, end_index);
length(); // length of string object

at(index); // gives char at that index of string
obj.copy(to_char_array, length, start_index);
to_char_array[length] = 0; // put null character to convert to c-string
```

--------------------------------------------------------------------------------

##### OPERATOR OVERLOADING

```cpp
class Counter
{
private:
    unsigned int count;
public:
    Counter() : count(0)
    {}
    unsigned int get_count() {
        return count;
    }

    // here goes the overloading
    void operator ++ () { // prefix hai abhi bas
        ++count;
    }

}; 

Count c1;
++c1;
++c1;
// c1 is 2;
```

#### Nameless temporary objects

```cpp
Counter operator ++ () {
    ++count;
    return Counter(count); // unnamed temporary object initialized to this count
    // but then you require constructor arguement which initializes count
}

// to overload postfix

Counter operator ++ (int) { // just a syntax to make it postfix
    return Counter(count++);
}
```

- Here’s the key: ***The argument on the left side of the operator (dist1 in this case) is the object
  of which the operator is a member. The object on the right side of the operator (dist2) must
  be furnished as an argument to the operator. The operator returns a value, which can be assigned
  or used in other ways***

```cpp
Distance operator + (Distance) const { // you can put const or not
    // code goes here
}
```

[see this const here](#const-member-function)

- ==
- ++
- +
- > 
- <
- +=
- []
  can be overloaded easily    

### Mutable member

- when create a const obj, a mutable member can be changed
  
  ```cpp
  class Moot
  {
  public:
    Moot();
    ~Moot();
  private:
    mutable int size;    
    int sx;
  };
 

const Moot moot;
moot.change_size(); // valid
moot.change_sx(); // invalid
```
--------------------------------------------------------------------------------
##### INHERITANCE

- Inheritance is the process of creating new classes, called derived classes, from
existing or base classes.

- The derived class inherits all the capabilities of the base class but
can add embellishments and refinements of its own.

- if you don’t specify a constructor, the derived class will use an appropriate constructor from the base class.

- The answer is that member functions can
access members of the base class if the members are public, or if they are protected. They
can’t access private members. Any member data that the derived classes might
need to access should be made protected rather than private. This ensures that the class is
“inheritance ready.”

```cpp
// to inherit

class Cunter
{
public:
    Cunter();
    ~Cunter();
    void do() {}
};

class Cuntest : public Cunter // inherits all the features of the Cunter class
{
public:
    Cuntest() : Cunter() // call the parent constructor
    {}
    // overrride
    void do() {
        // do more stuff
        Cunter::do();
    }

};
// good practice to write the constructor for child, because it uses only
// default constructor of the parent, other it doesn't use
```

class A <-------- class B
   ^        public
   |
   | private
   |
   |
 class C 

now, only objects of C can access any data of A.
objects of B can access only public and protected data of A
```cpp
int a = objB.private // invalid
int a = objB.protected // invalid
int a = objB.public // valid

// all invalid
int a = objC.private
int a = objC.protected
int a = objC.public
```

> class A <------- class B <-------- class C 

multiple inheritance possible

```cpp
class A : public B, public C
{
public:
    A();
    ~A();

};
```

---

### POINTER

#### ptr-void

- `void *ptr;`

- // can point to anything

- array can be accessed using pointer notation

```cpp
int arr[5] = {1,2 ,3,4,5};

int x = *(arr+1); // element 2 in the array
```

- c-string last character is '\0' which makes false if put in a condition check.

```cpp
char *stg = "this";
// stg points to 't' in the string literal.
// *(stg+4) is the null character.

// read right to left
const int* cptrInt; //cptrInt is a pointer to constant int
int* const ptrcInt; //ptrcInt is a constant pointer to int

char *ar[3] = {"apples", "oranges", "bananas"};
```

| a   | p   | p   | l   | e   | s   | \0  | o   | r   | a   | n   | g   | e   | s   | \0  | b   | a   | n   | a   | n   | a   | s   | \0  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

###### memory-allocation

- the new operator. This versatile operator obtains memory from the operating system and returns a pointer to its starting point.

```cpp
char *mm;
mm = new char[length_of_memory]; // like malloc(in_c)
delete[] mm; // like free(in c)
// brackets indicated that we were deleting an array
```

- suppose you use new in a function. If the function uses a local variable as a pointer to this memory, the pointer will be destroyed when the function terminates, but the memory will be left as an orphan, taking up space that is inaccessible to the rest of the program. Thus it is always good practice, and often essential, to delete memory when you’re through with it.

- We should note a potential glitch in using destructors as shown in NEWSTR. If you copy one
  String object to another, say with a statement like s2 = s1, you’re really only copying the
  pointer to the actual (char*) string. Both objects now point to the same string in memory. But
  if you now delete one string, the destructor will delete the char* string, leaving the other
  object with an invalid pointer. This can be subtle, because objects can be deleted in nonobvious ways, such as when a function in which a local object has been created returns. 

```cpp
// access pointer obj member
Cry *cr;
cr = new Cry;// points to new Cry object

(*cr).member_1 = something; // inefficient and inelegant
cr->member_1 = something; // better
cr->a_function();


// another way
Distance& dist = *(new Distance); // new returns a pointer to memory block large enough for object
// dist is a reference alias
dist.get_dis();
dis.show_dis();
```

....................................................................................................

```cpp
class sampleclass
{
sampleclass* ptr; // this is fine
};
```

*However, while a class can contain a pointer to an object of its own type, it cannot contain an
object of its own type:*

```cpp
class sampleclass
{
sampleclass obj; // can’t do this
};
```

*This is true of structures as well as classes*

--------------------------------------------------------------------------------

 ##### POINTERS TO POINTERS

```cpp
int* arrptr[100]; // array of pointers
// but array is itself a pointer

// call
exec(arrptr);


void exec(int** the_arr) {
    for (int i = 0; i < 100; ++i)
    {
        cout << **(the_arr+i) << endl;
    }

}
```

```cpp
// quick and brief demonstration

#include <iostream>
#include <string>
using namespace std;


void exec(int** the_arr);

int main() {

    int* arrptr[3];
    int a=9,b=8,c=7;
    (arrptr[0])=&a;
    (arrptr[1])=&b;
    (arrptr[2])=&c;

    exec(arrptr);


}
void exec(int** the_arr) {
    for (int i = 0; i < 3; ++i)
    {
        cout << **(the_arr+i) << endl;
    }

}
```

> *Actually, when we sort person objects, we don’t move the objects themselves; we move the
> pointers to the objects. This eliminates the need to shuffle the objects around in memory,
> which can be very time-consuming if the objects are large.*

- Above nice trick

--------------------------------------------------------------------------------

##### POLYMORPHISM

```cpp
class Base
{
public:
    Base();
    ~Base();
    void draw() {}

};


class B1 : public Base
{
public:
    B1();
    ~B1();
    void draw(/*of_B1*/) {}

};

class B2 : public Base
{
public:
    B1();
    ~B1();
    void draw(/*of_B2*/) {}

};


B1 b1;
B2 b2;

Base* baseptr;
baseptr = &b1;
baseptr->draw(); // calls Base only
baseptr = &b2;
baseptr->draw(); // calls Base only

 // The rule is that pointers to objects of a derived class are typecompatible with pointers to objects of the base class.

// but if we modify draw() in base class,
virtual void Base::show() {
    // base class ka
}
//  then the statements
Base* baseptr;
baseptr = &b1;
baseptr->draw(); // calls b1 ka draw only
baseptr = &b2;
baseptr->draw(); // calls b2 ka draw only

// abstract class : cant instatiate the base class
// declare atleast one virtual function = 0 in the base class

class Bs
{
public:
    virtual void fxn() = 0; // now this becomes an abstract class
    // pure virtual function
};
```

- *Base class destructors should always be virtual. Suppose you use delete with a base class
  pointer to a derived class object to destroy the derived-class object. If the base-class destructor
  is not virtual then delete, like a normal member function, calls the destructor for the base
  class, not the destructor for the derived class. This will cause only the base part of the object to
  be destroyed.*
- the base virtual destructor must be empty.

```cpp
class Parent
{
    protected:
    int basedata;
};
    class Child1 : virtual public Parent // shares copy of Parent
    { };
    class Child2 : virtual public Parent // shares copy of Parent
    { };
    class Grandchild : public Child1, public Child2
    {
        public:
        int getdata()
        { return basedata; } // OK: only one copy of Parent
        // if we dont use virtual then the above line gives error.
        /*The use of the keyword virtual in these two classes causes them to share a single common
        subobject of their base class Parent. Since there is only one copy of basedata, there is no
        ambiguity when it is referred to in Grandchild.*/
    };
```

- We want the function frifunc() to have access to both of these private data members, so we
  make it a friend function. It’s declared with the friend keyword in both classes:

`friend int frifunc(alpha, beta);` // alpha beta are classes

This declaration can be placed anywhere in the class; it doesn’t matter whether it goes in the
public or the private section.

- In class alpha the entire class beta is proclaimed a friend. Now all the member functions of
  beta can access the private data of alpha

```cpp
class alpha
{
public:
    friend class beta;
};
```

- To access showtotal() using only
  the class name, we must declare it to be a static member function. This is what we do in
  STATFUNC, in the declarator
  static void showtotal()
  Now the function can be accessed using only the class name.
  `Class::showtotal();`

- The member functions of every object have access to a sort of magic pointer named this,
  which points to the object itself. Thus any member function can find out the address of the
  object of which it is a member

```cpp
class where
{
    private:
        char charray[10]; //occupies 10 bytes
    public:
        void reveal()
        { cout << “\nMy object’s address is “ << this; }
};
////////////////////////////////////////////////////////////////
int main()
{
    where w1, w2, w3; //make three objects
    w1.reveal(); //see where they are
    w2.reveal();
    w3.reveal();
    cout << endl;
    return 0;
}
// in fxn, this->member_data accesses the data of this object itself.
```

--------------------------------------------------------------------------------

##### TEMPLATES

```cpp
template <class T>
T abs(T n) {
    return (n<0) ? -n : n;
}
 // called a function template
/*a template function is a specific instance of a function template.
Notice that the amount of RAM used by the program is the same whether we use the template
approach or actually write three separate functions.
*/

template <class A, class B>
// now use both in the functions

template <class Type>
class Stack
{
public:
    Stack();
private:
    Type number; // now it can be long int short any
};

// during instantiation
Stack<float> s1;    

// outside declaration new syntax
template<class Type>
Stack<Type>::Stack() //constructor
{
top = -1;
}
```

### exceptions

```cpp
class A
{
public:
    A();
    class error {
        // what it does if thrown
    }
    ~A();
    void func() {
        throw error();
    }
};

// in main

try {
    // do the thing which you want
    A a;
    a.func();
    // func() throws error
}
catch(A::error) {
    // do this if error occured
}
```

---
### standard-template-library

- The term data structures refers to the ways data is stored in memory, and algorithms refers to how it is manipulated.

> STL Tutorial and Reference Guide, Second Edition by David R. Musser, Gillmer J. Derge, 
> and Atul Saini


---
#### container

- A container is a way that stored data is organized in memory
- A container is a way to store data, whether the data consists of built-in types such as int and
  float, or of class objects. The STL makes seven basic kinds of containers available, as well as
  three more that are derived from the basic kinds.
- Containers in the STL fall into two main categories: sequence and associative. The sequence
  containers are vector, list, and deque. The associative containers are set, multiset, map, and
  multimap. In addition, several specialized containers are derived from the sequence containers.
  These are stack, queue, and priority queue.

| Container          | Characteristic                                 | Advantages and Disadvantages                                                                                                                             |
| ------------------ | ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ordinary C++ array | Fixed size                                     | Quick random access (by index number),Slow to insert or erase in the middle, Size cannot be changed at runtime                                           |
| vector             | Reloc ating,                                   | Quick random access (by  ,number) expandable array,Slow to insert or erase in the middle, Quick to insert or erase at end                                |
| list               | Doubly linked list                             | Quick to insert or delete at any location, Quick access to both ends Slow random access                                                                  |
| deque              | Like vector, but can be accessed at either end | Quick random access (using index number), Slow to insert or erase in the middle, Quick insert or erase (push and pop) at either the beginning or the end |

```cpp
vector<int> v;
list<char> lschar;
// memory allocation dynamic
```

| Container | Characteristics                                                             |
| --------- | --------------------------------------------------------------------------- |
| set       | Stores only the key objects, Only one key of each value allowed             |
| multiset  | Stores only the key objects, Multiple key values allowed                    |
| map       | Associates key object with value object, Only one key of each value allowed |
| multimap  | Associates key object with value object, Multiple key values allowed        |

---

#### vector

` vector<type> name;`

can by dynamically allocated, no need to put no_of_elem.

```cpp
vector<int> v(no_of_elements);
vector<int> v = {1,2,3,4,.....};

v.size(); // length of the vector

v.push_back(8); // puts element 8 back of the array

v.max_size(); // returns max size the vector can hold in this system

double arr[] = { 1.1, 2.2, 3.3, 4.4 };
vector<double> v1(arr, arr+4); 	//initialize vector to array
vector<double> v2(4); 			//empty vector of size 4 (garbage hai yaha)

v1.swap(v2);
// swaps contents of v1 and v2

v2.back(); // returns last element
v2.pop_back(); // removes last element

v.insert(iter_location, element);
v.erase(iter_location, element);

// not so efficient with vector because you have to shift all the elements



























```




---

##### data-structure-functions

| Name       | Purpose                                                                                              |
| ---------- | ---------------------------------------------------------------------------------------------------- |
| size()     | Returns the number of items in the container                                                         |
| empty()    | Returns true if container is empty                                                                   |
| max_size() | Returns size of the largest possible container                                                       |
| begin()    | Returns an iterator to the start of the container, for iterating forwards through the container      |
| end()      | Returns an iterator to the past-the-end location in the container, used to end forward iteration     |
| rbegin()   | Returns a reverse iterator to the end of the container, for iterating backward through the container |
| rend()     | Returns a reverse iterator to the beginning of the container; used to end backward iteration         |

| Container      | Implementation                                | Characteristics                                                                        |
| -------------- | --------------------------------------------- | -------------------------------------------------------------------------------------- |
| stack          | Can be implemented  as vector, list, or deque | Insert (push) and remove (pop) at one end only                                         |
| queue          | Can be implemented as list or deque           | Insert (push) at one end,  remove (pop) at other                                       |
| priority queue | Can be implemented as vector or deque         | Insert (push) in random order  at one end, remove (pop) in sorted order from other end |


---
#### algorithms

- Algorithms in the STL are procedures that are applied to containers to process their data in various ways. For example, there are algorithms to sort, copy, search, and merge data. Algorithms
  are represented by template functions. These functions are not member functions of the container classes. Rather, they are standalone functions. Indeed, one of the striking characteristics
  of the STL is that its algorithms are so general. You can use them not only on STL containers,
  but on ordinary C++ arrays and on containers you create yourself

| algo       | purpose                                                                                                      |
| ---------- | ------------------------------------------------------------------------------------------------------------ |
| find       | Returns first element equivalent to a specified value                                                        |
| count      | Counts the number of elements that have a specified value                                                    |
| equal      | Compares the contents of two containers and returns true if all corresponding elements are equal             |
| search     | Looks for a sequence of values in one container that corresponds with the same sequence in another container |
| copy       | Copies a sequence of values from one container to another (or to a different location in the same container) |
| swap       | Exchanges a value in one location with a value in another                                                    |
| iter_swap  | Exchanges a sequence of values in one location with a sequence of values in another location                 |
| fill       | Copies a value into a sequence of locations                                                                  |
| sort       | Sorts the values in a container according to a specified ordering                                            |
| merge      | Combines two sorted ranges of elements to make a larger sorted range                                         |
| accumulate | Returns the sum of the elements in a given range                                                             |
| for_each   | Executes a specified function for each element in the container                                              |


---
#### iterator

- Iterators are a generalization of the concept of pointers: they point to elements in a container.
  You can increment an iterator, as you can a pointer, so it points in turn to each element in a
  container. Iterators are a key part of the STL because they connect algorithms with containers.

- You can increment iterators with the
  ++ operator so they point to the next element, and dereference them with the * operator to
  obtain the value of the element they point to. In the STL an iterator is represented by an object
  of an iterator class.

| Iterator Type | Read/Write     | Be Saved | Direction        | Access |
| ------------- | -------------- | -------- | ---------------- | ------ |
| Random access | Read and write | Yes      | Forward and back | Random |
| Bidirectional | Read and write | Yes      | Forward and back | Linear |
| Forward       | Read and write | Yes      | Forward only     | Linear |
| Output        | Write only     | No       | Forward only     | Linear |
| Input         | Read only      | No       | Forward only     | Linear |

---

#### function-object

- a function object can be taken as an argument, in some of the algorithms:-

```cpp

sort(data,  data+6, greater<double>()); // this greater function reverses the sorting order

// another example

bool isDon(string name); // checks if name == "don" then returns true

find_if(name, name+6, isDon);
// 3rd parameter is the address of the function object
// find_if applies isDon to every element on the list

// similarly 
for_each(start_iter, end_iter, fxn_to_be_applied_on_each_element);
