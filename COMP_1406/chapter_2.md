#Chapter 2

|how to solve|
|:---|
|understand problem|
|devise plan|
|carry out plan|
|look back|

##Vampire number 
>V = X*Y
>V is 2n digits
>both (X,Y) are n digits long
>every digit in vampire number have to be th digits of both the fangs
>**ex**
>1260 - smallest vampire number
>21 * 60 = 1260

##Control Structures
* branching control structure(if,if else, switch)
* repetition control structures
* nested control structures

##Error found in program
approach
* Tracing source code manualy

##lhun alogrithm
* check sum

##devise a plan
* validating # bool valid(#)
* creating valid #

###vampire Numbers code ???
```
for x from 0 to 9
	if valid(n*10+x)then
		output  n||x (cascade) 
		
		just an idea
		int a = n%100 - n%10 OR int a = (n%100)/10
		
		now we make a function
		//n = number and i being location of number
		int digit(n,i)
		{
			return (n%10^i)/10^(i-1)
		}
		
		//double a number an add into a single digit
		to double a number and get it's sum
		digit((x*2),1) + digit((X*2),2)
```
			
##Data validation
* send data three times, but triple the data size
* lhun alogrithm

