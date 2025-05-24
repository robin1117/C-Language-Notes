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
| Switch Statement     |                                    |                 |
- If you want to how actually `\t` works, for that first you need to know how  [[Output Screen]] was divided into parts in C language !
- After Knowing CFS its becoming better to solve [[Some Mathematical Programs]]
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

#### <font color="#00b050">Syntax of for-loop : :</font>
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
- So, `Printf()` Runs for {`floor`(log<sub>2</sub>(n)) } + 1 

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

```C
for(i = 1; i<=n; i++)
{
  for(j = i; j<=2*i; j++)
  {
  printf("Robin");
  }
}
```

If  we want to count how many times the above `Printf("Robin")` executes then here we will have to use <font color="#953734">Loop Unfolding </font>Method -

| `i=1`     | `i=2`        | `i=3`        | `i = n`       |
| --------- | ------------ | ------------ | ------------- |
| `j = 1,2` | `j = 2 to 4` | `j = 3 to 9` | `j = n to 2n` |
| 2-time    | 3-times      | 7times       | (n+1)times    |
Using Formula : S<sub>n</sub> = `n/2 ( First-Term + Last-term )`
- First Term = 2
- Last Term = (n+1)
So according to Formula : S<sub>n</sub> = n/2 ( 2 + (n+1) )
-  S<sub>n</sub> = `n/2 ( n+3 )` Answer value is depends on `n`
- if `n = 1` S<sub>1</sub> = `1/2 (1+3)` = `1/2 (4)` = `2` times

<font color="#ffc000">Another Example -</font>
```C
for(i = 1; i<=n; i++)
{
  for(j = i; j<=3*i; j++)
  {
  printf("Robin");
  }
}
```

| `i=1`       | `i=2`        | `i=3`        | `i = n`       |
| ----------- | ------------ | ------------ | ------------- |
| `j = 1,2,3` | `j = 2 to 6` | `j = 3 to 9` | `j = n to 3n` |
| 3-time      | 5-times      | 7times       | (2n+1)times   |
Using Formula : S<sub>n</sub> = `n/2 ( First-Term + Last-term )`
- First-Term = 3
- Lats-Term = (2n+1)
So according to Formula : S<sub>n</sub> = `n/2 (3 + (2n+1))`
- S<sub>n</sub> = `n/2 ( 2n+4 )`
If `n = 2` S<sub>2</sub> = `2/2 ( (2)2 + 4 )`
- S<sub>2</sub> = 8 Times


<font color="#ffc000">Another Example -</font>
```C
for(i = 1; i<=n; i=i*3)
{
  for(j = i; j<=n; j++)
  {
  printf("Robin");
  }
}
```

| `i=`3<sup>0</sup>     | `i=`3<sup>1</sup>     | `i=`3<sup>2</sup>     | `i=`3<sup>3</sup>     | `i=`3<sup>4</sup>     | `i=`3<sup>k</sup>     |
| --------------------- | --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| j = 3<sup>0</sup> - n | j = 3<sup>1</sup> - n | j = 3<sup>2</sup> - n | j = 3<sup>3</sup> - n | j = 3<sup>4</sup> - n | j = 3<sup>k</sup> - n |
| n - 3<sup>0</sup> +1  | n - 3<sup>1</sup> +1  | n - 3<sup>2</sup> +1  | n - 3<sup>3</sup> +1  | n - 3<sup>4</sup> +1  | n - 3<sup>k</sup> +1  |
- (n - 3<sup>0</sup> +1) + (n - 3<sup>1</sup> +1) +(n - 3<sup>2</sup> +1) +(n - 3<sup>3</sup> +1) +(n - 3<sup>4</sup> +1) -----------------------+(n - 3<sup>k</sup> +1)
- (n+1)(k+1) {   -3<sup>0</sup> + -3<sup>1</sup> + -3<sup>2</sup> + -3<sup>3</sup> + -3<sup>4</sup> ------------------+ -3<sup>k</sup> }
-  By using GP Formula : a = 3<sup>0</sup> , r = 3 , Terms = k+1 
- S<sub>Terms</sub> = a ( r<sup>Terms</sup> - a) / ( r  - a )
- S<sub>k+1</sub> = 3<sup>0</sup> ( 3<sup>k+1</sup> - 3<sup>0</sup> ) / 3 - 3<sup>0</sup>
- S<sub>k+1</sub> = 1 ( 3<sup>k+1</sup> - 1 ) / 2
Solving for Value k :
- 3<sup>k</sup> <= n
- taking log both side
- log(3<sup>k</sup>) <= log(n)
- k log(3) <=log(n)
- k = log(n) / log(3)
- k = log<sub>3</sub> (n)

#### <font color="#00b050">Syntax of While ( ) : :</font> 
```C
While(expression / condtion){ //expression is madatory else erro
s1;
s2;
}
// While loop executes again and again until Express not becomes False:
```

```C
int i = 1;
While( ++i < 5 ){
printf("%d",i); //2 3 4
}
```

```C
int i = 1;
While( ++i < 5 );
printf("%d",i); // 5
```
#### <font color="#00b050">Syntax of do_While ( ) : :</font>
```C
Do{
printf("Robin");
} While(0); //It executes atleast 1 times
```

### <font color="#f79646">Jump Statements</font> allows the programmer skip one or all iteration of loops . Jump statements (like `break`, `continue`, `goto`, `return`) in programming languages are used to alter the normal sequential execution flow of a program, effectively transferring control from one part of the code to another.

- `break`: Terminates the loop entirely and transfers control to the statement immediately following the loop.
- `continue`: Skips the current iteration of the loop and proceeds to the next one.
- `goto`: Transfers control to a labeled statement within the same function.
- `return`: Exits a function and returns a value (if defined) to the caller.

#### <font color="#92d050">keywords : : </font>
- Keywords are the reserved words in any programming language, each keywords have there specific meaning and its unchangeable as programmer. we can not use these keyword by there own purpose -
- <font color="#00b0f0">Switch</font> is also one of the Keywords used to create Selection Statement with multiple choices
- Multiple Choices are provided with another keyword <font color="#00b0f0">case :</font>

syntax of Switch :
```C
// switch() selectes an appropriate case by comparing expression and Constant.
Switch(expression){ 
case Constant : //Block of Statement
  break;
case Constant : //Block of Statement
  break;
default : //Block of Code
  break;
}
```

- Break is Optional.
- Expression evaluated to a int value
- position of default does not matter, it can be anywhere
- default is optional
- Duplicate case labels are not allowed
- case label cannot be a variable
- range  => case `low-value  . . .  high-value` (not on all compilers)

if we want to executes same code for some set of values 
```C
Switch(){
Case 1 : 
Case 13 : 
Case 18 : printf("1");
          break;
}
```
### <font color="#ffc000">Garbage Value </font> 
By declaring a Variable we are just label a memory location with that identifier name, and this memory location may already contains some data if the programmer not initialize variable explicitly. then that previously resides data is known as Garbage Value for The variable 


#controlFlowStatement