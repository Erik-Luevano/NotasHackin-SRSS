Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download compressed disk image

### Solución

```
Descargamos el archivo y analizamos particiones con mmls:
┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ gzip -d disk.flag.img.gz 
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
                     
Despues utilizamos fls para listar los archivos o directorios en una particion 
especifica se usa -o para indicar el offset del inicio de la particion

┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ fls disk.flag.img -o 0000360448 | grep flag
                                       
indicamos -r al,no ver nada para hacer una busqueda recursiva
                                       
┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ fls disk.flag.img -o 0000360448 -r | grep flag
++ r/r * 2082(realloc):	flag.txt
++ r/r 2371:	flag.uni.txt
                             
al ver los archivos llamados flag vamos a ver su contenido con icat indicando su particion 
                             
┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ icat disk.flag.img -o 0000360448 2082
            3.449677            13.056403
                             
┌──(erik㉿kali)-[~/Documentos/PicoCTF/apprentice]
└─$ icat disk.flag.img -o 0000360448 2371
picoCTF{by73_5urf3r_adac6cb4} <-- flag

```