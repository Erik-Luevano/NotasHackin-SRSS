Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)

Hints:
1.- Indentation is very meaningful in Python
2.- To view the file in the webshell, do: `$ nano fixme1.py`
3.- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4.- The `str_xor` function does not need to be reverse engineered for this challenge.

### Solución
webshell
```
erik616-picoctf@webshell:~$ nano fixme1.py 
[Se soluciona un pequeño error de indentación]
erik616-picoctf@webshell:~$ ls -la
total 36
drwxr-xr-x 4 erik616-picoctf erik616-picoctf  180 Feb 20 22:31 .
drwxr-xr-x 3 root            root              29 Feb 13 18:05 ..
-rw------- 1 erik616-picoctf erik616-picoctf 1234 Feb 20 22:11 .bash_history
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  220 Feb 13 18:05 .bash_logout
-rw-r--r-- 1 erik616-picoctf erik616-picoctf 3771 Feb 13 18:05 .bashrc
drwxrwxr-x 3 erik616-picoctf erik616-picoctf   19 Feb 20 22:29 .local
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  807 Feb 13 18:05 .profile
-rw------- 1 erik616-picoctf erik616-picoctf 1169 Feb 20 22:13 .python_history
drwx------ 2 erik616-picoctf erik616-picoctf   48 Feb 20 21:49 .ssh
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf  167 Feb 18 21:45 .wget-hsts
-rw-r--r-- 1 root            root            4443 Feb 20 22:13 README.txt
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf  835 Feb 20 22:31 fixme1.py
erik616-picoctf@webshell:~$ chmod +x fixme1.py 
erik616-picoctf@webshell:~$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
```