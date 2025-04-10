We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Hints:
1.-Try fixing the file header

### Solucion

```
Descargamos el archivo Mystery
que al parecer esta dañado ya que no se reconoce, con hexeditor modificamos el encabezado de los exas:
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/c0rrupt]
└─$ xxd mystery              
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4322 4452  .PNG........C"DR

y tambien el chunck critico para que sea reconocido:
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/c0rrupt]
└─$ file mystery       
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

Con ayuda de pngcheck nos damos cuenta que notifica de un error: 
─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.3.1)

mystery  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERROR: mystery

El cual podemos solucionar editando otra vez con hexeditor y siguiendo el estandar de la imagen colocando 00 en un chunck que estaba mal y unas correcciones mas de bits ya podremos abrir el archivo:
picoCTF{c0rrupt10n_1847995}
```