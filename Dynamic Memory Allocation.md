DMA provides us 4 function using which we can allocate and deallocate memory during Runtime. In the DMA we have to study about 4 inbuilt function -
- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

#### `malloc( a )` : :
- `malloc(size in Bytes)` - It Accepts One Mandatory <font color="#ffff00">Arguments( which should be an Unsigned Integer).</font> provided number refers to the number of bytes 
- <font color="#ffff00">Return : </font>It returns<font color="#6425d0"> Starting Address of Memory Block</font> . or <font color="#3f3f3f">NULL</font> if Memory Not available

```C
int *p = malloc(5) //it returns address of block whose size 5bytes
```

- Size of operator are used to find correct size of Datatype, for different computer it is different . that`s` why we need to use `Sizeof()`

```C
int *p = malloc(Sizeof(int)*5) // More reliable and flexible
```

```C
malloc(100); //malloc findes 100bytes in memory if it is available it returns starting address of block, If not available it returns NULL pointer
```

<font color="#de7802">Example</font>
```C
#include <stdio.h>
#include<stdlib.h>

int main()
{
int *p = malloc(sizeof(int)*5);
for(int i = 0; i<5; i++)
	scanf("%d",p+i);

for(int i = 0; i<5; i++)
	printf("%d\n",(p+i));
}
```

#### `calloc (a, b)` : :
- `calloc(a, b)` it takes two arguments 
	- `a` : : No. of blocks -
	- `b` : : Size of each block -

Difference Between `malloc()` & `calloc()` - 
- `malloc()` : : It searches & returns starting address.
- `calloc()` : : It searches & Initializes all block with zero & returns Starting address.


#### `realloc (P, N)` : :
- `realloc()` : : It used to re-allocate the previous Size that was previously acquired by `malloc()` or `calloc()`.

<font color="#c0504d">Example</font>
```C
int *p = malloc(5*sizeof(int));// 20 bytes
p = realloc(p, 10*sizeof(int));// 40 bytes Without loosing previous data we get extra 20 bytes this can be done realloc :
```

#### Memory Leakage Problem
Memory leak occurs when programmers occupy in heap and forget to release it.

The Consequences of memory leak is that it reduces the performance of the computer by reducing the amount of available memory

```C
void fun{
int *p = malloc(200*Sizeof(int));
// free(p);
}

void main(){
fun();
fun();
fun();
fun();
}
```

In the above code fun function allocates 800bytes memory in each call and after the termination of each call function leave allocated memory as it is , without getting freed.
Programmer should free the allocated memory by using `free()` keyword

#Arrays_Pointer