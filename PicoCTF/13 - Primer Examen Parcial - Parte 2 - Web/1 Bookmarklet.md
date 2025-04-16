Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:52685/), and find the flag!

Hints:
1.-A bookmarklet is a bookmark that runs JavaScript instead of loading a webpage.
2.-What happens when you click a bookmarklet?
3.-Web browsers have other ways to run JavaScript too.

### Solucion

```
En la pagina web que nos da seleccionamos el codiguito que nos muestran en la seccion de debajo, inspeccionamos y en terminal copeamos el codigo:
javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£Ö�ÓÚåÛÑ¢ÕÓ�Ô�ÅÐ�Ù�í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();

Solo damos enter y nos suelta el navegador un mensaje con la flag:

picoCTF{p@g3_turn3r_1d1ba7e0}
```