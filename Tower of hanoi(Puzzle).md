#functonAndStorageClasses
TOH is a kind of puzzle its visually arrangement consist of 3 pillars and `n` number of disks of different sizes -

![[TOH.gif| 300]]

| <center>\|</center>         | <center>\|</center> | <center>\|</center> |     | <center>\|</center> | <center>\|</center> | <center>\|</center>         |
| --------------------------- | ------------------- | ------------------- | --- | ------------------- | ------------------- | --------------------------- |
| <center>--\|--</center>     | <center>\|</center> | <center>\|</center> |     | <center>\|</center> | <center>\|</center> | <center>--\|--</center>     |
| <center>---\|---</center>   | <center>\|</center> | <center>\|</center> |     | <center>\|</center> | <center>\|</center> | <center>---\|---</center>   |
| <center>----\|----</center> | <center>\|</center> | <center>\|</center> |     | <center>\|</center> | <center>\|</center> | <center>----\|----</center> |
| Source                      | Aux                 | Destination         |     | Source              | Aux                 | Destination                 |

What we we have to do with this problem is actually, we need to move all the disks from Source to Destination in such a way -
- We can only put a smaller size disk above large only.
- We can move exactly one disk at a time.

### 🤔Thinking while Solving Recursive Problem :
While solving a Larger Recursive problem, we do always made <font color="#f79646">assumption</font> that, we know the answer of smaller size problem.

<font color="#f79646">How the Recursion is defined ?</font>
Every Recursive call do some work and other work left over the Recursion, we don`t` need to worries about how the recursion will do that. if you worries about recursion you might be get into trouble.

<font color="#f79646">If you want to understand Recursion in coding way ?</font>
Always assume I know the answer of the smaller size of the problem for which we are trying find answer.

Do we know recursion ? 
```C
// Recursion Format
if(){
//smallest value of input for which we can answer directly without Recusion !
}

else{
// Recusrive call
}
```

---

<font color="#f79646">According to Question What is smallest value of input(number of disk ) for which we can answer directly ?</font>
- Number of disk = 1 : Move : Source ---> Destination 
<font color="#f79646">According to Question What is smallest number of work/Unit done that every recursive call do ?</font>
- Every recursive call move one disk 

![[TOH with Recursion.png|300]]

✅ Actual Code -
```C
void TOH(int n, char A, char B, char C){
    if(n ==1){
    printf("%C--->%C\n",A ,C);
    }
    
    else{
    TOH(n-1, A,C,B);
    printf("%C--->%C\n", A, C);
    TOH(n-1,B,A,C);
    }
}

void main(){
int n = 2;
TOH(n,'A','B','C');
}
```