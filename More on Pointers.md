what we study till now in Complex Declaration about pointers -
- `int (*p)[4]` - P is a pointer to array of size 4 of integer
- `int *(*p)[5]` - P is a pointer to array of 5 pointer to integers
- `int *p[4]` - P is array of 4 pointers to integer
- `int (*p)()` - P is pointer to function that takes no argument and returns an integer
- `int (*p)(int float)` - P is a pointer to function that takes two arguments `int` & `float` and it returns an integer.
- `int(*p)(char*)` - P is pointer to function that takes a pointer to `char` as argument and return integer.
- `int (*f)(int*)` - f is pointer to function that takes a pointer integer as argument and returns `int`.

### Function Pointer -
We already discuss a lot about function in previous sections and over there we had saw how we <font color="#c3d69b">pass values</font> and <font color="#fac08f">address</font> to function.
include some extra knowledge with it--
Just like every variable have address in memory in the same way function whatever we declare also occupy some space in memory , this makes it clear that if function have address means we can make Pointer for it.
🫨this makes sense that we can also pass function as argument to another function

Let`s` make pointer for function type -`int Add(int, int)` 
- its pointer is something look like `int (*p)(int, int)` -
- Here `p` is a pointer to function that takes 2 integers arguments and returns integer -
- So we can do like this `p = Add` - This shows Name of function represent address of the function -

<font color="#fac08f">Example</font>-
```C
#include<stdio.h>
int Add(int a,int b){
return (a+b);
}
int Sub(int a, int b){
return (a-b);
}

void main(){
int (*p)(int, int);
p = Add;
printf("%d\n",(*p)(10,20)); //30
p = Sub;
printf("%d\n",(*p)(10,20)); //-10
}
```

<font color="#e36c09">Some GATE Questions -</font>

<font color="#e36c09">Example1</font>
```C
int a[4] = {10, 20, 30 ,40};
int *p[4] = {a+3, a+2, a+1, a};
int y;
y = --p[0]-p[1];
printf("%d",y); //0
printf("%d",*p[0]); //30
```

<font color="#e36c09">Example2</font>
```C
int a = 5, b = 10, c = 15;
int *p[3] ={&a, &b, &c};
printf("%d",*p[*p[1]-8]); //15
```

<font color="#e36c09">Example3</font>
```C
int a[] = {10, 20, 30, 40, 50};
int *p[] = {a, a+3, a+4, a+1, a+2};
int **ptr = p;
ptr++;
printf("%d %d",ptr-p, **ptr); //1 ,40
```

<font color="#e36c09">Example4</font>
```C
void f(int*);

int main() {
  int a[2][3] = {1, 2, 3, 4, 5, 6};
  f(a[1]);
printf("%d %d",a[1][1],a[1][2]); //5 6
return 0;
}

void f(int *p)
{
p--;
*p = *p * *p;
p--;
*p = *p * *p;
}
```

<font color="#e36c09">Example5</font>
```C
int a[4][5] = {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20};
printf("%d",*(*(a + **a+2))+3); //19
```

<font color="#e36c09">Example6</font>
```C
int f(int *a, int n){
if(n<=0) return 0;

else if(*a%2==0)
    return (*a + f(a+1,n-1));
    
else
    return *a - f(a+1,n-1);
}

void main(){
int a[] = {12, 7, 13, 4, 11, 6};
printf("%d",f(a,6)); //15
}
```

<font color="#e36c09">Example7</font>
```C
int f(int *p, int n){
if(n<=1) return 0;
else
   return Max(f(p+1,n-1), p[0]-p[1]);
}

void main(){
int a[] = {3, 5, 2, 6, 4};
printf("%d",f(a,5)); //3
}
```


#Arrays_Pointer