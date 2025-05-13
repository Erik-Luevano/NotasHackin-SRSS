Now you DON’T see me. This report has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Hints:
1.-How can you be sure of the redaction?

### Solución

```
Descargas y abres el archivo gracias luego seleccionas todo el texto
que existe en el y se puede ver como la bandera solo estaba como tapada al copear 
se puede ver: 


──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ ^[[200~Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
zsh: bad pattern: ^[[200~Financial
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ Breakdown - Just painted over in MS word.
Breakdown: no se encontró la orden
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ Cost Benefit Analysis
Orden «Cost» no encontrada. Quizá quiso decir:
  la orden «host» del paquete deb «bind9-host»
  la orden «ost» del paquete deb «openstructure»
  la orden «most» del paquete deb «most»
Pruebe con: sudo apt install <nombre del paquete deb>
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ Credit Debit
Orden «Credit» no encontrada. Quizá quiso decir:
  la orden «mredit» del paquete deb «mrtrix3»
Pruebe con: sudo apt install <nombre del paquete deb>
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ This is not the flag, keep looking
This: no se encontró la orden
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ Expenses from the
Expenses: no se encontró la orden
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ picoCTF{C4n_Y0u_S33_m3_fully}
picoCTF{C4n_Y0u_S33_m3_fully}: no se encontró la orden
                                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/rgw]
└─$ Redacted document.~

picoCTF{C4n_Y0u_S33_m3_fully} <---
```