
#Chapter 4 Dynamic Memory

##What memory allocation looks like
`|code|data|heap|=>free memory<=|stack|`

###Code Segment
* where the code is stored

###Data Segment
* contains static and global varibles
* can be split into inizilised and uninitilized regions

###Heap
* Where all dynamically allocated memory is stored

###Free memory
* this is memory for the program to use, memory shrinks and grow as the program 
executes demending on how much memory the heap and stack use

###Stack (function stack)
* Data needed for handling function calls is also stored here (ex. return address)

###Varible Decleration
* creates an identifiers(or a lable) for a location in memory

###address-of operator(&)
* will return the memory location of it's operand
```c++
int x = 4; cout << &x;
//this will print out memory location in hex
```
###pointer
* is a varible that stores a memory location
* since it is a varible it also has a memory location
eg. <type>*
	int x = 4; int* x_ptr = &x;

###Refrence is (int &hello)
* you can change the data at memory location

###derefrence operator (*)
* lets us get and set data
```c++ 
int x =4;
int* x_ptr = &x;
cout<< *x;
//goes to what it is actually pointing to
```
##Dynamic Memory Allcoation Memory

######staticly allocated integer (static array x[]) - automatic varible

```c++
int x[3];
for(int = 0; i<3; ++i){
	cin >> x[i];
}
```
######dynamically allocated array
```c++
int* x;
int size;
cin >>size;

//allocate memory on the heap
x = new int[size];

for(int i = 0; i < size; i++){
	cin >> x[i];
}
//the size of x after calling new, it can never be changed ( size is fixed)
//do not know the size at compile time
```
###pointer arithmitic
* the compilers auto-matic multiplication for going over data

	when you call "new T[num]" the memory manager looks in the heap for chunk of contiguous memory that can store num objects
	an array can be treated as a pointer, that is why when passed through a function it loses it's size
	eg. an example of what the function is actually doing
	void foo(int x[]) = > void foo(int* x)

###dynamic memory allocation ( using the 'new' keyword)
* we can allocate mamory for a single thing or for an array of things, things might be objects

#STACK
* when you add you push
* when you remove something you pop

* when function is called a stack frame is pushed onto the stack

* memory is allocated when the stack frame is pushed on the stack
* memory is deallocate d when it is no longer needed ( this must be done manually in c++, this is dangeourse as there can be memory leaks)
..* it is you responsiblity to deallocate memory
#####examples
```c++
//this does not change the data in memory but, just lets the heap reallocate the memory, STOP THE LEAKS
delete x;
delete[] array;
```
######more examples
```c++
	int* x - new int;	//allocate memory for a single int
	int* y = x;			//y points to the same place a x
	delete y;			//valid deallocation
	delete x;			//valid deallocation - will try to delete but will end up doing nothing
						//one can see that these both do the same thing

	x = nullptr; 		//often see null or 0 // to get rid of hazzard of overwriting data
	y = nullptr;
```

#Arrays and pointers

```c++
int nums[] = {1,2,3,4,5];
int* numsPtr = nums;
int* numsPtr2 = &(nums[0]);

nums[3] == *(numsPtr + 3)
```

######simulating miulit-Dimensinal Arrays

```c++
int grid1[3][3]; // this is a whole chunk of memory
int** grid3 = new int*[3]; // 2-d array is a pointer to a pointer // while the pointer is pointers to the second array
for(int i = 0; i <3; i++){
	grid3[i] = new int[3];
}
```
##Stack verses Heap
* Allocating and deallocating memory is ver fast on the stack
* Allocating memoty on the heap may be slower and we rarelt have guarantees
* Deallocating memory on the head is fast

##functions with pointer parameters
* we have seen pass-by-refrence
.. * `void foo(int& passByVale){passByValue = 0;}// example of a pass by value function`
*we can also do this with pointers
.. * `void foo(int* passByRefrence){*passByRefrence = 0;}//example of a pass by refrence function with pointers`
* both of these function do essentialy the same thing

* operator presedence '*'(derefrence)  is second to ' . '(go into)
```c++
	(*p).h == p->h
```

#C++ Strings with C Style
```c++
//this is a string in c
char s[] = ['h','i','\0'];
//append amd contatination, two meetofs both using allocated memory
void append(char* &word, char c)

char* concatenate(char* s1, char* s2)
```
