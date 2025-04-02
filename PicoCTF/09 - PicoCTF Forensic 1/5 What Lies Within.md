There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

Hints:
1.-There is data encoded somewhere... there might be an online decoder.

### Solucion

```
Descargamos con wget:
──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/whatlieswithin]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2025-04-02 19:05:24--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                             100%[===================================================================================>] 610.57K  1019KB/s    in 0.6s    

2025-04-02 19:05:26 (1019 KB/s) - ‘buildings.png’ saved [625219/625219]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/whatlieswithin]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/whatlieswithin]
└─$ open buildings.png 

Vemos que es una imagen de una capilla, con ayuda de: http://stylesuxx.github.io/steganography/

que es una pagina para checar si exiten mensajes ocultos en las imagenes podemos ver que encontramos:
picoCTF{h1d1ng_1n_th3_b1t5}
```