Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.

Hints:
1.-To view the file in the webshell, do: `$ nano level1.py`
2.-To exit `nano`, press Ctrl and x and follow the on-screen prompts.
3.-The `str_xor` function does not need to be reverse engineered for this challenge.

### Solución
webshell
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.py
--2025-02-20 22:43:36--  https://artifacts.picoctf.net/c/11/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                       100%[======================================================================================================>]     876  --.-KB/s    in 0s      

2025-02-20 22:43:36 (418 MB/s) - 'level1.py' saved [876/876]

erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
--2025-02-20 22:43:51--  https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.42, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                             100%[======================================================================================================>]      30  --.-KB/s    in 0s      

2025-02-20 22:43:51 (20.2 MB/s) - 'level1.flag.txt.enc' saved [30/30]

erik616-picoctf@webshell:~$ mkdir quePasa
erik616-picoctf@webshell:~$ cp level1.py
cp: missing destination file operand after 'level1.py'
Try 'cp --help' for more information.
erik616-picoctf@webshell:~$ cp level1.py quePasa/
erik616-picoctf@webshell:~$ cp level1.flag.txt.enc 
cp: missing destination file operand after 'level1.flag.txt.enc'
Try 'cp --help' for more information.
erik616-picoctf@webshell:~$ cp level1.flag.txt.enc quePasa/
erik616-picoctf@webshell:~$ cd quePasa/
erik616-picoctf@webshell:~/quePasa$ chmod+x level1.py
-bash: chmod+x: command not found
erik616-picoctf@webshell:~/quePasa$ chmod +x level1.py
erik616-picoctf@webshell:~/quePasa$ nano level1.py
[En codigo se ve la contraseña en un if: 1e1a]
erik616-picoctf@webshell:~/quePasa$ python3 level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
erik616-picoctf@webshell:~/quePasa$ 
```