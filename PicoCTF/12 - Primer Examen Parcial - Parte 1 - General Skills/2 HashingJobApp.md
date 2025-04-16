If you want to hash with the best, beat this test!`nc saturn.picoctf.net 51900`

Hints:
1.-You can use a commandline tool or web app to hash text
2.-Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

### Solucion

```
Cyberchef

El reto va de transformar la cadena a md5 hash cosa que podemos lograr con Cyberchef, nos pide algunas transformaciones y suelta la flag:

erik616-picoctf@webshell:~$ nc saturn.picoctf.net 51900
Please md5 hash the text between quotes, excluding the quotes: 'Keanu Reeves'
Answer: 
Time's up. Press Ctrl-C to disconnect. Feel free to reconnect and try again.
^C
erik616-picoctf@webshell:~$ nc saturn.picoctf.net 51900
Please md5 hash the text between quotes, excluding the quotes: 'a treehouse'
Answer: 
98b0ee4dfd8e04322c60bd32481b512e
98b0ee4dfd8e04322c60bd32481b512e
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'school cafeteria'
Answer: 
3e06bd96dca5d429a2e06b3ea613eb41
3e06bd96dca5d429a2e06b3ea613eb41
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Japan'
Answer: 
53a577bb3bc587b0c28ab808390f1c9b
53a577bb3bc587b0c28ab808390f1c9b
Correct.

Flag: picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
```