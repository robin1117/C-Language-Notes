#functonAndStorageClasses
Whenever an operation is define in term of itself is called recursion.
- In recursion many functions work together.
- there should be one case that can be solved without recursion, we can answer directly.
- base case for which the function does not call itself
- when a function call itself this is called recursion


✅In every Recursive code At least these two cases must be there.
```C
void fun(int n){
 if(?){
 //we can answer directly
 //easy to solve
 //No recusrion is needed
 }
 else{
 //input is large 
 //we can not answer directly
 //recusrion is needede
 }
}
```

```C
void fun(int n){
  if(n==1){
  printf("robin");
  return;
  }
  else{
  printf("robin");
  fun(n-1);
  }
} //This code will print 'robin' n times
```

✅Sum of digits of a number
```C
int sum_of_digits(int n){
  if(n==9){
  return n;
  }
  else{
  return (n%10 + sum_of_digits(n/10))
  }
}
```

✅A * B Using Recursion
```C
int mul(int i, int j){
  if(i==0 || j==0){
  return 0;
  }
  else{
  return(i+ mul(i,j-1));
  }
}

int main(){
int a = 6, b = 6;
printf("%d",mul(2,3));
}
```

✅A+B Using Recursion
```C
int add(int i, int j){
  if(i==0 ){
  return j;
  }
  else if(j ==0){
  return i;
  }
  else{
  return (1 +add(i,j-1)) ;
  }
}
int main(){
int a=6, b =5;
printf("%d",add(a,b));
}
```

✅a<sup>b</sup> using recursion 
```C
int power(int a , int b){
  if(a==0){
  return 0;
  }
  else if(b==0){
  return 1; 
  }
  else{
  return (a * power(a, b-1));
  }

}
int main(){
  int a=2, b =3;
  printf("%d",power(a,b));
}
```

✅find Decimal to Binary -
```C
void con(int a){
  if(a==0){
  printf("0");
  }
  else if(){
  printf("1");
  }
  else{
  con(a/2);
  printf("%d",a%2);
  }

  int main(){
  int a = 3;
  con(a);
  }
}
```

✅Convert Decimal to Hexa-Decimal
```C
void Hexa(int a){
    if (a==0){
    return;
    }
    else{
    Hexa(a/16);
    switch(a%16){
        case 10 : printf("A");
        break;
        case 11 : printf("B");
        break;
        case 12 : printf("C");
        break;
        case 13 : printf("D");
        break;
        case 14 : printf("E");
        break;
        case 15 : printf("F");
        break;
        default : printf("%d",a%16);
    }
    printf("%d",a%16);
    }
}

int main(){
int a = 10;
Hexa(a);
}
```

✅Convert Decimal to Hexa-Decimal
```C
void Octa(int a){
    if (a==0){
    return;
    }
    else{
    Hexa(a/8);
    printf("%d",a%8);
    }
}

int main(){
int a = 10;
Octa(a);
}
```

✅Calculate No. digits in a number.
```C
int cal(int a){
    if(a<=9){
    return 1;
    }
    else{
    return 1+cal(a/10);
    }
}

int main(){
int a = 19;
printf("%d",cal(a));
}
```

You can solve more problems like this one , but for now let`s`  we move ahead and discuss about a new problem know as [[Tower of hanoi(Puzzle)]] , [[Fibonacii Series]]