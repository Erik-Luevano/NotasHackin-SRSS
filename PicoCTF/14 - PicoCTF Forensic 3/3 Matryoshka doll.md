Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this

Hints:
1.-Wait, you can hide files inside files? But how do you find them?
2.-Make sure to submit the flag as picoCTF{XXXXX}


### Solución

```
Descargamos la imagen y con ayuda de binwalk vemos que hay otra imagen dentro
la extraemos:

──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/matryoska]
└─$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/matryoska]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/Forensic3/matryoska]
└─$ cd _dolls.jpg.extracted 
                                                                                                                      
┌──(erik㉿kali)-[~/…/PicoCTF/Forensic3/matryoska/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
Repetimos ese mismo proceso hasta llegar aqui:

──(erik㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                                                      
┌──(erik㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls                   
136DA.zip  flag.txt
                                                                                                                      
┌──(erik㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}  Obteniendo la flag


```