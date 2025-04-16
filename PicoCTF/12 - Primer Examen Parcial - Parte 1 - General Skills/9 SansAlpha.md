The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 63996 ctf-player@mimas.picoctf.net`Use password: `f3b61b38`

Hints:
1.-Where can you get some letters?

### Solucion

```
La manera de solucionar este reto fue que como no se podian usar letras seria ir adivinando con comodines, se descubrio que esta el carpeta bin con el comando base 32 y con mas comodines adivinar el resto al igual que primero se verifico que si estaba una flag.txt
Con esta variable _1='/???/????32 2>&1' luego pudimos encontrar la cadena en base 32 que luego deciframos en una pagina
:
SansAlpha$ ls
SansAlpha: Unknown character detected
SansAlpha$ ??????/*
bash: blargh/flag.txt: Permission denied

SansAlpha$ /?
bash: /?: No such file or directory

SansAlpha$ /??
bash: /??: No such file or directory

SansAlpha$ /???
bash: /bin: Is a directory

SansAlpha$ /???/?
/bin/[: missing ']'

SansAlpha$ /???/??

──(erik㉿kali)-[~]
└─$ ssh -p 63996 ctf-player@mimas.picoctf.net
ctf-player@mimas.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Wed Apr 16 00:42:20 2025 from 127.0.0.1
SansAlpha$ ???/????32
bash: ???/????32: No such file or directory

SansAlpha$ /???/????32
/bin/base32: read error: Is a directory

SansAlpha$ _1='/???/????32 2>&1'
SansAlpha$ ${_1}
/bin/base32: extra operand '/usr/libx32'
Try '/bin/base32 --help' for more information.

SansAlpha$ ${_1:0:11} ??????/*
/bin/base32: extra operand '/usr/libx32'
Try '/bin/base32 --help' for more information.

SansAlpha$ ${_1:0:11} ??????/????.???
/bin/base32: extra operand '/usr/libx32'
Try '/bin/base32 --help' for more information.

SansAlpha$ ${_1:0:11} ??????/????.???
/bin/base32: extra operand '/usr/libx32'
Try '/bin/base32 --help' for more information.

SansAlpha$ _1=`/???/????32 2>&1`
SansAlpha$ ${_1}
bash: /bin/base32:: No such file or directory

SansAlpha$ ${_1:0:11} ??????/*
/bin/base32: extra operand 'blargh/flag.txt'
Try '/bin/base32 --help' for more information.

SansAlpha$ ${_1:0:11} ??????/????.???
OJSXI5LSNYQDAIDQNFRW6Q2UIZ5TO2BRGVPW25JRG4YXMM3SGUZV6MJVL5WTIZDOGM2TKXZWGQYG
ENTBMRSH2===

Flag decodificada:
picoCTF{7h15_mu171v3r53_15_m4dn355_640b6add}

```