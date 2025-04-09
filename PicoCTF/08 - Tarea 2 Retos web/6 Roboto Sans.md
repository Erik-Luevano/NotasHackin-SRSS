The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:63181/) out.

### Solucion

```
Existe un archivo robots.txt en la pagina en donde hay 3 lineas base 64, la unica que dice algo es la de enmedio:

anMvbXlmaWxlLnR4dA==

Que es js/myfile.txt

Al poner esa ruta en el link nos suelta la flag:
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```