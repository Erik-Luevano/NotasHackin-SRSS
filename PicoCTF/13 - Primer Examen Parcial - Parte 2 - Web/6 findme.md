Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:62981/).

Hints:
1.-any redirections?

### Solucion

```
La pagina es un login en el cual nos sugieren un usuario y contraseña, accedemos y esta un buscador, puse la palabra flag y en la hint nos dice de chequear el redireccionamiento, habro la pestaña de network para ver que onda y retrocedo en la pagina, veo que al final del link aparece un tipo cadena b64 y al darle otra vez otra, resulta que son las 2 partes de la flag:

picoCTF{proxies_all_the_way_3d9e3697}
```