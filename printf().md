whatever you provide inside double quotes to `printf()` (in C) it printed exactly as it is **unless** you use format specifiers like `%d`, `%s`
`printf()` is a function, So I mean its a function and every function return some value then what actually the `printf()`returns. <font color="#92d050">Basically it returns number of Characters/Symbols it printed.</font>

```C
int a;
a = printf("%d",4/2+3*2);
printf("%d",a); // 81
```

```C
int a;
a = printf("%d",printf("Gate 2023"));
printf("%d",a); // Gate 202391
```

```C
int main(void) {
  int a= printf("/n");
  printf("%d",a); //1
}
```
#DataType_Operators