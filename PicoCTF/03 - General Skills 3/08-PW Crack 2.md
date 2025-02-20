Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

Hints:
1.-Does that encoding look familiar?
2.-The `str_xor` function does not need to be reverse engineered for this challenge.

### Solución
webshell y python
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
--2025-02-20 22:53:03--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                       100%[======================================================================================================>]     914  --.-KB/s    in 0s      

2025-02-20 22:53:03 (912 MB/s) - 'level2.py' saved [914/914]

erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
--2025-02-20 22:53:18--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.71, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                             100%[======================================================================================================>]      31  --.-KB/s    in 0s      

2025-02-20 22:53:18 (12.7 MB/s) - 'level2.flag.txt.enc' saved [31/31]

erik616-picoctf@webshell:~$ mkdir c2
erik616-picoctf@webshell:~$ cp level2.py c2/
erik616-picoctf@webshell:~$ cp level2.flag.txt.enc 
cp: missing destination file operand after 'level2.flag.txt.enc'
Try 'cp --help' for more information.
erik616-picoctf@webshell:~$ cp level2.flag.txt.enc c2/
erik616-picoctf@webshell:~$ nano level2.py
erik616-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
[El archivo level2.py tenia la contraseña en 4 valores hexadecimal]
>>> hex_values = [0x64, 0x65, 0x37, 0x36]
>>> clavesita  = ''.join(chr(value) for value in hex_values)
>>> print(clavesita)
de76
>>> 
KeyboardInterrupt
>>> 
erik616-picoctf@webshell:~$ cd c2/
erik616-picoctf@webshell:~/c2$ chmod +x level2.py
erik616-picoctf@webshell:~/c2$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
erik616-picoctf@webshell:~/c2$ 
```