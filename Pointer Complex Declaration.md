- `int (*p)[4]` - p is a pointer to array of 4 integers - 
     - means p is pointer which can store address of whole array of size 4 integers

- `int *(p[4])` - P is an array of 4 pointers to integer -
     - means p is the array of size 4 which can store 4 integer addresses 

- `int (*p)(int)` - P is a pointer function that takes one integer argument return an integer value
     - means p can store the address of function that takes one argument and returns one integer value

<font color="#e36c09">Example 1</font>
```C
void fun (int *);
void main(){
int a[4] = {10, 20, 30, 40};
fun(a);
printf("%d"a[0],a[1]); //10 21
}

void fun(int * p){
++p;
++*p;
}
```


<font color="#e36c09">Example 2</font>
```C
void fun (int *);
void main(){
int a[4] = {10, 20, 30, 40};
fun(a);
printf("%d"a[0],a[1]); //10 20
}

void fun(int * p){
*p++;
}
```

<font color="#e36c09">Example 3</font>
```C
void fun (int *);
void main(){
int a[4] = {10, 20, 30, 40};
fun(a);
printf("%d"a[0],a[1]); // 11 20
}

void fun(int * p){
++*p++;
}
```

**Note :**
One thing about Increment  / Decrement operator keep it in your mind  - its result is treated as Constant. So we cannot do like this way-
- ❌`++(++p)` this is something like `++5` which is Invalid

<font color="#c3d69b">Whenever we pass an array we were passing a reference address</font>, you know guys array name itself represents an address,
There is nothing like pass by value in C in context with arrays

### What`s` The general way Pass an Array !

```C
void main(){
int a[4] = {10, 20 ,30, 40};
fun(a);
}

void fun(int *p){

}
void fun(int a[]){ //compiler internally treated as int* p

}
void fun(int a[4]){ //compiler internally treated as int* p

}
```

Whenever you pass an array it formal arguments treated an pointer, whether you write something else `a[]` `a[4]`. but compiler internally it treated as pointer.

<font color="#f79646">Example 4</font>
```C
void sum (int *, int);

void main(){
int a[4] = {10, 20, 30, 40};
sum(a, 4);

}

void sum(int *p, int n){
int s = 0;
for(int i=0;i<n;i++)
    s = s+ p[i];
printf("%d",s); //100
}
```


<font color="#f79646">Example 5</font>
```C
void fun(int *);

void main(){
int a[2][3]={10,20,30,40,50,60};
fun(a[0]);
printf("%d %d %d",a[0][0],a[0][1],a[0][2]); //10 20 100
}

void fun(int *p){
++p;
*p++;
*++p;
p--;
*p = 100;
}
```

<font color="#f79646">Example 6</font>
```C
void main(){
int a[2][3]={10,20,30,40,50,60};
fun(a);
}

void fun(int (*p)[3]){
++p;
printf("%d",*((*p+1)+1)); // 60
}

```

<font color="#00b0f0">BrainStorm</font> : - when we declare a pointer we have to tell to to compiler about its data type and generally we provide same datatype whose variable address we want to store Right -
Don`t` you might think what happen if we provide some other data type to our pointer variable that is different from our variable data type whose address we want to store ?

```C
int a = 300;
char *p;
p = (char*)&a; //her we typecaste the address for compiler 
printf("%d",*p); //while dereferincing p compiler access 1byte == 44
```

```C
int a = 160;
char *p;
p = (char*)&p;
printf("%d",*p); //-96
```

How these unexpected answers are coming ? to understand these you have to know first how these variables are stored in memory !
Basically in the memory data can get stored in two ways Little-Endian , Big-Endian for more details about, check COA -
for now we consider Little Endian - According to which LSB stores first in memory !

So how `int a = 300 (4bytes)` will stored in memory .

| MSB      |          |          | LSB      |
| -------- | -------- | -------- | -------- |
| 00000000 | 00000000 | 00000001 | 00101100 |
So,
`printf("%d",*p)` This line prints `44` because  our pointer datatype is `char` so, while dereferencing it fetches `1 byte` from memory only   
[[More on Pointers]]

[[Types of pointers]]

[[How do the Computer Understand Negative Numbers]]

#Arrays_Pointer