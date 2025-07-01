 In C programming, a String is a <font color="#f79646">Sequence of Characters terminated with a null character</font> `\0`,
`\0` Character tells the compiler this is the end of this String.
- `\0` treated as Single Character -
- `\0` with it compiler come to know that string is terminated -
In C whatever we write inside double quotes its consider be a STRING !  <font color="#ffc000">"Robin"</font>  for us ,But in the memory it is something look like / stored like -

| R   | o   | b   | i   | n   | \0  |
| --- | --- | --- | --- | --- | --- |


Character Array-
- `char name[]`  = `{'R','O','B','I','N'}`

Character String-
- `char name[]`  = `{'R','O','B','I','N','\0'}`

<font color="#9bbb59">Example-</font>
```C
char name[10] = "Robin";
printf("%s",name);
printf("%c",name[0]);
name[1] = 'b';
printf("%s",name);
```

Points to be noted -  : :
🔥As we know, every string must contain a null character (`\0`) at the end. This is why we need one extra character in our character array in addition to the size of the actual string.
🔥When declaring an array of characters to store a string, always try to provide a size that is one more than the length of the string to accommodate the null character (`\0`). which is present at the end of string.

- `char name[6] ="Robin"` ✅
- `char name[5] ="Robin"` ❌ Behaviour is Undefine otherwise !

<font color="#92d050">There is difference between Character Array and String</font>, in case of character array it does not matter weather its terminated with  `\0` or not. 
But in the case of string it must be ended with null character

<font color="#8064a2">EXAMPLE -</font>
```C
#include<Stdio.h>
void main(){
char name[] = "Robin";
printf("%s",name); //Robin
}
```
In case of String `printf`  it takes the address & print again and again till not getting null `\0` . that is also the reason why were null`\0` induced

```C
#include<Stdio.h>
void main(){
char name[] = "Robin";
printf("%s",name+1); //obin
}
```

String is nothing but it is address, it always provides address of its first element.
This means we can store this address in character pointer like -
- `char *p = "Robin";`

What are the differences comes when we declare an STRING with <font color="#f79646">character array </font> or <font color="#f79646">character pointer</font>

| `char a[]="Robin"`                                                                                                              | `char *p ="Robin"`                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| We can change any of the character of  of the String. <br>Because we are allow to change the content of array<br>`a[1] = 'C'` ✅ | String made with pointer cannot change <br>Because its stored in Read only memory .<br>`*(p+1) = C`❌ |
| Array name treated as constant. <br>`a = "Sapna"` ❌                                                                             | But we can change the address of `p` pointer<br>`p = "Sapna"`✅                                       |
| We can not do like this with array Name it treated as constant.<br>`a++`❌<br>`a--` ❌                                            | But we can apply increment or decrement operation over pointer.<br>`p++`✅<br>`p--`✅                  |
Stings are nothing but are the address and we can  just providing this address to `printf()` -  In case of string `Printf()` just take address of the first character and it find out you are going to print something that is actually a string , that why we can directly provide sting to `printf("Hello")` by Omitting `%s`.
And this `String("Hello")` is stored in Read only memory .

```C
prinf("Robin"); //Robin
prinf("%d","Robin"); //Robin "%s"optional
prinf("Robin"+1); //obin
```

---
```C
"Hello" // Address of 'H'
"Hello"+1 // Address of 'e'
*("Hello"+1) //e
```

```C
printf("%c",*("Hello"+1)); //e
printf("%c","Hello"[1]); //e
```
---
```C
char *p = "Hello";
char *q = "Hello";
```
Both the `p` and `q` are refers to the same string or single string `"Hello"` which stored in Read Only Memory

```C
char arr1[] = "Hello";
char arr2[] = "Hello";
```
In the case of array stings both `arr1` and `arr2` are referring different addresses of the string `"Hello"`  which have separate space in the memory

---
<font color="#f79646">Examples-</font>
```C
if("Gate"[1]=="Game"[1]){
	printf("Jai ho"); // Answer
}
else
	Printf("Meri");
```

<font color="#f79646">Examples-</font>
```C
char name[3][8] = {"Robin", "Kali", "Linus"};
printf("%s", name[0]);//Robin
printf("%s", name[0]+2);//bin
printf("%c", name[0]+2);//b
```

<font color="#f79646">Examples-</font>
```C
char name[3][13] = {"Amit", "Ram", "Balakrishn"};
//In such cases there is lot of memory wastage !
```

To overcome the wastage of memory we can use pointers !
```C
char *p = "Robin";
char *q = "Sapna";
char *r = "Vikram";
```

In more convenient way we can use pointers Array.
```C
char *p[3] = {"Robin","Sapna", "Vikram"};
printf("%s",*p); //Robin
printf("%s",*(p+1)); //Sapna
printf("%s",p[1]+2); //pna
printf("%s",p[2]+1); //ikram
printf("%c",p[1][2]); //p
```

#### Some important function for String.
- `Strlen()` : It returns the length if string.
	- It count char till first Null `char(\0)`

- `Strcpy()` : String copy.
	- It copy the whole string in addition with `\0` char ,form source to destination.
<font color="#f79646">Example</font>
```C
char a[10];
Strcpy(a,"Robin"); // 1st argument must be some memory area (array)
```

```C
char arr[10] = Robin Singh;
Strcpy(arr,"Ram"); // 1st argument must be some memory area (array)
printf("%d",arr) //Ram
printf("%d",arr+4) //n Singh
```

- `Strcat(str1, str2)`: It connect `str2` with `str1`
	- first Argument `str2` must has Array (space) enough Space Need for both String
<font color="#f79646">Example</font>
```C
char arr1[10] ="Robin";
char *p = "String";
Strcat(arr1,a);
printf("%S",arr1);
```

- `Strcmp(Str1,Str2)`
	- It is used to compare string `Str1` and `Str2`
	- If it found equal it returns Zero.
	- If it found unequal strings it returns the difference of ASCII code of the first unmatched characters, it will be `+ve` or `-ve` 

#### Taking Input as String

```C
char arr[20];
printf("Enter a number");
Scanf("%s",arr); //Robin Singh
printf("%s",arr); //Robin
```

`Scanf()` Reads value till not getting first space this  is the problem with `Scanf()`
That`s` why we use these function when we are working with strings.
- `gets()` 
- `puts()`

```C
char arr[20];
printf("Enter a number");
gets(arr); //Robin Singh
puts(arr); //Robni Singh
```



#Strings   