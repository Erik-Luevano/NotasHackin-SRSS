Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)

Hints:
1.-  Can grep be instructed to look at every file in a directory and its subdirectories?

### Solución
Shell
```
erik616-picoctf@webshell:~$ ls -la
total 3192
drwxr-xr-x   4 erik616-picoctf erik616-picoctf    4096 Feb 18 23:24 .
drwxr-xr-x   3 root            root                 29 Feb 13 18:05 ..
-rw-------   1 erik616-picoctf erik616-picoctf    1068 Feb 18 23:06 .bash_history
-rw-r--r--   1 erik616-picoctf erik616-picoctf     220 Feb 13 18:05 .bash_logout
-rw-r--r--   1 erik616-picoctf erik616-picoctf    3771 Feb 13 18:05 .bashrc
-rw-r--r--   1 erik616-picoctf erik616-picoctf     807 Feb 13 18:05 .profile
-rw-------   1 erik616-picoctf erik616-picoctf    1169 Feb 14 00:16 .python_history
drwx------   2 erik616-picoctf erik616-picoctf      48 Feb 18 22:58 .ssh
-rw-rw-r--   1 erik616-picoctf erik616-picoctf     167 Feb 18 21:45 .wget-hsts
-rw-r--r--   1 root            root               4443 Feb 18 23:17 README.txt
drwxrwxr-x 121 erik616-picoctf erik616-picoctf   28672 May  3  2020 big-zip-files
-rw-rw-r--   1 erik616-picoctf erik616-picoctf 3182988 Aug  4  2023 big-zip-files.zip
erik616-picoctf@webshell:~$ ls
README.txt  big-zip-files  big-zip-files.zip  hola
erik616-picoctf@webshell:~$ grep -r "palabra" carpeta/
grep: carpeta/: No such file or directory
erik616-picoctf@webshell:~$ grep -r "PicoCTF{" big-zip-files/
erik616-picoctf@webshell:~$ grep -r "picoCTF{" big-zip-files/
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
erik616-picoctf@webshell:~$
```