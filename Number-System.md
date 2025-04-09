🫡You will be studied about this in Digital-Logic in a good way.
👌But for now we are just take basic overview about Number System.

Generally there are four types of number systems : -
- Decimal Number-System -base 10
- Binary Number-System -base 2
- Octal Number-System -base 8
- Hexadecimal Number-System -base 16
---
🤔<font color="#ffff00">What`s` the logic we apply ?</font> when we add new value at the end of any number !
lets take example of `Decimal Number` and the same login you can use with other number system also
- ( 24 )<sub>10</sub> = 2 * 10<sup>1</sup> + 4 * 10<sup>0</sup> 
- Adding new Value in 24 it becomes 243
- 243 = 2 * 10<sup>2</sup> + 4 * 10<sup>1</sup> + 3 * 10<sup>0</sup>
- 243 = (2 * 10<sup>1</sup> + 4 * 10<sup>0</sup> )10+ 3 * 10<sup>0</sup>
- `New Value = ( old value * 10 + Symbol )`
- 243 = 24 * 10 + 3
---
For `Binary System` -
- `New Value = ( old value * 2 + symbol )`
```C
a = 10100(20) ~~~ Append(0) ~~~~ 101000(40) ~~~~~last bit(0)~~{EVEN}
a = 10100(20) ~~~ Append(1) ~~~~ 101001(41) ~~~~~last bit(1)~~{ODD}
```

<font color="#ffff00">Conclusion !</font>
- In Binary-Number if Last-Bit (ZERO) - then number is <font color="#fac08f">Even</font>.
- In Binary-Number if Last-Bit (ONE) - then number is <font color="#fac08f">odd</font>.
- It means we can easily find the given <font color="#e36c09">Binary-Number</font> is <font color="#fac08f">Even</font> or <font color="#fac08f">Odd</font> by just analysing <font color="#fac08f">last-bit only</font>
- Practically By just Making Bitwise AND `&` between the <font color="#e36c09">Binary-Number</font> and `1` ,we can find the about corresponding Binary-Number is Even or Odd.

```C
Even no & 1 = 0
Odd no & 1 = 1
```

---
let`s`  talk about Bitwise XOR `^`
- `5 ^ 5` = 0
- `5 ^ 5 ^ 5` = 5
- `5 ^ 5 ^ 5 ^ 5` = 0
- `5 ^ 1 ^ 3 ^ 5 ^ 3 ^ 1 ^ 4` = 4
XOR of two same number leads to always Zero 

<font color="#ffff00">Swapping !</font>

<font color="#00b0f0">Using 3 Variable </font>
```C
int a, b, c;
c = a;
a = b;
b = c;
```

<font color="#00b0f0">Using 2 Variable </font>
```C
int a, b, c;
a = a + b;
b = a - b;
a = a - b;
```

<font color="#00b0f0">Using XOR </font>
```C
int a = 10, b = 20;
a = a ^ b; //a=[20 ^ 10]
b = a ^ b; //b=[10]
a = a ^ b // a=[20]
```

<font color="#00b0f0">Unique Way</font> of swapping in Single line 
```C
int a = 5, b = 10;
b = ( a + b ) - (a = b);
printf("%d",a); //10
printf("%d",b); //5
```

---
<font color="#ffff00">A New Logic on Binary Numbers !</font>
- 2<sup>something</sup> value always contain a single 1 in its binary form.
- 2 = `10`
- 2<sup>2</sup> = 100
- 2<sup>8</sup> = 1000
This Concept should be in your mind - 
- ( 2<sup>n</sup> -1 ) & 2<sup>n</sup> = 0
- ( 2<sup>n</sup> -1 ) + 2<sup>n</sup> = 2<sup>n+1</sup>-1

00011111 - (2<sup>5</sup> -1)
<u>00000001 - (1)</u>
00100000 - (2<sup>5</sup>)

<font color="#ffff00">GP - Formula</font> !
With the GP formula you derive how the formula (2<sup>5</sup> -1) comes 

![[GP formula.png| 400]]
![[GP Formula 2.png]]
### Some Important Formula that you should know about these !
<font color="#953734">Some Common Formulas-</font>
- `1 + 2 + 3 + 4 + 5 ----- k {SUM}= k(k+1)/2`  
- 1<sup>2</sup>  + 2<sup>2</sup>  + 3<sup>2</sup>  + 4<sup>2</sup> -------k<sup>2</sup>  `{SUM}= K(K+1)(2K+1)/2`
- 1<sup>3</sup> + 2<sup>3</sup> + 3<sup>3</sup> + 4<sup>3</sup> --------K<sup>3</sup> `{SUM}=` (K(K+1)/2)<sup>2</sup>

<font color="#953734">Arithmetic Progress (AP)-</font>
- S<sub>n</sub> = `n/2 (a+l)`
- S<sub>n</sub> = `n/2 (2a+(n-1)*d)`
![[AP nth term.png|500]]


#DataType_Operators