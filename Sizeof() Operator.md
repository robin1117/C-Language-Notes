- `Sizeof()` Operator Comes Under the Category of Unary Operator 
- `Sizeof()` gives result at Compile Time .
- `Sizeof()` always returns Unsigned integer
```C
int a;
Sizeof(a) //4
```

```C
int i = 10;
printf("%u",sizeof(i+10)); //4
```

```C
int = 10;
printf("%u",sizeof(i=i+10));//No need to evaluate Compiler know `i` size so its just return size of int.
printf("%d",i);
//output = 4 ,10
```

```C
float b = 12.7;
10 + b -->Variable
10 + 5.6 -->literal //floating point literals are considered as double
```

```C
int main(void) {
  int c = sizeof('a');
  printf("%d",c); //4 
}
```
- In **C**, when you write `'a'`, it is **not** a `char` but an **integer constant**.
- This is because C treats character literals as `int` values (their ASCII codes).
- The ASCII code of `'a'` is **97**, and `97` is stored as an `int`.

#DataType_Operators