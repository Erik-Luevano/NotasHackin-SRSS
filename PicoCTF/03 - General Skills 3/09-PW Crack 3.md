Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

Hints:
1.-To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2.-To exit `bvi` type `:q` and press enter.
3.-The `str_xor` function does not need to be reverse engineered for this challenge.

### Solcuión
webshell

```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
--2025-02-20 23:02:44--  https://artifacts.picoctf.net/c/16/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.93, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                       100%[======================================================================================================>]   1.31K  --.-KB/s    in 0s      

2025-02-20 23:02:45 (556 MB/s) - 'level3.py' saved [1337/1337]

erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
--2025-02-20 23:02:59--  https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.71, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                             100%[======================================================================================================>]      31  --.-KB/s    in 0s      

2025-02-20 23:03:00 (31.2 MB/s) - 'level3.flag.txt.enc' saved [31/31]

erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
--2025-02-20 23:03:20--  https://artifacts.picoctf.net/c/16/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.71, 3.160.5.93, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                 100%[======================================================================================================>]      16  --.-KB/s    in 0s      

2025-02-20 23:03:20 (16.8 MB/s) - 'level3.hash.bin' saved [16/16]

erik616-picoctf@webshell:~$ mkdir lv3
erik616-picoctf@webshell:~$ cp l
level3.flag.txt.enc  level3.hash.bin      level3.py            lv3/                 
erik616-picoctf@webshell:~$ cp level3.py
cp: missing destination file operand after 'level3.py'
Try 'cp --help' for more information.
erik616-picoctf@webshell:~$ cp level3.py lv3/
erik616-picoctf@webshell:~$ cp level3.flag.txt.enc lv3/
erik616-picoctf@webshell:~$ cp level3.hash.bin lv3/
erik616-picoctf@webshell:~$ cat level3.py
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

erik616-picoctf@webshell:~$ cat level3.hash.bin 
1o[>(.erik616-picoctf@webshell:~$ cat level3.flag.txt.enc 
H_V
gPYTVQ
      _Herik616-picoctf@webshell:~$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
erik616-picoctf@webshell:~$ nano level3.py
erik616-picoctf@webshell:~$ chmod +x level3.py
erik616-picoctf@webshell:~$ python3 level3.py 
b'\x1b\x18\xe11o\x92\x18\xcc[\x05>\x1c\xea(\xe0.'
Please enter correct password for flag: nose    
That password is incorrect
erik616-picoctf@webshell:~$ nano level3.py
erik616-picoctf@webshell:~$ nano level3.py
erik616-picoctf@webshell:~$ nano level3.py
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: Claro
[No pude encontrarla viendo el hash o codigo, asi que intente con las 7 contraseñas]
Welcome back... your flag, user:

37x!'mCa"6:0vdfugBkesi

erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 6997
Welcome back... your flag, user:
~fo=M[J)c;9:Qi`c`h=<iP>0>8>37?q
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 3ac8
Welcome back... your flag, user:
{>52H&fcc5T1:le0g3d?;`d<2g+
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: f0ac
Welcome back... your flag, user:
.o7iR}32an`870aeh9Yfdn1fgg6)
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 4b17
Welcome back... your flag, user:
|=g=OB)a`1:S2hcb35<k
                    60<c635dy
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: ec27
Welcome back... your flag, user:
-<d=A)0a2:3kc326<:
50mb53dez
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 4e66
Welcome back... your flag, user:
|:`<OE(ag6;S5obb42=k
                    11<d125c~
erik616-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
erik616-picoctf@webshell:~$ 
```