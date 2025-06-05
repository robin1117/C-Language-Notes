<font color="#f79646">As its name pointer what`s it actual meaning ?</font> pointer name suggested that there is something that pointes to somewhere . 
in programming context <font color="#c00000">Pointer</font> is a special variable that are used to store address of other variable. no matter what other variable contains it can be <font color="#e36c09">value</font> or <font color="#c00000">address</font>

```C
int a = 10;
int *p; //pointer decleration
p = &a; //p can hold the address of varibale a
printf("%d",a) //10
printf("%d",p) //2036(memory location)
printf("%d",*a) //10
```

One thing definitely arises in your mind, While dereferencing `*` a pointer variable how do the compiler knows about how many bits from memory are need to access.
- Actually in the declaration like this `int *p` , Compiler come to know by pointers datatype.
- While dereferencing `*p` compiler access 4Bytes which is the size of `int`.

```C
int x = 10;
int *p;
p = &x;
printf("%d",*p);//10
```

![[POINTERACCESING.drawio (1).svg]]
- Compiler access 4bytes from 1000

---

<font color="#c3d69b">Example</font>
```C
int *p; //p is pointer to integer
int **q; // q is pointer to pointer to integer
```

<font color="#c3d69b">Example</font>

```C
int x = 5, *p, **p, ***r;
p = &x;
q = &p;
r = &q;
printf("%d",**q); //5
printf("%d",*q); //1000
```
![[pointer.drawio.svg]]

---

<font color="#c3d69b">Example</font>
```C
int a[4] ={10, 20, 30, 40};
int *p;
p = &a[0];
p = p+1;
printf("%d",p); // &a[20]
p++; //p = p+1; 
printf("%d",p); // &a[30]
```
- Name of the Array contains the address of the first element. ✅
```C
int a[4] ={10, 20, 30, 40};
int *p = a;
printf("%d",*p); //10
printf("%d",*(p+1)); //20
printf("%d",*(p+3)); //40
```


### <font color="#ffc000">Arrays</font> and <font color="#e36c09">Pointer</font> are Equivalent but not Same !

Example
```C
int a[4] = {10, 20, 30, 40};
int *p = a;
```
We can do like this - 
```C
printf("%d",p[0]); //10
printf("%d",p[1]); //20
printf("%d",p[2]); //30
printf("%d",p[3]); //40
```
According to Array - `*(x+i) = x[i]`
```C
printf("%d",*(p+0)); //10
printf("%d",*(p+1)); //20
printf("%d",*(p+2)); //30
printf("%d",*(p+3)); //40
```
- This is the Similarity Between Pointer and Array.✅
---
🤔Don`t` you curious about to know Difference Between Pointers & Array ?

```C
int a[4] = {10, 20, 30, 40};
```
- `a++`❌
- `a--`❌
- `--a`❌
- `++a` ❌

```C
int a = {10, ,20, 30, 40};
int *p;
```
- `p++`✅
- `p--`✅

---
**Arithmetic Validation of pointers**
- `Pointer + pointer`
- `pointer + 3` - Moving 3 Positions in Forward
- `pointer - 3` - Moving 3 Positions in Backward
- `pointer - pointer` 
     Only Possible when they are pointing address of Same Array


**Priority and Associativity** of <font color="#e36c09">pointer</font> `*`
- `*` and `++`  have Same Priority but Associative is `[R - L]`

---
⭐<font color="#ffff00">Note : </font>Whenever we are declearing a variable by appending `*` then its known as Pointer Variable, but apart from declaration any where, `*`  its know as Dereferencing Operator . 
### Complex Declaration !
In C Language there are some Important syntax Terminologies that you have to know -
- `()` - This represents functions ----<font color="#76923c">Priority 1</font> Associativity <font color="#76923c">L - R</font>
- `[]` - This represents Array ----<font color="#76923c">Priority 1</font> Associativity <font color="#76923c">L - R</font>
- `*` pointer ---<font color="#00b0f0">Priority 2</font> Associativity R - L
- `Identifier` - Variable-name, function-name ---<font color="#00b0f0">Priority 2</font> Associativity R - L
- `Data-type` - int, char, float ---<font color="#e36c09">Priority 3</font>

#### How we read Complex Declaration ?
- `int *(p[3])` - <font color="#92d050">P is Array of 3 pointers to integer</font>
     Basically this is the array of pointer Size `3` Storing `3` integers address
- `int(*p)[3]` - <font color="#92d050">P is an pointer to array of 3integers</font>
     This stores the address of whole array size `3`

<font color="#e36c09"> Complex-Example-</font>
- `int a[4]` = `{10, 20, 30, 40}`; --Priority 1
- `int *ptr[3]`  = `[a+1, a, a+2]`; --Priority 1
- `int **q`;
- `q = ptr`
     - `++q` - q represents the `&ptr[0]` - `++q` leads to represent the `&ptr[1]`
     - `*(++q)` - `q = q + 1` the `*q` q points `&ptr[2]`.
     - `printf("%u",++(*q))` <font color="#00b0f0">40 will be the answer</font>

### Some Examples On [[Pointer Complex Declaration]] -

#Arrays_Pointer