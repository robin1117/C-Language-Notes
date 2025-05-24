#### <font color="#00b050">Perfect Number : : </font>
- Perfect number is a number in which the sum of all factors other than the number itself is equal to number .
- `Num = 6` -> ( <font color="#92d050">1, 2, 3</font>, <font color="#ff0000">6</font> ) Factors of 6
- The sum of 1 + 2 + 3 = 6 , So we can say that the number 6 is a Perfect number

<font color="#ffc000">Program to check for perfect number</font> -
```C
int n = 6;
int Sum = 0;

for(i = 1; i < n;i++){
 if( n % i == 0){
 sum = sum + i;
 }
}

if (sum == n){
printf("Perfect Number !");
}
```

#### <font color="#00b050">Prime Number : :</font>
- A number which is Divisible by 1 and itself only .
- `Num = 7` -> <font color="#92d050">1</font> 2 3 4 5 6 <font color="#92d050">7</font>

<font color="#ffc000">Program to check for Prime Number</font>
```C
int n;
for( i = 2; i < n; i++ ){
 if( n % i == 0 ){
 printf("Not-Prime-Number");
 break;
 }
}

if( i == n ){
printf("Prime-Number");
}
```

```C
int n;
int count = 
0;
for( i=2; i<n; i++){
if( n % i == 0){
count++;
}
}

if ( count == 0 ){
printf("Prime Number")
}

else{
printf("Not Prime Number")
}

```

#### <font color="#00b050">Find the Number of Digit`s` in the in the provided  Number : :</font>

By dividing any number with its base like `342/10` in Decimal Case its result is 34.2( floating point ) and integer form its 34 and so on.
- With this concept we just made our below program.
```C
int n = 356, count = 0;

if (n == 0){
count = 1;
}

while(n != 0){
n = n/10;
count++;
}

printf("Number of digits: %d\n", count);
```

#### <font color="#00b050">Single digit Sum of a number : :</font>
- The single-digit sum of an integer is a type of problem where we repeatedly add all the digits of a number until the result becomes a single-digit number. WE USES THIS TO FIND <font color="#92cddc">DIGITAL SUM</font>

**Example:** Let’s say the number is **9875**  
9 + 8 + 7 + 5 = **29**  
2 + 9 = **11**  
1 + 1 = **2** → ✅ single-digit sum is 2

```C
int n;
if(n % 9 == 0){
printf("9");
}
else{
printf("%d", n%9);
}
```

(<font color="#92cddc">Decimal Number System</font>)<sub>10</sub>

| 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 10  | 11  | 12  | 13  | 14  | 15  | 16  | 17  | 18  |
| 19  | 20  | 21  | 22  | 23  | 24  | 25  | 26  | 27  |

(<font color="#92cddc">Octal Number System</font>)<sub>8</sub>

| 1   | 2   | 3   | 4   | 5   | 6   | 7   |
| --- | --- | --- | --- | --- | --- | --- |
| 10  | 11  | 12  | 13  | 14  | 15  | 16  |
| 17  | 20  | 21  | 22  | 23  | 24  | 25  |
#### <font color="#00b050">Power Vala Concept : :</font>
if we want to find the value of a<sup>b</sup> using C program -

```C
int a,b;
int prod = 1;
for (int i = 1; i <= b; i++){
prod = prod*a; 
}
printf("%d",result);
```
#### <font color="#00b050">Checking for Armstrong No : :</font>
- An Armstrong number is a number that is equal to the sum of its own digits, each raised to the power of the number of digits. For example, 153 is an Armstrong number because 1³ + 5³ + 3³ = 153

<font color="#ffc000">Easy-Version :</font>
```C
int n = 153;
int sum=0, last = 1;

while( n != 0 ){
last = n % 10;
n = n / 10;
sum = sum + (last * last * last)
}
printf("%d",last);

```

<font color="#ffc000">Actual-Version :</font>
```C
int original_number = 153;
int n = original_number;
int p = original_number;
int sum = 0;
int prod = 1;
int last;
int count = 0;

while(n != 0){
    n = n / 10;
    count++;
}

while(p != 0){
    last = p % 10;
    p = p / 10;
    prod=1;
    for(int i = 1; i<=count; i++){ 
        prod = prod * last;
        }
    sum = sum + prod;
}
printf("%d",sum);
```

#### <font color="#00b050">Checking For Strong Number : :</font>
- An Strong Number is a number whose sum of factorial of all own digits is equal to its number itself. 
```C
n = 145;
1! = 1;
4! = 24;
5! = 120;
```

```C
    int a = 145;
    int temp = a;  // Store original value for comparison
    int last;
    int sum = 0;

    while (temp != 0) {
        last = temp % 10;
        temp = temp / 10;

        int prod = 1;
        for (int i = 1; i <= last; i++) {
            prod *= i;
        }

        sum += prod;
    }
     if(sum == a){
    printf("This Show Strong Number");
     }
    else{
    printf("This Show Not Strong Number");
     }
```

#### <font color="#ffc000">Revers The Number : :</font>
```C
int a = 156;
int last;
int reversed=0;
while(a != 0){
last = a%10;
a = a/10;
reversed = reversed*10+last;
}
printf("%d",reversed);
```

#### <font color="#00b050">e<sup>x</sup> - Expansion ! : :</font>
e<sup>x</sup> = 1 +  x/1!  +  x<sup>2</sup>/2!  +  x<sup>3</sup>/3! . . . . ..  

```C
//find Exapanssion for x = 2 and for 4 terms

int sum = 0;
int x = 2;
for(int i = 0; i <= 3; i++){

     float y = 1;
     for(int j = 1; j <= i; j++){
      y = y * x;   
      }
      
      float fac = 1;
      for(int k = 1; k <= i; k++){
      fac = fac * k;     
      }
      
   sum = sum +(y/fac);
   
}

printf("%d",sum);
```



#controlFlowStatement