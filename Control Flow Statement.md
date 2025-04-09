By default the program executes in the order in which the programmer writes statements as. ( Top to bottom )
🤔If due to some reasons Programmer wants to change or alter the default order of Execution. then Programmer needs to use the Concept of <font color="#ffff00">Control Flow Statements </font>.
For that C -Language Provides CFS 🥲

==C-Language CFS can be Classify into 3 Categories== 

| Selection Statements | Iterative Statements (Repeatitive) | Jump Statements |
| -------------------- | ---------------------------------- | --------------- |
| if                   | For                                | Continue        |
| if-else              | While                              | break           |
| if else-if else      | do-While                           | exit            |
| if - else if         |                                    | return          |

### <font color="#fac08f">Selection Statements </font>allows programmer to select those specific statements from our whole program. that programmer wants to executes based on some conditions only rather than executing all statement in once which is Default flow.

```C
if( condition / expression ){ //this should never be empty!
s1;
s2;
s3;
}
```

```C
if(12+3*4)
printf("2"); // without parantheses if() executes till first semi-colon ;
printf("3");
```

```C
void main(){
int i=3;
if(i<2); // without parantheses if() executes till first semi-colon ;
printf("Hello");
}
```

```C
if(2)
printf("2"); //2
if(3)
printf("3"); //3
if(4)
printf("4"); //4
//All if`s block are different in themselves !
```

<font color="#ffff00">Program for Even or Odd Logic !</font>
```C
int a;
if(a % 2 == 0 ){
printf("Even");
}
```

```C
if( (a & 1) == 0 ){
printf("Even");
}
```

```C
if( ((a>>1)<<1) == a ){ //right most bit may be loose(case of odd) or not! otherwise even
printf("Even");
}
```

---

```C
if( condition / expression ){ //this should never be empty!
s1;
s2;
}

else{ //Alternate Block of code
s3;
s4;
}
```

```C
if(2){
printf("Hello"); // without parantheses if() executes till first semi-colon ;
printf("Maza");
else  //else block should be right after the if block || thats why Error is there !
printf("Aa raha")
printf("Ya nhi")
```

```C
int i = 1;
if(i+2-3){
printf("Hello");
}
else{
printf("2");
printf("3");
}
```

---

```C

If(expression1){
s1;
}

else if(expression2){
s2;
}

else{
s3;
}
```

```C
if(2)
printf("2"); //this will executes only !
else if(3)
printf("3");
else if(4)
printf("4");
```

---

<font color="#ffff00">Let`s` Try to find Maximum Among 3 Number.</font>
```C
int a,b,c;
if(a>b && a>c)
 printf("%d is largest",a);
if(b>a && b>c)
 printf("%d is largest",b);
if(c>a && c>b)
 printf("%d is largest",c);
//This is not the Optimized Program but it works well! with unnessary Process
```

Little Bit Optimized : : Code
```C
int a, b, c;
if(a>b && a>c)
 printf("%d is large",a);
else{
 if(b>c){
 printf("%d is large",b);
 }
 else{
 printf("%d is large",c);
 }
}
```

Using Ternary Operator : : Code 
```C
int a,b,c,large;
large = (a>b && a>c) ? a : (b>c) ? b : c ;
```

```C
int a,b,c,d,large;
large = (a>b && a>c && a>d)? a : (b>c b>d)? b : (c>d)? c : d ;
```


### <font color="#fac08f">Iterative or Repeatitive Statements </font> Allow the programmer to Execute a Piece of code for the multiple times like for 100 or more times, Based on some Condition until the condition will not becomes false .

Syntax of for-loop : :
```C
for( expression1 ; expression2 ; expression3 ){
//code
}
//expression 1 executed for 1 time only.
//expression 2 is evaluated its True / False.
//code will executed if expression 2 is evaluated as True.
//then expression 3 is evaluated then.
```

```C
for ( i=6 ; i<=10 ; i++ ){
printf("Robin"); // Robin * 5 times
}
```

```C
for(i=10 ; i<=100 ; i++){
Printf("Robin"); // Robin * (100-10+1)=91 times
}
```

- <font color="#92d050">Expression</font> is a statement which have some value.

```C
int a = 1;
for( 10 ; a <= 3 ; 12 ){
printf("Robin"); // 2 times executes
}
```

```C
char ch = 1;
for(ch=1; ch; ch++) //without curly brackets, scope of for loop is till to the first semi-colon ; 
 printf("Robin"); // Robin * 255times
printf("End"); // End * 1 times
```

```C
char ch;
for(ch=1; ch; ch+2) 
 printf("pankaj"); // infinite times Executes. after 255 plus 2 leads to 1 so, infinite
```

```C
int i = 1;
for(printf("1"); ch<=5; printf("3")){
printf("2");
i++
}
//12323232323
```

```C
for(10;11;12){
printf("Robin"); //indinite times executes
}
```

---

<font color="#ffc000">In for loop All 3 Expressions are Optional</font> We can omit / neglect all of them ! But the 2 semi-colon must be Mandatory
```C
int i = 1;
for(  ;i<=5; i++){
printf("Robin") // print 5 times
}
```

```C
int i = 1;
for( ; i<=5 ; ){
printf("Robin");
i++;
} 
```

In for loop if we omit <font color="#ffc000">Expression 2</font> then by default compiler considered at place of<font color="#ffc000"> Expression 2</font> as Non Zero <font color="#ffc000">True</font> Value 
```C
int i = 1;
for( ;  ; ){
printf("Robin"); // prints for infinite times
}
```

```C
int i = -1
for(i++;++i;i++){
printf("Robin"); // prints for infinite times 
}
```

```C
int i = 1
for( ; ++i<5 ; ){
printf("%d",i); //2 3 4
}
```

```C
for(i=1; i<=10; i+2){
printf("Robin"); // this executes for 5 times.
}
```

```C
for(i=1; i<=n; i+2){
printf("Robin"); // this executes for celling(n/2) times.
}
```

```C
for(i=0; i<=n; i+2){
printf("Robin"); // this executes for celling(n/2) add + 1 only if n(even) times.
}
```

```C
for(i = 1; i<=n; i=i*2){
printf("Robin"); //no. of times this print ?
}
```
- `i` = 1 , 2<sup>1</sup> , 2<sup>2</sup> , 2<sup>3</sup> , 2<sup>4</sup> ---  2<sup>k</sup>  `(printf runs on these values)`
-  Means `Printf()` runs for `K + 1` times
-  2<sup>k</sup> `< =` `n`
- taking `log()` both side -
- k `log(2)` `< =` `log(n)`
- k `< =` `log(n)` / `log(2)`
- k `< =` log<sub>2</sub>(n)
-  k `=`  `floor`(log<sub>2</sub>(n))
- So, `Printf()` Runs for `floor`(log<sub>2</sub>(n)) + 1

Let`s` Understand Little about<font color="#ffc000"> Nested for loop</font>

```C
for(i = 1; i<=n; i++){
printf("Robin"); // n times
}
```

```C
for(i = 1; i<=3; i++)
{
  for(j = 1; j<=n; j++)
  {
  printf("Robin"); // 3n time
  }
}
```

```C
for(i = 1; i<=n; i++)
{
  for(j = 1; j<=n; j++)
  {
  printf("Robin"); // n*n time
  }
}
```

```C
for(i = 1; i<=n; i++)
{
  for(j = 1; j<=n; j=j*2)
  {
  printf("Robin"); // n (1+floor(log-base2 n))
  }
}
```

```C
for(i = 2; i<=n; i=i*2)
{
  printf("Robin"); //floor(log-base2 n)
}
```
<font color="#ffc000">Whatever till we study are known as Independent Nested Loop.  !</font>
Now we study about the possible categories <font color="#d99694">Dependent Nested Loop</font>

### <font color="#ffc000">Garbage Value </font> 
By declaring a Variable we are just label a memory location with that identifier name, and this memory location may already contains some data if the programmer not initialize variable explicitly. then that previously resides data is known as Garbage Value for The variable 

