A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message Try it here!

Hints:
1.-In the country that doesn't exist, the flag persists

### Solución

```
Nos dan un link que contiene imagenes de muchos paises, al ver el codigo fuente vemos 
que tienen como una flag asociada cada pais, le pregunte al shat que si habia un pais falso y si

resulta que UPANZI no existeasi que descargo esa imagen en la terminal y con stepic que es una
herramienta para extraer mensajes ocultos mediante esteganografía a las imagenes le paso un comando con
-d para que decodifique:

──(erik㉿kali)-[~/Documentos/PicoCTF/tarea3/fas]
└─$ stepic -d -i upz.png
/usr/lib/python3/dist-packages/PIL/Image.py:3402: DecompressionBombWarning: Image size (150658990 pixels) exceeds limit of 89478485 pixels, could be decompression bomb DOS attack.
  warnings.warn(
  
dandonos la flag:
picoCTF{fl4g_h45_fl4ga664459a}         
```