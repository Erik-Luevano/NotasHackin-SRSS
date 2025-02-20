Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

Hints:
1.- If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
2.- To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
3.- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
4.- Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 runme.py` You should have the flag now!

### Solución
python
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2025-02-20 21:54:04--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.93, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                        100%[======================================================================================================>]     270  --.-KB/s    in 0s      

2025-02-20 21:54:04 (93.2 MB/s) - 'runme.py' saved [270/270]

erik616-picoctf@webshell:~$ ls -la
total 7100
drwxr-xr-x   5 erik616-picoctf erik616-picoctf    4096 Feb 20 21:54 .
drwxr-xr-x   3 root            root                 29 Feb 13 18:05 ..
-rw-------   1 erik616-picoctf erik616-picoctf    1068 Feb 18 23:06 .bash_history
-rw-r--r--   1 erik616-picoctf erik616-picoctf     220 Feb 13 18:05 .bash_logout
-rw-r--r--   1 erik616-picoctf erik616-picoctf    3771 Feb 13 18:05 .bashrc
-rw-r--r--   1 erik616-picoctf erik616-picoctf     807 Feb 13 18:05 .profile
-rw-------   1 erik616-picoctf erik616-picoctf    1169 Feb 14 00:16 .python_history
drwx------   2 erik616-picoctf erik616-picoctf      48 Feb 20 21:49 .ssh
-rw-rw-r--   1 erik616-picoctf erik616-picoctf     167 Feb 18 21:45 .wget-hsts
-rw-r--r--   1 root            root               4443 Feb 20 21:42 README.txt
drwxrwxr-x 121 erik616-picoctf erik616-picoctf   28672 May  3  2020 big-zip-files
-rw-rw-r--   1 erik616-picoctf erik616-picoctf 3182988 Aug  4  2023 big-zip-files.zip
drwxrwxr-x   5 erik616-picoctf erik616-picoctf     124 May 13  2022 files
-rw-rw-r--   1 erik616-picoctf erik616-picoctf 3995553 Aug  4  2023 files.zip
-rw-rw-r--   1 erik616-picoctf erik616-picoctf     270 Mar 16  2023 runme.py
erik616-picoctf@webshell:~$ chmod +x runme.py
erik616-picoctf@webshell:~$ python3 runme.py
picoCTF{run_s4n1ty_run}
erik616-picoctf@webshell:~$ 
```