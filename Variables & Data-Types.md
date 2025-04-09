### <font color="#92d050">Variables-Identifier</font>
Variable is anything which <font color="#ffff00">being able to vary</font>(change), In this world we have two kind of data one is Constant(can not changes with time) & other Variable(can be changed with time)

---
- Let`s` take real life Example ~ <font color="#f79646">In your day to day life you might be  notice that Based on the type of container, we usually store things according to that in it,</font> <font color="#c3d69b">we cannot store milk in cylinder </font>
- <font color="#f79646">Same way Variables is just like container for storing data values, there are different types of variables, based on that only it hold data in it,</font> <font color="#c3d69b">variable of type int(5) can`t store float(5.2) type data</font>
---
- In Computer When you store data in a memory location using a variable, <font color="#92d050">you can access that data later by using the variable's identifier (name)</font>, which essentially acts as a <font color="#f79646">label</font> to retrieve the value stored at that memory location, without needing to know the exact memory address directly
---
### <font color="#92d050">Data-Type</font>
- <font color="#ffff00">That Thing is OK !</font> we have <font color="#c3d69b">different types of variable</font> for storing <font color="#c3d69b">different types of data,</font> **But the Question is How do the Computer know about type of variable, for processing data computer should know about the variables what types of data they hold.** ?
- So there must be a facility of *Data-Types* in Programming Language : -
- Here comes the concept `Data-Type` which we mention before <font color="#ffff00">variable name</font>, So that computer interprets what type of data that particular Variable is holded.

```C
a = 5; //That`s not enough ❌
int a = 5; //We have to use Data-type with variable
```

Till now what we Come to know, overall we have to tell to the compiler about Data-Type 
with Variable name.

--- 

In C-Language We classify Data-Types Mainly in 3-Catogries : -
- Primitive
- Derived
- User-Define

| <font color="#92d050">Primitive</font> | <font color="#92d050">Derived</font> | <font color="#92d050">User-Define</font> |
| -------------------------------------- | ------------------------------------ | ---------------------------------------- |
| int                                    | array                                | user-define                              |
| float                                  | pointer                              | structure                                |
| char                                   | string                               | enum                                     |
| Void & other                           | -                                    | typedef                                  |
Firstly we will discuss about [[Primitive Data-Type]]

#DataType_Operators