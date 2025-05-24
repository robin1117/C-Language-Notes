#functonAndStorageClasses
In mathematics, the Fibonacci sequence is a sequence in which each element is the sum of the two elements that precede it.

<font color="#9bbb59">0, 1</font> ,1 ,2 ,3 ,5 ,8 ,13 , 21 . . . . . . . . 

When we said every term is some of two element it means we require two term initially fixed.

```C
#include <stdio.h>

int fib(int n){
    if(n == 1){
        return 1;   
    }
    else if(n == 0){
        return 0;
    }
    else{
        return fib(n - 1) + fib(n - 2);
    }
}

int main(){
    int n = 3;
    int result = fib(n);
    printf("Fibonacci of %d is %d\n", n, result);
    return 0;
}

```