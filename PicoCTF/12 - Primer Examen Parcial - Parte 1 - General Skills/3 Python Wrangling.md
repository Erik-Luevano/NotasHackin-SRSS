Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py) using [this password](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt) to get [the flag](https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en)?

Hints:
1.- Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py`

2.- $ man python

### Solucion

```
Nos dan 3 archivos a descargar un codigo de python un documento donde esta presuntamente la flag y una contraseña, consid¿ste en correr el programa de python con el parametro -d en archivo de flag y utilizar la contraseña proporcionada:

erik616-picoctf@webshell:~$ ls                     
README.txt  ende.py  flag.txt.en  pw.txt
erik616-picoctf@webshell:~$ python3 ende.py -d flag.txt.en
Please enter the password:^CTraceback (most recent call last):
  File "/home/erik616-picoctf/ende.py", line 39, in <module>
    sim_sala_bim = input("Please enter the password:")
KeyboardInterrupt

erik616-picoctf@webshell:~$ cat pw.txt 
68f88f9368f88f9368f88f9368f88f93
erik616-picoctf@webshell:~$ python3 ende.py -d flag.txt.en
Please enter the password:68f88f9368f88f9368f88f9368f88f93

picoCTF{4p0110_1n_7h3_h0us3_68f88f93}
 

```
