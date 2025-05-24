We know that in <font color="#fac08f">char</font> type variable we can store one character at a time, it can be of any symbol like - `@`,`#`,`$`  etc

we come to in biggest confusion, when you notice Range of <font color="#fac08f">char data-type</font> . actually 1 Byte <font color="#fac08f">char</font> can hold single symbol then how the range of char is possible , I mean how range is possible here ? because its just hold a symbol not any integer !
- `sign char` - 1Bytes = 8bit
- `unsigned char` - 1Bytes = 8bit
- <font color="#ff0b0f1">Range Unsigned char</font> = 0----to---2<sup>8</sup>-1 === (0-----255)
- <font color="#ff0b0f1">Range Signed char</font> = -2<sup>8-1</sup>---to---2<sup>8-1</sup>-1 === (-128---to---127)

==Here comes the concept of Character System : :==
According to the Character System any Symbol like `A`,`*`,`&`  in this world , it can be of any other language,  can be representable in form of `+ve`integer number.
ASCII-CS is one of the Character system for English type language that defines the integer code for the corresponding Symbols.
Refer This To Know More About- [ASCII Table](https://www.cs.cmu.edu/~pattis/15-1XX/common/handouts/ascii.html)

#DataType_Operators