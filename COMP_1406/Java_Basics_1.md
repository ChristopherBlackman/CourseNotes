
#java basics

* classes have to have capitals
* class names corespod to the name of the file

* static methods -> class methods
* non-static method -> instance

```Java
//this is what a program looks like in java
public class HelloWorld{
	public static void main(String[] args){
	}
}
```
data types
```Java
byte  = 0b;
float = 0.0f

char	//2 bytes

byte 	//8 byte
short 	//16 byte
int 	//32 byte
long 	//64 byte

float  	//32 byte
double 	//64 byte

boolean	//1 byte
```
<br>
primitive data types are stored in memory where they are declared
<br>
every other object is stored in the heap
<br>
each primitive has a class with (state and behaviour)
<br>
ex. of the integer class 
```Java
Integer x = new Integer(12);
x.intValue();		//12
x.doubleValue();	//12.0
x.toString();		//"12"
//conversion methods

//static methods
Integer.MAX_VALUE		//(2^31) -1
Integer.BYTES;			//4
Integer.compare(12,17);	//some negative number ->{<0 -> a<b, =0 -> a=b,>0 -> a>b} 
Integer.parseInt("13");	//13

ex array list
ArrayList<int>;
ArrayList<dataType>;

for each loop
for(String s : ArrayIfStrings){
	System.out.println(s);
}
```

imutable data structures : data structures that cannot be changed
<br>
mutable data stuctures   : data structures that can be changed

###method signiture 
*  consists of the method name and the list of input argument types ( order matters as well)
* functiuons are uniquly defined by their signitures

###Function/method overloading
* multiple functions with the same name but diffrent function sigintures

###Constructor
* like a method but not the same, a constructor creates and inizilises an object,
* a constructor has the same name as the class, a constuctor has no return type ( not even void)
<br>
"this" in java refrences the object ( all classes extend object in java)

###constructors
* constructor chaining by using "this()", can only be used once and must be the very frit line of code
* java will create a default example <-> there are no constructors defined

####note
* in c++ this is a pointer so when you are setting an x value you would have to do "this->x = ..."
* constuctor chaining in  c++ from a construtor Foo():Foo(varibles){}
* in c++ no constuctor means that there is no innizilization


##How to implement you won stack
**stack has three operations**
* top  - access data on the top
* pop  - remove top element
* push - add an element to the top

####note
* a stack can be implemented by using a link list
* a link list is a struct with a pointer inside pointing to another struct

##Memory model is the same as c++ memory model
*in java "==" is comparing the "memory address" or compares the refrence
*never use "==" unless using primitive data types of looking for null
<br>
to get by this we create a method in the class that compares the primitive data types
```Java
//ex methods for string
.equals() // returns a boolean
.compareTo() // returns a int
```
literal of a type
* a value that you assign at the present and not later

####note
* java stores a small amount of intergers into the data segment for preformance, other than that it creates an object on the heap

###shallow copy
* when java just copys the pointers to the data

###deep copy
* when you have to re-initilize all the structures in the your object down to the primitive types

Limit of Array Size in java is  2^32

###Testing
* Bounadery Cases
* Near-Bounadary Cases(off-by-one errors)
* typical cases
* extreme cases

#Linked list
* is a data structure for a sequential collection of data 
* to know when a linked list stops we use a "null" refrence pointer
* head is the frist node in the linked list
* tail is the last node in the linked list
```Java
public class Node {
	Integer data;
	Node next;
}
```
##Linked lists
* Random Access data Structure (by position in the array) (finding by position is fast (constant time))
* find by value (worst case is n)
* if sorted then by binary search it is logn
* adding in the front is less work than adding to the end
##Arrays
* sequential data structure (finding position i costs time proportinal to i)
* worst case (worts case n)
* adding things to the back is faster than adding things to the front

##which is better
* implementation (easy)
* memory space
* speed


#Classes and it's attributes
Class Atributes
```Java
static int count;
static final string s;
```
instace attributes
```java
String name;
int a;
```

constructors
```java
public MyClass(){..}
```
instatence methods
```java
String getName(){}
```
class Methods
```java
static void foo(int n){}
```
Class Attributes and Class Methods are Static
* these belong to the class itself. 
* they do not belong to a piticular object

Instace attributes and instace methods are non-static
* they belong to individual objects.
* each object gets a copy of each
* need an object to acces these

#Three Pinciples of OOP

##Encapsulation
* Objects combine both data and operations on the data(they have both state and behaviour)
* allows uss to modul very real-world problems nicely
* helped us modulize our code
<br>
##Inheritance
* classes can inherit attributes and operations from other classes
* promotes code sharing and re-usability
* yeilds heirarchal code organization
<br>
##Polymorphisim
* objects act like other objects
* dynamic bininding allows objects to determin which methods to use at runtime
* simplifies code understanding
* standerdizes method naming
<br>
##Unified Modeling Language(UML)
* way to make code better displayed and layed out

#Inheritance

we have seen the "has-a" relationship between objects in Java
```java
//A Student Object has a String
Public class Student{
	String name;
}
```

An important realtionship from isheritance is the "is-a" relationship
<br>
ex
>A Dog is a mammal <br>
>A mammal is an animal <br>
>Abird is an animal (but not a mammal)

* in java extends inherits from other classes (all the way to object)

* java automatically extends Object for you classes, this is why we see the toString Methods, .Equals methods ...

```java
Public class CSSstudent{} === Public class CSSstudent extends Object {}
```

when we inherant from a class
* we ge all the public (and protected ) methods from the class (this can be done by doing protected[private to things that do not inherite]instead of private)
* we get all public (and protected )methods from the parent class
* we get none of the constructors ( we will have to write our own contructors) (instead java uses "super()" to call the constructor above the object, you can add multiple parameters)
* be careful  ^ as this is dangerous
* it is possible to overload methods to change the behavior of child classes
* Method Hiding is when you refefine a class method of a parent class
* final , const after constructor, only make the refrence constant (no such thing as a const array)
* final methods cannot be overridden
* final classes cannot be extened ( no sub classes from this class )
* concrete classes can be instatiated
* abstract classes cannot be instatiated
* protected attribute  allows for child classes to access
* a abstract method makes the child have to either define that method, or become another abstract class

abstract classes
	* allow us to enforce consistencty among all sub classes
abstract methods
	* allow us to enforce that there is a method of this name amoung a sub class

#####note
* abstract class need not abstract methods, an abstract method need to have an abstract class, define what something is
<br>

######class name tyically nouns
* concrete class must have everthing defined

* interface: defines what an object can do. typically adjectives
* attribues insde of an interface are public static final, also just defining constants
* methods without a body are public abstract
* "default" methods
* multiple interfaces just use a comma
* how to add an interface, use key word "implements"

* useful interface is comparable with generics <T>

#Ploymorphism

##ADT - Abstract Data Types

####mathematical model 
* has data
* opera	-remove/pop() //remove from the top
* peek()/top() //next value

####double endded Queue
* addfrist(x),removeFrist() // add or remove from the enque
* addLast(x),removeLast()   // add or remove from the dequeue

####List interface
* represents a sequence indexed by 0,1,2... n-1	
* size
* get(i)
* set(i)
* set(i,a)
* add(i,a)/insert(1,a)	
* remove(i)

####Unordered Set Interface
* represetns an unordered collection of distict values
* size()
* add(x)
* remove(x)
* find(x)

####Map/Dictionary Interface
* in a map or dictionary data structure the data is a key/value pair ex (k,v)	
* keys are distinct in the dictionary
* there are no restrictions on the values

####Sorted set Interface
* represents a sorted colletion of distict elements
* the data has some total order

```
                |< 0 if x < y
compare(x,y)----|> 0 if x > y
                |= 0 if x = y
```
* size()
* add(x)
* remove(x)
* find(x) does a successor search or a predeccesor search
	
###data structure
* is a systematic approach to storing and accessing sata so that it can be used efficintly for a  specific purpose
* is the implemetation of an ADT

###ADT 
* is data and operatioons on that sata  that are presisly indemended of any implementaion
* adt is a mathematical construct. we simulate them as APIs or interface

###Generics
* allow types and parameyers in the definitions classes, interfacesm or methods
* advatages (eleiminates the need for excessive type casting, allows comiler to do stronger checking, dont have to rewrite the code)
* can be used to paramatize types

Ex

```java
	public class Box <T>{
		T thing;
	}
	
	main {
		Box<String> stringBox = new Box<String>();
		stringBox.thing.toUppercase();
		Box<Integer> ....;
	}
	//generic array creation is not permmited in java
```

#Comparisions in data structures

######array
* stack -> add/remove from the end of the array
* we'll leave some room in the array
* resizing is only negative

#####Linked-list
* stack -> add/remove front
* node

###fifo queue for an array (circular array)

```

========================
|0|1|2|3|4|5|6|7|8|9|10|
========================

========================
|10|0|1|2|3|4|5|6|7|8|9|
========================
  B   F

F = front 
B = back 
L = length
```
>to find the back position you can do B%L	<br>
>so that we can find the back if it 		<br>
>happens to go past the end of the array	<Br>

###fifo queue fora linked list
* easy to add()/remove() from the front 
* easy to remove() from the back

>for fifo just add to the back and remove from the front

###Deque for a linked list (a double linked list)
* easy to remove from the front and the back of the list

###Deque for an array

```
=======================
|1|2|3|0|0|0|0|0|0|0|0|
=======================
warning 
f = 0
b = 2

mod != % in most programming langagues

-1%L = -1 // for any numbe that is < 0, for any number >= 0 the langauge operator will work

array[(f-1)mod length] will work in mathematics

array[(f-1)% length] will not work for computers

array[(f-1+length)%length] will work work for computers

```

###unordered collection / set array
use a an array to store elements
* find   O(n)
* add    O(n) //find element
* remove O(n) //find element

###unordered collection / set hash table
hash table  (hashing with chaining)
```
===============
|0|1|2|3|4|5|6|
===============
```
######this hash table is made up of linked list inside this table

>hash function
>h(x) = x mod 7

worst  case expected case
* find   O(n)	     O(1)
* add    O(n)	     O(1)
* remove O(n)	     O(1)

```
n = # of elements
d = capacity of the array

n/d <= 1   -> average size of each list
```
###Bad Operations
Array		
* closing gaps / creating gaps is O(n)
Linked List
* seaching is O(n)

game with lists of componets
```
players	List<players>	|
bullets	List<Bullets>	|--- List<things>
lasers	List<lazers>	|
```

