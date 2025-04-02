This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

Hints:
1.-How do operating systems know what kind of file it is? (It's not just the ending!
2.-Make sure to submit the flag as picoCTF{XXXXX}

### Solucion

```
Descarganmos el archivo con wget:
(kali㉿kali)-[~/Documents/PicoCTF/Forensic/extensions]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt    
--2025-04-02 18:56:01--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                                  100%[===================================================================================>]   9.75K  --.-KB/s    in 0s      

2025-04-02 18:56:01 (165 MB/s) - ‘flag.txt’ saved [9984/9984]

Vemos con un cat sencillo que tiene PNG hasta arriba y tambien con xxd vemos que los numeros coinciden con los de un PNG, asi que cambiamos la extencion y intentamos abrir:
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/extensions]
└─$ mv flag.txt flag.png  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/extensions]
└─$ open flag.png 

efectivamente es una imagen con la flag:
picoCTF{now_you_know_about_extensions}
```