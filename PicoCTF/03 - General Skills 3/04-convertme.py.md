Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

Hints:
1.-Look up a decimal to binary number conversion app on the web or use your computer's calculator!
2.-The `str_xor` function does not need to be reverse engineered for this challenge.
3.-If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
4.-To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
5.-Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
6.- Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

### Solcuión
python
```
Para convertir un numero decimal a binario base 2 dividimos sobre 2 y vamos ponendo 1 o 0 segun si hay residuo:
- 17 ÷ 2 = 8,  1
- 8 ÷ 2 = 4,  0
- 4 ÷ 2 = 2,  0
- 2 ÷ 2 = 1,  0
- 1 ÷ 2 = 0,  1
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2025-02-20 22:19:50--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                    100%[======================================================================================================>]   1.16K  --.-KB/s    in 0s      

2025-02-20 22:19:50 (88.2 MB/s) - 'convertme.py' saved [1189/1189]

erik616-picoctf@webshell:~$ ls -la
total 36
drwxr-xr-x 3 erik616-picoctf erik616-picoctf  169 Feb 20 22:19 .
drwxr-xr-x 3 root            root              29 Feb 13 18:05 ..
-rw------- 1 erik616-picoctf erik616-picoctf 1234 Feb 20 22:11 .bash_history
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  220 Feb 13 18:05 .bash_logout
-rw-r--r-- 1 erik616-picoctf erik616-picoctf 3771 Feb 13 18:05 .bashrc
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  807 Feb 13 18:05 .profile
-rw------- 1 erik616-picoctf erik616-picoctf 1169 Feb 20 22:13 .python_history
drwx------ 2 erik616-picoctf erik616-picoctf   48 Feb 20 21:49 .ssh
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf  167 Feb 18 21:45 .wget-hsts
-rw-r--r-- 1 root            root            4443 Feb 20 22:13 README.txt
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 1189 Mar 16  2023 convertme.py
erik616-picoctf@webshell:~$ chmod +x convertme.py 
erik616-picoctf@webshell:~$ python3 convertme.py 
If 17 is in decimal base, what is it in binary base?
Answer: 10001
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
erik616-picoctf@webshell:~$ 
```