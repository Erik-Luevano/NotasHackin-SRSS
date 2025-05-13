The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file here. 

Hints:
1.-This problem can be solved by just opening the file in different ways

### Solución

```
Descargamos el pdf al abrirlo se nota que es la mitad de la flag,
intentarlo convertirlo a un archivo png revelara la otra mitad de la flag:

──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/sotp]
└─$ open flag2of2-final.pdf 
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/sotp]
└─$ 1n_pn9_&_pdf_2a6a1ea8}  
zsh: parse error near `}'
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/sotp]
└─$ convert flag2of2-final.pdf flag2of2-final.png 
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/sotp]
└─$ open flag2of2-final.png 
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/sotp]
└─$ picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}   
```