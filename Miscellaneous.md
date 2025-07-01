### Scoping : 
- What is Scoping ? : <font color="#ffc000">Scope Is program scope is a part of code in which the variable is accessible. </font>
- There are 2 types of Scoping we have -
	- <font color="#00b050">Static Scoping ( Lexical Scoping )</font> and even all modern programming languages Support Static Scoping in addition to C Language -
	- <font color="#e36c09">Dynamic Scoping</font> - Dynamic scoping determines the scope of a variable based on the execution path (function call chain) at runtime, meaning it looks for a variable in the calling function's scope if it's not found in the current function's scope.- Languages that support Dynamic Scoping - <font color="#4bacc6">LaTex</font>, <font color="#4bacc6">Bash</font>

Let`s` Understand it by an Example -
Consider the program in a hypothetical language that allows global variable a choice of <font color="#92d050">static</font> & <font color="#fac08f">dynamic Scoping</font>

```C
int i; //global Varibale

program main(){
	i = 10;
	call f();
	}
	
program f(){
	i = 20;
	call g();
	}
	
program g(){
	print i;
	}
	
```

Output Under Static Scoping : 10
Output Under Dynamic Scoping : 20



### Some Important Function and <font color="#92d050">Buffer</font> and <font color="#92d050">Echo</font> :
- `getchar` - `Buffered and Echoed`
- `getch` - `UnBuffered and UnEchoed`
- `getche` - `UnBuffered and Echoed`

Most of the peoples don`t` know what these do ?
-  <font color="#de7802">These 3 functions are related to taking character as input :</font>
	- Is the character `Buffered or Not`  /  `Echo or Not`
- First thing you have to understand What is the Meaning of something `Buffered or Not`   `Echo or Not` 
	- `Buffered` : In programming, a buffer is a region of memory used to temporarily store data while it's being moved from one place to another,
		- <font color="#de7802">Example</font> - whatever the keys you press from the keyword, that Particular characters not directly get stored to the program , other than this, behind the scenes first all character gets stored to buffer first ,and from their it  sends to the program with the hitting enter.
	- `Echo`: Is the character displayed over the screen or not !

### Comma <font color="#92d050">,</font> Operator :
Comma `,` in C language can be act like <font color="#ffc000">SEPERATOR</font> | <font color="#ffc000">OPERATOR</font> | and can do the work of <font color="#ffc000">MERGING</font> 

SEPERATOR
```C
int a=5, b=4, c=6;
```

OPERATOR
```C
int a;
a = (3,4,5);//a =5

var = (Exp1,Exp2,Exp3,Exp4,...ExpN);
//All these expressions are evaluated from left to right and the final value is rightmost which will goes into the varibale
```

✅Comma Operator has Last priority -
```C
int a;
a = 3,4,5; // with whome 3 will go ? either with = or ,
a = 3; // 
```

### Unions in C :
<font color="#ffc000">Structure</font> : In case of structure all the members occupy separate space in memory
```C
struct A{
int i;
char c;
}

struct B{
char c; //1byte
int a; //4bytes
float b;//4bytes
}
```

<font color="#ffc000">Union</font> : In the case of Union all the members share same memory space
```C
union A{
int i; 
char c;
}

void main(){
union A a;
printf("%d",sizeof(a));//4bytes
}
```

Example :
```C
union A{
char c;
int a;
}
void main(){
union A x ={'A'}
printf("%c",x.c);
printf("%d",x.a);
}
```

NOTE :
- Until and unless you not get the Real time application of Union, till now everything is worst
- To get the actual working of union we have to study Data structure topic, called trees. and we will study about it in DS.
- `Type Pruning` is the Real time application of union
### Pre-process in C:
Pre-process is the process that take place just Before the compilation, during which all the required header files and Preprocessor directives are get included to your program.

Instructions that we provide at the top of our program , all that comes under Pre-processing phase

```C
#define Max 20  //these are pre-process directives (Macrros) there work is just copy paste ! or we can say it just replaces.
#include <studio.h>
void main(){
	int i;
	i = Max + 3;
	printf("%d",i); 
	}
```

```C
#define square(x) x*x //5+2 * 5+2
void main(){
int i;
i = square(5+2); 
printf("%d",i) //17
}
```