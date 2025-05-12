Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: dds1-alpine.flag.img.gz

Hints:
1.-Have you ever used `file` to determine what a file was?
2.-Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85
3.-Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48
4.-Using your own computer, you could use qemu to boot from this disk!

### Solución

```
descargamos el archivo y descomprimimos, luego utilizamos srch_strings:

(erik㉿kali)-[~/Documentos/PicoCTF/diskdisk]
└─$ wget https://mercury.picoctf.net/static/2f998eee12730cf5766624681212a441/dds1-alpine.flag.img.gz
--2025-05-12 11:40:52--  https://mercury.picoctf.net/static/2f998eee12730cf5766624681212a441/dds1-alpine.flag.img.gz
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 29768911 (28M) [application/octet-stream]
Grabando a: «dds1-alpine.flag.img.gz»

dds1-alpine.flag.img.gz   100%[===================================>]  28.39M  1.67MB/s    en 17s     

2025-05-12 11:41:09 (1.68 MB/s) - «dds1-alpine.flag.img.gz» guardado [29768911/29768911]

                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/diskdisk]
└─$ gzip -d dds1-alpine.flag.img.gz 
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/diskdisk]
└─$ srch_strings dds1-alpine.flag.img | grep "pico"
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_267e38f6}
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/diskdisk]

y nos da la flag al filtrar por pico: picoCTF{f0r3ns1c4t0r_n30phyt3_267e38f6}

```