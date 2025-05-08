We found this file. Recover the flag.

Hints:
1.-Weird that it won't display right...


### Solución

```
Descargamos el archivo y vemos que corresponde a un
entonces le cambiamos la extencion y con hexeditor modificamos algunos ofsets
que tenia mal correspondientes al tipo de archivo

──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ ls
tunn3l_v1s10n
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ mv tunn3l_v1s10n tunn3l_v1s10n.bmp
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ ls
tunn3l_v1s10n.bmp
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ hexeditor tunn3l_v1s10n.bmp 
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ open tunn3l_v1s10n.bmp 
                               
Aqui volvemos a hexeditor porque la imagen biendo los detalles no corresponde su altura
asi que modificamos los ofsets de altura:

┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/tunn3l]
└─$ hexeditor tunn3l_v1s10n.bmp
Abrimos la imagen y alli esta la flag:
picoCTF{qu1t3_a_v13w_2020} 

```