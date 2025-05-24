- Guys on our Output screen where we get output of our program ,you definitely saw a cursor blinking over there also , its look like CMD black screen !
- Basically this Black Screen have 80 Columns and 25 Rows 
- And these 80 Columns are divided into 5 Frames 
- Means Single Frame Contains 8 Column

After knowing all these knowledge now its time to understand How the<font color="#fac08f"> format Specifier</font> `\t` works !
- Every time in C language when you try to executes `Printf("\t")` , it will throw the Curser in next Frame

| \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| |
| -------------------------- | -------------------------- | -------------------------- | -------------------------- | -------------------------- |

```C
printf("Hello\th")
```

| \|H\|e\|l\|l\|o\| \| \| \| | \|h\| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| | \| \| \| \| \| \| \| \| \| |
| -------------------------- | -------------------------- | -------------------------- | -------------------------- | -------------------------- |
|                            | Curser here                |                            |                            |                            |

#controlFlowStatement