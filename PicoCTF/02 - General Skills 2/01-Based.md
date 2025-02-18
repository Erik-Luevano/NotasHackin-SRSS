To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

Hints:
1.- I hear python can convert things.
2.- It might help to have multiple windows open.
### Solucion 1
CyberChef
```
Cadena 1:
Input: 154 151 155 145
Recipes:
From Binary

Output:
'table'

Cadena 2:
Input: 154 151 155 145
Recipes:
From Octal

Output:
'street'

Cadena 3:
Input: 154 151 155 145
Recipes:
From Hexadecimal

Output:
'socket'

erik616-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
table
Please give the 01110100 01100001 01100010 01101100 01100101 as a word.
...
you have 45 seconds.....

Input:
table
Please give me the  163 164 162 145 145 164 as a word.
Input:
street
Please give me the 736f636b6574 as a word.
Input:
socket
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}

```