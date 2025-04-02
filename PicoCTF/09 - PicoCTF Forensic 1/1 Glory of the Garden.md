This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

Hints:
1.-What is a hex editor?

### Solucion

```
Primero descargamos el archivo con wget:
──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/GloryoftheGarden]
└─$ wget https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg    
--2025-04-02 18:30:12--  https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg.1’

garden.jpg.1                              100%[===================================================================================>]   2.19M  1.97MB/s    in 1.1s    

2025-04-02 18:30:14 (1.97 MB/s) - ‘garden.jpg’ saved [2295192/2295192]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/GloryoftheGarden]
└─$ 

Como es una imagen, podemos ver los strings de ella con "strings" y ayuda de grep podemos verificar si esta la flag:
─(kali㉿kali)-[~/Documents/PicoCTF/Forensic/GloryoftheGarden]
└─$ strings -n 13 garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"


```