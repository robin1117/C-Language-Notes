As a beginner in CS, most of the students find this topic very hard, but I would like to tell you this is the easiest topic in this world. This why because Students make this topic difficult themselves.

### <font color="#92d050">Address</font>
Let`s`  first we talk about Addresses ! in real world .
Basically Address is of two types - 
- <font color="#00b0f0">Absolute Address</font>
     - we can understand <font color="#00b0f0">Absolute address</font> in such a way, suppose your House address is `Street no 1, Kirti Nagar Bhiwani Harayna 127021, India` this is kind of Absolute address, because with this address anyone in this world can be reaches to my house
     - <font color="#00b0f0">Absolute address</font> is kind of root address

- <font color="#938953">Relative Address </font>
     - There might be a situation, someone come to my colony but he did`t` know the exact location of my house, so what he have to do now , he may be asked randomly anyone in my area about my house , then that person taught to him in such way the 4th one house is of  robin`s`  which is <font color="#938953">Relative Address</font> 
     - Overall we can understand <font color="#938953">Relative address </font>in such a way that we can finding some address using another address

✅<font color="#938953">Relative addressing is the purpose of Arrays introduction in the C Language </font>

<font color="#b2a2c7">How to find address in C langauge</font> ?
In C language we have operator known as `&` - <font color="#de7802">Address of Operator </font>- using which we can find address of any variable.
- If I know some address it means I just standing in front of that block

<font color="#b2a2c7">How to find value at particular address ?</font>
Similarly for accessing value form address we have operator `*` - <font color="#f79646">Value at memory location</font> - which retrieves value from address.
- using `*` means we are inside the block of the provided address

### Why Arrays ?
Whenever we want to create multiple variables of same type then we use arrays. Arrays is groups of elements of same type which stored in continuous memory locations.

```C
int a[3]; //we are asking 16B memory from compiler.

// | 4Byte | 4Byte |  4Byte  | ---total 16 bit memory 
// 100     104     108
// initally all 3 varibales holds Garbage values.
```

Each element in array have their unique index Number, using which we can access elements. 

```C
int a[4];
a[0] = 10;
```

Array name holds the address of first element of the array.

```C
int a[4];
printf("%d",a); //456985
printf("%d",*a); //10
```

The way we can declare Arrays -
❌`int a[]` 
✅`int a[] = {10, 20, 30}`
✅`int [2] = {1, 2, 3, 4, 5}`
✅`int a[4]`
✅`int a[2+2]`
✅`int a[2*3]`
✅`int a[4*sizeof(int)]`
✅`int a[size]`
    -  Array size can be unsigned integer greater than zero

### Some Important points about Array in C : :
- Collection of same type of element.
- Element are Stored in Sequence one after another.
- Internally Array Name is a Constant Pointer.
- Array Name refers to the Address of the first element of array.
- Relative Addressing
- Normal variable `int a = {1}`
- Array name cannot be L value of any assignment Statement. as it representing address of the first element of array.

### Playing with Address in Arrays : :
- We know that Array name refers to the address of the first element that Array.
- If `a` is the name of array then `&a` will revers to the address of whole array

```C
int a[4] = {10, 20, 30, 40};
printf("%d",a); // 1000 Address of 1st element
printf("%d",&a[0]); // 1000 Address of 1st element
printf("%d",&a); //1000 Address of whole array
```

Name of array does not represent address with 2 Operator `&` and `sizeof()`, other than it treated as object.

Thinks need to keep in mind !
- If `a` is address / pointer variable then `a+1` ?
- `address + value => address`
- `value + address => address`
- `address + address => invalid` 

if declaration of array is having n- dimension and : :
- Any where in program you provide exactly n-dimension then it is an element .
- Any where in program you provide less than n-dimension then it is an element .

```C
a[2][3] = {1,2,3,6,7,8};

a //refers Address
a[0] // refers Address
a[1] // refers Address
a[1][1] // refer element
```

### How to find a + 1 : :
To find this kind of addition you have to follow some steps is `a` is address .
- First you have to determine What is a ? 
- If it is address whose address is this ?
- what the size of that datatype ?

Like this !
```C
int a[4] = {1, 2, 3, 4};
a + 1; // a is address! this address points &a[0], size of a[0] is 4 bytes So .
&a[0] + 1 * 4;
1000  + 4
1004 //this is the address of a[1];
```
- `a + 1` =  `&a[1]` 
- `*( a + 1 )` = `a[1]` = `2` `<this is actually what compiler did behied the seen>` 

```C
int a[4] ={10,20,30,40};
printf("%d",a[1]); //20
printf("%d",1[a]); //20
printf("%d",*(a+1)); //20
printf("%d",*(1+a)); //20
```

`*(a+i)` = `*(i+a)` = `i[a]` = `a[i]`  

```C
int a[5] = {10, 20, 30, 40, 50};
printf("%d",a); //1000
printf("%d",&a); //1000
printf("%d",a+1); //1004
printf("%d",&a +1); //1020
printf("%d",*(a+1)); //20
```
❌ Invalid `int 4[a] = {10,20,30,40};`❌

### 2D - Arrays : :
Till now you were studied lot of about 1D array , but the interesting thing in C is you can make 2D and 3D arrays have you here about 2D or 3D arrays before ?

<font color="#f79646">Visually 2D arrays is something look like -</font>
![[2D arrays.svg| 700]]

- `int a[2][3]`
- `&a` = Address of whole array 24 bytes
- `a` = `&a[0]` - - Here `a` represents  address of `a[0]`
- `a[0]` = `&a[0][0]`

<font color="#00b050">Example -</font>
```C
int a[2][3] = {10, 20, 30, 40, 50, 60};
printf("%u",a); //1000 12bytes Address of a[0] array
printf("%u",a[0]); //1000 4bytes Address of a[0][0] element
printf("%u",&a); //1000 24Bytes Address of whole array
```

<font color="#00b050">Example -</font>
```C
int a[2][3] = {10, 20, 30, 40, 50, 60};
printf("%u",a[0]+1); //1004
printf("%u",a+1); //1012 
printf("%u",&a+1); //1024
```

<font color="#00b050">Example -</font>
```C
int a[3][4] = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120, 130};
printf("%u",a) //1000 16bytes
printf("%u",&a) //1000 48bytes
printf("%u",a[0]) //1000 4bytes
printf("%u",&a[0][0]) //1000 4bytes
printf("%u",*a) //1000 4bytes
printf("%u",**a) //10
printf("%u",a+1) //1016 16bytes
printf("%u",*a+1) //1004 4bytes
printf("%u",a[0]+1) //1004 4bytes
```

<font color="#ffff00">For 2D Arrays </font>🔥
- `*(a[0]+1) = a[0][1]`=== `*(a[1]+1) = a[1][1]`
-  `*(a[0]+j) = a[0][j]`=== `*(a[i]+2) = a[i][2]`
- `*(a[i]+j) = a[i][j]` = `*(*(a+i) + j)`


### 3D Arrays : :
Similarly we can make and understand 3D arrays as we understand 2D. Let`s` Understand it by example.
<font color="#f79646">Visually 3D arrays is something look like -</font>
![[3D array.svg|700]]

<font color="#00b050">Example -</font>
```C
int a[2][3][2] = {1,2,3,4,5,6,7,8,9,10,11,12}
printf("%u",a) //1000 24bytes
printf("%u",a[0]) //1000 8bytes
printf("%u",a[0][0]) //1000 4bytes
printf("%u",&a) //1000 48bytes
printf("%u",a+1) //1024 24bytes
printf("%u",a[0]+1) //1008 8bytes
printf("%u",a[0][0]+1) //1004 4bytes
printf("%u",&a+1) //1048
printf("%u",a[0][0][0]+1) //2
```

<font color="#00b050">Example -</font>
```C
int a[3][2][3] = {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18}
printf("%u",a); //1000 24bytes
printf("%u",&a); //1000 72bytes
printf("%u",a[0]); //1000 8bytes
printf("%u",a[0][0]); //1000 4bytes
printf("%u",a+1); //1024 
printf("%u",&a+1); //1072
printf("%u",a[0]+1); //1012
printf("%u",a[0][0]+1); //1004
printf("%u",a[0][0][0]+1); //2
printf("%u",*a); //1000 8bytes
printf("%u",**a); //1000 4bytes
printf("%u",***a); //1
printf("%u",*a+1); //1008 
printf("%u",**a+1); //1004
```

#### Declaration & Initialization of Array : :
If only Declaration is there without initialization it is mandatory to provide the size of each dimension of array .
- `int a[][]` ❌
- `int a[][10]` ❌
- `int a[2][2]` ✅
in case , we are initializing the array, there is flexibility that you can omit the size of <font color="#fac08f">1st dimension</font> no other dimension is having such flexibility
- `int a[][] = {1,2,3,4}`❌
- `int a[][3] = {1,2,3,4}`✅
- `int a[2][] = {1,2,3,4,5}`❌
- `int a[2][3] = {1,2,3,4,5,6}`✅

Practice these Examples and now let`s` we move ahead and learn about [[pointers]]

#Arrays_Pointer