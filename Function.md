#functonAndStorageClasses
Todays we were gone discuss about Function in C -Language, Before we Understand How ,When, Where we uses Function, <font color="#fac08f">think in mind have you use any function till Now in Your Code ?</font>
- Actually we already used lot of function like `Printf()` ,`Scanf()` etc. 
- <font color="#ffff00">Now Question is did we wrote the code of these function or are we using them only.</font>
- Actually All those function `Printf()` ,`Scanf() etc` are comes in the categories of <font color="#9bbb59">predefined function</font> means, compiler designer define or write code for these function, and we are just using those function Only .
- By this way one thing we come to know `Code Resuability` is the biggest <font color="#00b0f0">Advantage of functions.</font>
-  <font color="#d99694">Function is self Contained Block of code that accomplish a task !</font>

##### Now its Time to understand How We make our own Function, often we call it as <font color="#76923c">User Define Function.</font>
Before we write own function, we have to know some key points about C - Language. 
- In C-Language Before we go using anything, we were have to give information about that to the Compiler .
- Compilation parse from top to Bottom .
- `#include<stdio.h>` file contains forward declaration of Predefine function `Printf()`,`Scanf(),Pow()` etc 

```C
#include<stdio.h>
//forward-Decleration-for-compiler to avoid compilation error
int mul(int,int); //-->function-Prototype

void main(){
    int a = 10,b = 20, ans;
    ans = mul(a,b);
    printf("%d",ans);
}

int mul(int x, int y){
    int result;
    result = x*y;
    return result;
}
```

- By default return type of function is `int`
```C
#incude<stdio.h>
//Inplicit Deleration
mul(int x, int y){ //compiler assume retyen type of mul() is int
    int result;
    result = x*y;
    return result;
}

void main(){
    int a = 10,b = 20, ans;
    ans = mul(a,b);
    printf("%d",ans);
}
```

```C
#incude<stdio.h>
void main(){
    int a = 10,b = 20, ans;
    ans = mul(a,b); //compiler assume retyen type of mul() is int
    printf("%d",ans);
}

double mul(int x, int y){ //but here actual function returning in double 
    double result;
    result = x*y;
    return result;
}
// So this function leads to Error
```

🤔 More Precisely we can say that Header file contains forward declaration of function like `printf()`, `Scanf()`, `pow()` etc !

```C
#include<Stdio.h> //just Forward decleration of printf(); not body
void main(){
printf("Hello"); //call
}
```

think ? where is the body of `printf()`
❌Actual code of `prinf()`  is Basically not Accessible for the programmer.
✅All predefined function are store in Archive file in the form of pre-compiled code

![[ProgramExecution.drawio.svg]]

- Is this program Compile without `printf()` definition ! YES
- Is this  program Run without `printf()` definition ! NO
- <font color="#f79646">Linker is a System Software</font> which Generates Runnable file then Loader will take the work, <font color="#f79646">Linker</font> will also find `main()` function from code that why we can say execution start from main function
- <font color="#92d050">Loader is a System Software</font> which Loads the ready to run programs to Memory
- After Complete execution of any function it Deleted own activation record from memory
- If a function return Some value it is not necessary to use. we can use or not its Up to US

```c
#include<stdio.h>
int mul(int x, int y){
return x*y
}
```

Above program gets <font color="#4bacc6">compile</font> without any problem.
but in execution phase <font color="#f79646">Linker</font> throws<font color="#ff0000"> Error main() not found</font>

<font color="#f79646">Swap program but does`t work like as we are expecting !</font>
```C
#include<stdio.h>
void swap(int int);
void main(){
int a = 10, b = 20;
printf("Before Swap");
printf("a = %d , b = %d",a,b);
swap(a,b);
printf("a = %d , b = %d",a,b);
}

void swap (int x, int y){
int temp;
temp = x;
x = y;
y = temp;
}
```

<font color="#f79646">To make this working correctly we have to use pointers and actual reference of variables-</font>
```C
#include<stdio.h>
void swap(int int);
void main(){
int a = 10, b = 20;
printf("Before Swap");
printf("a = %d , b = %d",a,b);
swap(&a,&b);
printf("a = %d , b = %d",a,b);
}

void swap (int* x, int* y){
int temp;
temp = x;
x = y;
y = temp;
}
```

Now, we have to study about [[Storage Class]] which taught 4 important thing about Variables in C - Language. 
