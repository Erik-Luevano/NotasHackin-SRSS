Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)
Hints:
1.-On the webshell, use `ls` to see if both files are in the directory you are in
2.-The `str_xor` function does not need to be reverse engineered for this challenge.

### Solución
python
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/code.py
--2025-02-20 22:13:26--  https://artifacts.picoctf.net/c/2/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.71, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                         100%[======================================================================================================>]   1.25K  --.-KB/s    in 0s      

2025-02-20 22:13:26 (591 MB/s) - 'code.py' saved [1278/1278]

erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/codebook.txt
--2025-02-20 22:13:41--  https://artifacts.picoctf.net/c/2/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.71, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                    100%[======================================================================================================>]      27  --.-KB/s    in 0s      

2025-02-20 22:13:41 (10.8 MB/s) - 'codebook.txt' saved [27/27]

erik616-picoctf@webshell:~$ mkdir Hola
erik616-picoctf@webshell:~$ ls -la 
total 44
drwxr-xr-x 4 erik616-picoctf erik616-picoctf 4096 Feb 20 22:14 .
drwxr-xr-x 3 root            root              29 Feb 13 18:05 ..
-rw------- 1 erik616-picoctf erik616-picoctf 1234 Feb 20 22:11 .bash_history
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  220 Feb 13 18:05 .bash_logout
-rw-r--r-- 1 erik616-picoctf erik616-picoctf 3771 Feb 13 18:05 .bashrc
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  807 Feb 13 18:05 .profile
-rw------- 1 erik616-picoctf erik616-picoctf 1169 Feb 20 22:13 .python_history
drwx------ 2 erik616-picoctf erik616-picoctf   48 Feb 20 21:49 .ssh
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf  167 Feb 18 21:45 .wget-hsts
drwxrwxr-x 2 erik616-picoctf erik616-picoctf    6 Feb 20 22:14 Hola
-rw-r--r-- 1 root            root            4443 Feb 20 22:13 README.txt
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 1278 Mar 16  2023 code.py
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf   27 Mar 16  2023 codebook.txt
erik616-picoctf@webshell:~$ cp code.py Hola/
erik616-picoctf@webshell:~$ cd codebook.txt Hola/
-bash: cd: too many arguments
erik616-picoctf@webshell:~$ cp codebook.txt Hola/
erik616-picoctf@webshell:~$ cd Hola/
erik616-picoctf@webshell:~/Hola$ ls -la
total 12
drwxrwxr-x 2 erik616-picoctf erik616-picoctf   41 Feb 20 22:15 .
drwxr-xr-x 4 erik616-picoctf erik616-picoctf 4096 Feb 20 22:14 ..
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 1278 Feb 20 22:15 code.py
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf   27 Feb 20 22:15 codebook.txt
erik616-picoctf@webshell:~/Hola$ chmod +x code.py
erik616-picoctf@webshell:~/Hola$ python3 code.py 
picoCTF{c0d3b00k_455157_7d102d7a}
erik616-picoctf@webshell:~/Hola$ 
```