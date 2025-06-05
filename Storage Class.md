#functonAndStorageClasses
These are the 4 important things that Storage Class taught about variables~
- <font color="#c0504d">Scope</font> : in program scope is a part of code in which the variable is accessible.
     - <font color="#d99694">File Scope</font> of a variable means we can access that variable any where inside the file (Global-Scope).
     - <font color="#d99694">Block-Level-Scope</font> means when that variable is accessible  with in the block only (Local Variable). 
- <font color="#ffc000">life time</font> : its time span/Duration in which it is available(alive or active) in the program.
- <font color="#595959">Default Value</font> : A variable which is not initialized its always holds Default Value( Garbage Value ).
- <font color="#00b0f0">Storage Area </font>: Where a Variable is Storage in memory.

### Our First Storage class is <font color="#e36c09">Auto Storage Class </font>-
whenever the variables declared inside a function then that variable is called <font color="#f79646">auto variable</font>
```C
void main(){
auto int a = 10; //(auto varibale)//We can write like this (auto int a = 10) also 
int a = 10; //auto is optional.
}
```

why do we call these as <font color="#f79646">auto variables ?</font>
- Actually <font color="#f79646">auto variables</font> created automatically when we enter the block in which they are declared and destructed automatically when you exit the block.
- Scope : block in which they are declared.
- lifetime : block in which they are declared.
- default value : Garbage.
- Store : inside Stack of the Memory.

Important Points About <font color="#f79646">auto</font> !
- for <font color="#f79646">auto variables</font> <font color="#c0504d">Scope</font> and <font color="#ffc000">life time</font> is Same which is Block
- main Scope variables are accessible inside sub scope. 
- sub scope variables are not accessible to the main Scope variable

```C
void main(){
int a = 0;
++a;
    {
    int a = 10;
    ++a;
    printf("%d",a);
    }
++a;
printf("%d",a);
}
```

This Memory diagram shows everything about which variable get stored where. 
![[Memory Layout Diagram.png]]


### Our Third Storage Class is <font color="#e36c09">Register</font> -

- The `register` storage class in C is used to define local variables that should be stored in the CPU **registers** instead of RAM. 
- Register variables have the same properties as `auto` variables (i.e., they are local to the function and have automatic storage duration), but the key difference is that they are stored in CPU registers, which are tiny, high-speed storage locations used to hold data and instructions during program execution. This makes accessing them faster than regular memory .
- These variable have no address you can`t` use `&` 

```C
register int a; 
```

- The `register` keyword tells the **compiler** to try to store the variable in a CPU register for faster access. If a register is available, the compiler may place it there. If not, the variable is stored like a normal `auto` variable — usually on the **stack**.

### Our Fourth Storage is <font color="#e36c09">Static Variable</font> -

- lifetime of these variables Through out the program  life time .
- Its scope is Block level
- Default value is Zero.
- Stored in Static Area(Data_Segment) of Memory and executes in compile time.
- Its Value can persist between different different function call.
- No Redeclearation / initialization
- They are created only once in a program

### Our Fifth Storage is <font color="#e36c09">Global Variable</font>
These are the variables which are present outside all the function.
- Lifetime is entire duration of program.
- its scope is external
- Default value is Zero.
- Stored in Static Area(Data_Segment) of Memory

```JavaScript
void f1(){ extern int x; // we have to provide Forward decleration to the compiler so that compiler not get confussed. 
    ++x;
    printf("%d",x);
}
int x;
void f2(){
    ++x;
    printf("%d",x);
}
void main(){
    f1();
    f2();
    ++x;
    printf("%d",x);
}
```

🤔 With this keyword `extern int x` we are just providing information to the compiler, that we will just get this variable bellow, this statement actually does`t` allocate any type of memory.

### More on Static and Global Variables.
- We can use Static variable as much as possible with in a file by declaring it as a global, but we can`t` access it from another file even if we use `extern` keyword
- Global variable `( int x )`  can be used with in or another file we can access it from another file using  `entern` Keyword.

❌ Invalid ( don`t` we put same name of two child in single home )
```C 
void main(){
int i
int i 
}
```

❌ Invalid ( Static variable can be initialized with constant only ! )
```C
void main(){
int j = 10
static int i = j 
}
```

❌ Invalid (  )
```C
void main(){
static int i;
static int i; 
}
```

✅ valid ( Global variable can be re-declared )
```C
static int i; // global varibales were created in the data segment before compile time
static int i;
void main(){
}
```

- Global Variable (<font color="#ff0000">Global variable cannot be Register its scope as much block only</font>)
     - Can be re-declared for multiple times
     - can not redefine
- Local Variable
     - Can not re-declare
     - Can be re-define

<font color="#c0504d">declaration</font> is for Compiler for information purpose only. No memory is allocated
<font color="#9bbb59">definition</font> is leads to memory alocation 

The things related to <font color="#9bbb59">stack</font> were build during <font color="#9bbb59">runtime</font>  (auto variables)
The things related to <font color="#c0504d">Data Segment</font> is build <font color="#c0504d">before runtime</font>, ( Global & Static ) they already dealt before compilation

⚠️Warming
```C
int i;
i = 30;
int main(){
return 0
}
```

❌Error
```C
static int i;
i = 30;
int main(){
return 0
}
```

### [[Recursion]]