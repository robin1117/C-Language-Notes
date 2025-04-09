### <font color="#92d050">Integer(int)</font>
Based on the <font color="#fac08f">Size</font> and <font color="#fac08f">Sign</font> further integer is of many types : -
Depending on how our data that we want to store, its large, small or what be its sign negative or positive by considering these factors, only after that we will choose Data-Type.

---
- `short int`- 2Byte =16bits
- `short a` - 2Byte =**16bits**
- `signed short a` -2Byte =16bits
- `signed short int a` -*2Byte =16bits*
---
- `int`- 4Byte = 32bit
- `long int` - 4Bytes = 32bit
- `long long int` - 8bytes = 64bits
---
- `unsigned short int`-
- `unsigned int`
- `unsigned long int`
- `unsinged long long int`
---
<span style="background:#d3f8b6">C-Standard</span> does`t` specify the size of Data-Types , Although In C -Language size of the data types depend on compiler to compiler
#### <font color="#ff0000">Range of Data-Types-</font>

![[Number line.png]]

**In maths Whole numbers starts from 0 - 1 - 2 - 3 ---- ∞**, that`s` is why we considered zero in our counting ~

- ==Unsigned short int 2Bytes =16bit==
- `Range` = `0-------------2`<sup>16</sup> `- 1`
- `Range` = `0-------------65535`
- ==short int 2Bytes = 16bit==
- Range = -2<sup>16-1</sup>---to---2<sup>16-1</sup> -1
- `Range` = `-32768, -32767, -32766_____,-2,-1, 0, 1, 2,______32765 ,32766 ,32767`
- <span style="background:rgba(240, 200, 0, 0.2)"> General Formula for Finding Range </span>
- let us suppose we have data-structure of n-bit : -
- <font color="#00b0f0">With n-bits : :</font> total 2<sup>n</sup> values we can represent  
- <font color="#00b0f0">For unsigned : :</font> Range = 0 --- to --- 2<sup>n</sup> - 1
- <font color="#00b0f0">For signed : :</font> Range = -2<sup>n-1</sup> --- to --- 2<sup>n-1</sup> -1

[[Range as Cyclic Property]] , I mean how we treat <font color="#e5b9b7">Range</font> of any datatype as a <font color="#e5b9b7">Cyclic Property</font> 
### <font color="#92d050">Floating(float)</font>
Similarly Based on Size float also have 3 types : -
- `float`- 4Byte = 32bits
- `double` - 8Byte = 64bits
- `long double` - 12Bytes = 12bits

### <font color="#92d050">Character(char)</font>
This is the bit strange how the character can be negative : -
- `sign char` - 1Bytes = 8bit
- `unsigned char` - 1Bytes = 8bit
- <font color="#00b0f0">Range Unsigned char</font> = 0----to---2<sup>8</sup>-1 === (0-----255)
- <font color="#00b0f0">Range Signed char</font> = -2<sup>8-1</sup>---to---2<sup>8-1</sup>-1 === (-128---to---127)
🫡To Understand More about <font color="#fac08f">Char</font> in C we have to understand about [[ASCII-CS]] -<font color="#00b0f0"> Character System</font>

---
### <font color="#ffff00">Format Specifier </font>
It is a template that defines the format of output or input in a program
- `%d` int
- `%ld` long int
- `%c` char
- `%f` float
- `%u` unsigned

whatever you provide inside double quotes to `printf()` (in C) is printed exactly as it is **unless** you use format specifiers like `%d`, `%s`
```C
#include<stdio.h>
void main(){
printf("My Name Is Robin");
}
```

When we are trying to print a variable with `printf()` then with Format Specifier we are just giving information about what type of data that a particular variable hold that we want to print
```C
#include<stdio.h>
void main(){
int a = 20;
printf("%d",a); //%d specifies datatype of a
}
```

same with `scanf()` we have to tell to it ,what type of data will come from user ,so that it will store at address of variable according to format.
```C
#include<stdio.h>
void main(){
int a;
printf("Enter a Number");
scanf("%d",&a);
printf("The Value is %d",a);
}
```


#DataType_Operators