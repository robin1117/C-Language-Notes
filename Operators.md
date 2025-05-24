Based on the number of Operand Operators can handled, it can be classify in to 3 categories : -
==Every Operator have Some value Output==
 - Unary - works over 1 operand
 - Binary - works over 2 operand
 - Ternary - works over 3 operand

#### <font color="#00b050">Assignment Operator ( = ) : : Binary Operator</font>
- Assignment Operator has Two sides ( L Value = R Value )
- L Value will always be <font color="#92d050">Variable</font> neither <font color="#c00000">constant</font> nor <font color="#c00000">Literal-constant </font>
- R Value can be<font color="#92d050"> Literal-constant </font>, <font color="#92d050">Variable </font>, <font color="#92d050">Expression</font>
#### <font color="#00b050">Arithmetic Operator : :</font> 
- `+` Plus
- `-` Minus
- `*` Multiply
- `/` Divide
- `%` Modules 

==Let discuss little bit about Modules.==
- A % B - It gives Remainder When A / B
- `%` - It takes two operator both must be type of integer. other wise return <font color="#ff0000">Error</font>
- What if operand be `-ve` , Does this make any affect on output remainder  ? 🤔 As per C standard The Result will be <font color="#fac08f">Undefine</font> , But on compiler to compiler <font color="#fac08f">result may be same as the sign of first operand.</font>


```C
a = 3 + 4 * 5;
a = 3 + 20
a = 23
```

```C
int a, b, c;
a = b = c = 10;
-------[       ]
---[      ]
[    ]
printf("%d",a) // a = 10
```

```C
int a, b, c;
a = b = 10 = c;
-------[10 = c]; //This Lead thrown an error !
```

==Result / Behaviour of an operator based on its operand ~== What its mean ?
- int / int = int
- float / int = float
- int / float = float
- float / float = float

```C
int a;
a = 4.0 * 3 % 5 + 6; //by Associativity (*) FIRST SOLVE
a = 12.0 % 5 + 6; //12.0 % 5 thrown error, because modules allow only integers operands
printf("%d",a);
```

#### <font color="#00b050">Relation Operator : : Binary Operators (Relation Operator is a way of Asking Question)</font>
==Result of any Relation operator is Zero or One==
- `<` - less than
- `>` - greater
- `<=` - less than or equal to
- `>=` - greater than equal to
- `==` - equality check
- `!=` - not equal
#### <font color="#00b050">Logical Operator : :</font>
In C language every non-zero value treated as True based on this concept. these logical operator works. its result is always either 0 or 1
- logical and ( `&&` )
- logical OR ( `||` )
- logical not (`!`)

==Lets Solve some Expression and understand== <font color="#e36c09">Precedence</font> and <font color="#e36c09">Associativity</font>.
Associativity Defines what we do if we have operators of same level of priority - 
According to the Precedence : : Priority Order of operators is -
`+` `-` Unary operator have highest Priority
`%` `/` `*`   Associative L --> R
`+` `-`   Associative L --> R
`<` `<=` `>` `>=` Associative L --> R
`==` `!=` Associative L --> R
`&&` Associativity L --> R
`||` Associativity L --> R
`=`  Associative R --> L

```C
int a;
a = 2 < 5 != 2 < 5 && 8 > 10 == 8 > 10;
printf("%d",a); //0
```

```C
int a;
a = 2 != 5 == 3 && 6 > 5 == 10 > 6;
a = 2 != 5 == 3 && 1 == 10 > 6;
a = 2 != 5 == 3 && 1 == 1;
a = 2 != 5 == 3 && 1;
a = 1 == 3 && 1;
a = 0 && 1;
a = 0;
printf("%d",a); // 0

a = ((2 != 5) == 3) && ((6 > 5) == (10 > 6));
------------------- && (not will need to solve)
printf("%d",a); // 0
```

 <font color="#92d050">Priority : : actual meaning</font>
let ` 3 + 4 * 6` suppose.
In the above expression `4` may stuck in confusion because it have two options either it can go with plus(`+`) or with multi(`*`) .
Priority defines with which it should go with  `+`  or  `-`

#### <font color="#00b050">Modify Operator : : Uniary Operator</font> 

| Increament Operator   | Decreament Operator   | WORKING                          |
| --------------------- | --------------------- | -------------------------------- |
| Pre-increament `++a`  | Pre-decreament `--a`  | first increase/decrease then use |
| Post-increament `a++` | Post-decreament `a--` | first use then increase/decrease |
<font color="#c0504d">important !</font>
Between 2 Successive sequence-point `;` we can modify the value of a variable atmost one time
😒That why Solving such question does not make any sense. 
```C
int a, b;
b = ++a + a++ + ++a;
printf("%d %d",a,b); // its output is compiler dependent
```


#### <font color="#00b050">Bitwise Operator : : </font> <font color="#00b050">works on Binary level</font>
- Bitwise AND `&`
- Bitwise OR `|`
- Bitwise XOR `^`
- Bitwise NOT `~`
- Bitwise left shift `<<`
- Bitwise Right shift `>>`

Bitwise AND `&` - If both bit 1 then only Ans 1 -
```C
int a = 5 ,b = 17 ,c;
c = a & b;
printf("%d",c); //1
//5  = 00101
//17 = 10001
//c  = 00001
```

Bitwise XOR `^` - If both bit same then only Ans 0 -
``` C
int a = 5 ,b = 17 ,c;
c = a ^ b;
printf("%d",c); //20
//5  = 00101
//17 = 10001
//c  = 10100
```

Bitwise Left Shift `<<` - It just shift all the bits in left direction -
```C
int a = 5;
b = a < 1;
printf("%d",b); //10
//00000101 (5)
//00001010 (10)
```

If we have binary Number `101` and in the right side we can append 0 or 1 then how the number changes ?there is logic that we have to know.
- Appending Zero in last of `101` then it becomes - `1010` - New number 2(old) 
- Appending One in last of `101` then it becomes - `1011` - New number 2 (old) +1
This is the Logic of Appending digits in the right side of any binary number.

Bitwise Right Shift `>>`  - It just shift all the bits to right direction-
```C
int a = 5;
b = a > 1;
printf("%d",b); //2
//00000101 (5)
//00000010 (2)
```
Right shift operator just half (integer) the value.

Bitwise NOT `~`  - It just shift all the bits to right direction-
```C
int a = 5;
a = 5;
printf("%d",~(a)); //-6
//~a = -(a+1)
//~5 = -(5+1) = -6
```

#### <font color="#00b050">Ternary Operator : : ( ? : ) </font>
Before understanding Ternary Operator, you have to know about two terminologies : -
- <font color="#e36c09">Expression : :</font> Any Statement which have some Value, Every Expression is Statement but Every Statement is not Expression.
- <font color="#e36c09">Statement : : </font>The program of C is build with multiple statement like `int a;`declaration statement `a=10;`Assignment Statement

Its a valid program it will run but does not give any output result.
```C
#include<stdio.h>
void main(){
12;  //statement and expression
17.5; //statement and expression
}
```

---
<font color="#00b0f0">Our Ternary Operator is also based on 3 Expression .</font>
- `expression1 ? expression2 : expression3`
Based on the `expression 1`, it can be `True or false`, that actually decides the output of the Ternary Operator which can be `expression 2` or `expression 3`

<font color="#ffff00">Problem-1</font>
```C
int a;
a = 9 != 3 > 5 ? 1 == 8 != 3 ? 10 : 20 : 30 ;
a = (9 != 3 > 5) ? (1 == 8 != 3 ? 10 : 20) : 30 ;
a = 1 ? (1 == 8 != 3 ? 10 : 20) : 30 ;
a = 1 == 8 != 3 ? 10 : 20;
a = 1 ? 10 : 20;
a = 10;
```

<font color="#ffff00">Problem-2</font>
```C
int a = 2, b = 2, c = 0, d = 2, e;
e = ((a++ && b++) && c++) || d++;
e = 1
```

<font color="#ffff00">Problem-3</font>
```C
a = 15 < 2 ? 1 != 12 > 15 ? 10 : 20 : 4 < 7 != 7 > 9 ? !5 ? 30 : 1 != 1 ? 4 : 5  : 6 ;
Sove this Your Note book, a =  4
```

<font color="#ffff00">Problem-4</font>
```C
a = 5 < 12 ? printf("GATE") && prinf("Wallah") || printf("2023") : prinf("sir");
Sove this Your Note book, a =  GATEWallah1
```

<font color="#ffff00">problem-5</font>
```C
int y;
int x = 12;
y = (x & 1) ? prinf("hello") : prinf("Everyone");
printf("%d",y)
o/p = Everyone8
```

#### <font color="#00b050">Short hand Operators : :</font>

- `x = x + 10`  = `x += 10`
- `x = x - 10`  = `x -= 10`
- `x = x * 10`  = `x *= 10`
- `x = x / 10`  = `x /= 10`
- `x = x % 10`  = `x %= 10`
- `x = x | 10`  = `x |= 10`
- `x = x << 10`  = `x <<= 10`
- `x = x >> 10`  = `x >>= 10`
- `x = x ^ 10`  = `x ^= 10`


#DataType_Operators