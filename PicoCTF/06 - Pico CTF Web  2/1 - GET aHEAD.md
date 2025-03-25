Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:21939/](http://mercury.picoctf.net:21939/)

Hints:
1.-Maybe you have more than 2 choices
2.-Check out tools like Burpsuite to modify your requests and look at the responses

### Solucion
Web, Debian
```
ejecutar el parametro -I:
erik@DESKTOP-NC0TP9I:~$ curl -I GET http://mercury.picoctf.net:21939/index.php
curl: (6) Could not resolve host: GET
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_6ef27873}
Content-type: text/html; charset=UTF-8

erik@DESKTOP-NC0TP9I:~$
```