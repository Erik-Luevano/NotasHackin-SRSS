There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 22902`, but it doesn't speak English...

Hints:
1.- You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2.- You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)
## Solucion
Python
```
erik616-picoctf@webshell:~$ nc mercury.picoctf.net 22902
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
100 
51 
100 
102 
100 
54 
100 
102 
125 
10 
erik616-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> entrada = """112
... 105
... 99
... 111
... 67
... 84
... 70
... 123
... 103
... 48
... 48
... 100
... 95
... 107
... 49
... 116
... 116
... 121
... 33
... 95
... 110
... 49
... 99
... 51
... 95
... 107
... 49
... 116
... 116
... 121
... 33
... 95
... 100
... 51
... 100
... 102
... 100
... 54
... 100
... 102
... 125
... 10"""
>>> resultado = ''.join([chr(int(numero)) for numero in entrada.splitlines()])
>>> print(resultado)
picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}

```
