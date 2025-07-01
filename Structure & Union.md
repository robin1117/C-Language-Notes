#user_define_datatype

Suppose you are making a software for any organization it may be a school, this suggested that your software should have information related to the <font color="#00b0f0">Students</font>, <font color="#00b0f0">Teachers</font> like -
- Students : <font color="#c3d69b">Age</font>, <font color="#c3d69b">Name</font>, <font color="#c3d69b">Gender</font>, <font color="#c3d69b">Class</font>, <font color="#c3d69b">Fathers_Name</font> etc -
- If we define all these in variables it will be hectic for us, for manipulating and updating -
- Even in C there is no such data type using which we can represent the Student -

Here comes to use the concept of Structure and Union -
- Basically C provides a feature using which we can make our own Custom Datatype.

Let`s` see how this Work -
- `struct` is the keyword used to create user define datatype.

Template Blueprint of structure -
```C
struct Student {
	int Roll;
	char name[20];
}; //This syntax is for compiler this does`t lead to any memory allocation but the memory is allocated when the variable that data type is created.
```
- Structure is a group of heterogeneous type of data element : means this can group variable of any datatype.
- Memory is created only when we declare variable of any datatype.


<font color="#fbd5b5">Example</font>
```C
struct Student {
	int Roll;
	char name[20];
}

void main(){
struct Student s1,s2;
s1.Roll = 10;
s2.Roll = 20;
s1.name = 'Robin'; //❌invalid, array name not in left side of assignment 
Strcpy(s1.name,"Robin");
}
```

<font color="#fbd5b5">Example</font>
```C
struct Student {
	int Roll;
	char name[20] = "Robin";//❌Invalid, not memory is allocated 
}
```

<font color="#fbd5b5">Example</font>
```C
//Tag(name) of structure is optional ❗
struct {
	int Roll;
	char name[20];
},s1,s2,s3 //varibales

void main(){
|
|
|
}
```

<font color="#fbd5b5">Example</font>
```C
typedef struct Student {
	int Roll;
	char name[20];
}Robin;

void main(){
Robin s1,s2; //varibale of robin datatpe
}
```

<font color="#fbd5b5">Example</font>
```C
struct Student {
	int Roll;
	char name[20];
}

void main(){
struct student s = {10, "Robin"};✅ //as soon variable declared we can initialized it  immediately
struct student s1 = {"Robin"};❌ // order should be same as in structure
struct student s2 = {10};✅ 

}
```

- 🥲Just like array element, Structure elements also gets store one after other in memory - but there is something called as <font color="#00b050">Padding / Alignment restriction.</font>(HomeWork)
- 🫢Array name is address But Structure name is not address

❗If we not initialize values to structure variables then by default all bits gets initialize with zeros 
- int  = 0
- float =0.0
- char = null ( for the character zero value means null whose ASCII (0) )

#### Structure name not represent address like Arrays.
This means it treated as variable and if we pass it to the function it will be as <font color="#e36c09">call by value</font>.

<font color="#8064a2">Structure as Pass by Value -</font>
```C
struct stu{
int Roll;
char name[20];
};
void display(struct stu);

void main(){
struct stu s;
scanf("%d",&s.Roll);//20
scanf("%s",&s.name);//Robin
display(s);
}

void display(struct stu t){
printf("%d",t.Roll);
printf("%s",t.name);


```

<font color="#8064a2">Structure as Pass by reference -</font>
```C
struct stu{
int Roll;
char name[20];
};
void display(struct stu*);

void main(){
struct stu s;
scanf("%d",&s.Roll);//20
scanf("%s",&s.name);//Robin
display(&s);
}

void display(struct stu* t){ //t holds the address of structur s
printf("%d",(*t).Roll);
printf("%s",t->name); //arrow operator only work with (pointer to structure)
}
```

#### Nested Structure !

<font color="#8064a2">Example -</font>
```C
struct date_of_birth{
int day;
int month;
int years;
};

struct stu{
int Roll;
char name[20];
struct date_of_birth DOB;
};

void main(){
struct stu s;
s.Roll = 10
strcpy(s.name,"Robin");
s.DOB.day = 2;
s.DOB.month = 3;
s.DOB.years = 1982;
}
```