Based on the Declaration we have different types of pointer in C language let`s` discuss each one by one !

#### Void Pointer -
If we declare pointer without providing extra knowledge ok Data type by just appending void like this `void *p`;

```C
void *p;
int a = 10;
p = &a;
```

The initialization of void pointer does`t` lead to any kind of error,
But the error too when we are trying to access or dereference the value from that address, because compiler need to know how many bits need to fetch , which is possible only with provided datatype.

```C
printf("%d",*p); //❌Error
```

But we can provide Data-Type information by Typecasting -

```C
printf("%d",*(int *)p);//✅ this works without error
```

- void pointer cannot dereference directly as like other pointers
- Don`t` perform any Arithmetic operation void pointer this may lead to error 

#### Wild Pointer -
These are uninitialized pointers or we can say Dangerous pointers too. because we don`t`  know to whom this pointer pointes in memory . So if we write `p*` in program, we may unintentionally change something that should not. 

#### Dangling Pointer -
If a function returns an address of local variable whose scope with in its block only, that variable can`t` be accessible any more after activation record of function is vanished even function return its address, function vanished everything inside with his activation record

```C
int * fun(){
int a = 10; //Vanished with this function
return &a;
}

void main(){
int *p;
p = fun(); //behaviour is undefine
}
```

- `Static int a = 10` its life throughout the program this is valid and works well !
- These variable stored in Data Segment of memory.

#### Null Pointer -
A valid pointer can contains only unsigned int type.
NULL pointer is specially designed pointer to differentiate from all valid pointers.

- We can also implement NULL pointer with `-ve`  `int *p = -100` ;
- But Denise ritchie implemented NULL pointer with Zero (0).
- Because OS occupies some of the initial level memory for its own and takes the guarantee not assigned this address to anyone. that`s` why NULL pointer implemented with Zeros.
- Another reason is 0 is represented FALSE in C- Language -
```C
int *p = (int*)0; //{p=NULL}
```

#Arrays_Pointer