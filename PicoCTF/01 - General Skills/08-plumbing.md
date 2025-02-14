Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.

Hints:
1.- Remember the flag format is picoCTF{XXXX}
2.- What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solucion 1
```
erik616-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 > datos 
^C
erik616-picoctf@webshell:~$ ls
README.txt  datos  file  file.1  flag
erik616-picoctf@webshell:~$ cat datos | grep pico
picoCTF{digital_plumb3r_ea8bfec7}
erik616-picoctf@webshell:~$ 
erik616-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep pico        
picoCTF{digital_plumb3r_ea8bfec7}
```
