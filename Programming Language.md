<font color="#2DC26B">Why we should Learn Programming Language ?</font>
- To increases our Logical thinking.
- Set of instructions commands written in some Program language, those are given to machine So that machine come to know what it need do, that why we need PL to write those instruction.

<font color="#2DC26B">Why Machine Understand only Zero and Once ?</font>
- Zeros and Once basically set a range through which Machine can understand Two states high(1) and low(0) . This is achieved by magnetic Flux

<font color="#2DC26B">Then Why we not write programs in Zeros and Once ?</font>
- We knows that Humans are not comfortable in Numbers, Its Really hard to directly write program in Zeros and Once

<font color="#2DC26B"> Based on closeness to hardware, programming languages are typically classified--</font>
- low-level languages (very close to hardware, like machine code and assembly language)
- high-level languages (further from hardware, with more abstraction, like Python, Java, and C++)

<span style="background:#fff88f">Low-level languages</span>
-  **Machine code:** The most basic level, directly representing the binary instructions the CPU understands. 
- **Assembly language:** A slightly more human-readable version of machine code, using mnemonics to represent instructions, but still very close to the hardware architecture.

<span style="background:#fff88f">High-level languages:</span>
- High-level languages refers to computer programming Language , it uses symbolic operators which makes its as human understandable language. means its very close to human language so for humans it is Easier to learn and write code with it. But  it May be less efficient than low-level languages due to compiler overhead because of More Abstraction
---
Whatever the instruction we write in high level language(English type) , those instruction need to be converted in Machine level Code(Binary) So that machine can understand, which is done by Translator. and then Based on that machine will generates OUTPUT

![[Translator Program.png]]

**Based on its Behaviour of conversion Translator can be classify in to 3 Categories**
**High-Level to Machine Code**
- **Compiler** (whole program)
- **Interpreter** (line-by-line)
**Assembly to Machine Code**
 - **Assembler**

| Feature             | **Compiler**                                                      | **Interpreter**                                                     | **Assembler**                                          |
| ------------------- | ----------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------ |
| **Function**        | Converts the entire high-level program into machine code at once. | Converts and executes code line-by-line.                            | Converts assembly language into machine code.          |
| **Speed**           | Faster because it compiles the whole program before execution.    | Slower because it translates and executes code simultaneously.      | Faster, as assembly language is close to machine code. |
| **Execution**       | Generates an independent executable file.                         | Does not create a separate executable file; runs the code directly. | Produces object code (machine code) for execution.     |
| **Error Detection** | Detects all errors after compilation; difficult to debug.         | Stops at the first error, making debugging easier.                  | Errors occur mostly in syntax and instruction format.  |
| **Examples**        | C, C++, Java (JVM acts as an interpreter)                         | Python, JavaScript, Ruby                                            | NASM, MASM, TASM (Assembly language processors)        |

---
Important points about Program Languages !

- Every Program Language must have some feature to take / read / fetch /input  Coming from the Keyboard.
- Every Programming Language must have some feature to give output / print from program to monitor 

##### <font color="#ffc000">Is it Necessary to Learn Programming Language to interact with Computer ?</font>
Basically in this world there are two types of peoples : -

- <font color="#e36c09">Programmer - </font>As programmer for making different kind of software we need to learn Program language 
- <font color="#e36c09">User - </font>but user just interact with Computer through interface that is provided by any of the software made by programmer , user does`t` need to care about what happening behind the interface, So all unnecessary Implementation abstracted from normal user. Programmer just provide interface out of box

---

**Platform Dependency !**

If you made a C-Program over Windows OS Compiler will generate  `.exe` which is executable over windows only not on any other OS.

If you made a C-Program over LINUS OS , Compiler over Linus will generate `.out` which is executable over LINUX only not on any other OS.

---
For Writing C-Program in our System we need to install Some C related Software like IDE and GCC Software .
After installing GCC Software By default we get Two things : -
- <font color="#e36c09">Compiler</font> : Compiler is a software which is responsible for generating `.exe` file after checking Syntactic correctness, How it does ? we will study about Compiler later point of view
- <font color="#e36c09">Library</font> : Library Contains Collection of Header file, these header file Contains Predefined functions that programmers can use after including the related header file at top of the C program

<font color="#d7e3bc">Lets Understand it By an Example-</font>

```c
#include<stdio.h>
void main(){
int a;
scanf("%d", &a); //Predefine-Function 1
printf("%d", a); //Predefine-Function 2
getch();
}
```
 In the above program we uses Predefine-Function which is present in header file `#include<stdio.h>` , we are just using Predefine-Function in our program as interface.

---

#### <font color="#e36c09">So, Now its Time to Deep-Dive into the Concepts C-language  !</font>
- [[Variables & Data-Types]] 
#### <font color="#de7802">As like other programming languages C also support some kind of operators, these are nothing but some special symbols which perform specific task</font> ?
- Before jump on the Operators you have to know little about [[Number-System]]
- So let`s` we study about [[Operators]]
#### <font color="#e36c09">What actually the</font> [[printf()]] <font color="#e36c09"> function returns </font> ?

#### [[Sizeof() Operator]]


#DataType_Operators