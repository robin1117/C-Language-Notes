In this section we were gone take brief overview how do the computer understand  `-ve`  Numbers, by the way this is the Part of Digital Logic -
One thing you have to keep it in mind that computer only understand in `0` and `1`s -

✅According to <font color="#92cddc">Signed Magnitude</font>(One of the formats for storing numbers in computers)
- `1 bit` is reserved for Signed bit
- `other bits` are reserved for magnitude

let`s` take Example `17` and `-17` 
How do we store this in `8bits` Look below -

| Signed bit | Magnitude | Decimal |
| ---------- | --------- | ------- |
| 1          | 0010001   | `-17`   |
| 0          | 0010001   | `+17`   |

<font color="#f79646">Main Disadvantage with this format is -</font>
- Unintentionally we get two representation of Zeros `+0` `-0`
- 00000000 => `+0`
- 10000000 => `-0` 

<font color="#f79646">To solve this Ambiguity we used 2s Complement Formate- </font>
- `+ve` no stored as its -
- `-ve` no stored in 2s complementation form -

Now how we can represent `17` and `-17` -
- `+17` - 00001011
- `-17` - (00001011)  -<font color="#ffff00">2s-Complement</font>-> (11110101)

<font color="#ffc000">If a Number is written in 2s complement form there are two way to get the number-</font>
- `11110101` - 
     - Either we do again 2s complement and gets value by appending `-ve`.
     - `(0001011)` --> `-11`
     - Or we have Direct Method to get the value by concentrating on Zero and `1` which we added after `1s` Complement. 
     - `11110101` --> 2<sup>3</sup> -2<sup>2</sup>  -1 = -11

#Arrays_Pointer 