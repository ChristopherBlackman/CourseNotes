#Data Structures und Arrays

#two types of arrays
* local arrays
* dynamic arrays

##local array in c++

```c++
int array[4];
int array[4] = {1,2,3,4};
```
###Note
* when you create an array in c++ it is local to that function or that class or that ...
* intilization in c++ there are no initial values (no default)

###There are partial initilizations in c++
```c++
int array[4] = {1}; // will only fill the frist array block into memory
int array[] = {1,2,3} // c++ will define based on items defined thus the size will be three
```

* in c++ arrays if you go out of bounds then c++ will conitue to acces that memory out of bounds and potentialy change it

* when you create local arrays the "sizeof" operator will tell you how many bytes the array occupys

so if you delare 
```c++
double numbers[5];

//then

(sizeof numbers)/(sizeof double)
```
###in c++ there is no way to measure array length and it is neccesary to either
* store the Length in a seprate variable
* use one array Element to store a Stop Symbol eg. ( '\0' ) ASCII 0

###structures
* array allows us to store things that are the same type
* a struct allows us to store several things that are not necessarily of the same type

#### struct eg
```c++
stuct <name>{
	<member1type> < member1name>
	<member2type> < member2name>
};     //needs a semi colon 

stuct <name>{
	<member1type> < member1name>
	<member2type> < member2name>
}<name1>,<name2>;     //variables that of type struct 


//ex
struct House{
	std::string address;
	int sqFoot;
	std::string  office;
};

House a ;
a.address;
```
###memory model
* heap stores dynamic memory 
* stack stores functions

####binary conversion
	decimal{0,1,2,3,4,5,6,7,8,9}
	2017
	7*1 + 1 *10 + 0 * 100 + 2 * 1000 == 2017

#####binary{0,1}binary digit is a bit
	1011
	1*1 + 1*2 + 0 * 4 + 1 * 8 = 11

####gexadeciaml conversion (used for viewing memory)
	hexadeciamal {0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F}
	0xb2c
	11 * 16 * 16 + 2 * 16 + 12 = 2860

* type casting c++
	(int)3.2

###Little Endian
* stores the least significant byte frist
	33 = 21	0 // looks like this on the computer thou (hexadecimal)
	read like this this in hex 00 21

###note
* if you check array size outside of function that was deeclared then you lose the size of the array
* you can only check array size inside the local function where it was defined

###pass by refrence
* passes the memory location of where the data is siting
* by adding const, it maakes the refence Read Only
```c++
//void print ( const int &y)...
\\example that shows that a pass by refrence
void print ( int &y ){
	cout << &y << endl;
}
int main (){
	int x =3;
	cout << &x << endl; // prints out memory location of x
	return 0;
}
```


###pass by value 
* you get a local copy in the stack of the item you passed

```c++
\\example that shows that the program makes a copy when you call a local function
void print ( int y ){
	cout << &y << endl;
}
int main (){
	int x =0;
	cout << &x << endl; // prints out memory location of x
	return 0;
}
```
