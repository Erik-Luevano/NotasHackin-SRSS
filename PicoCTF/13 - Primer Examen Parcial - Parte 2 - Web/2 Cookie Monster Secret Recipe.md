Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:49480/) and good luck

Hints:
1.- Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
2.- Cookies aren't just for eating - they're also used in web technologies!
3.- Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.

### Solucion

```
Al entrar en la pagina web existe un login ponemos credenciales cualquiera y vemos que nos dice que[

# Access Denied

Cookie Monster says: 'Me no need password. Me just need cookies!'

Hint: Have you checked your cookies lately?

checamos los cookies y nos genero una:
cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0FDOEZDRDc1fQ%3D%3D

La cual parece ser una cadena en b64, entramos a una pagina a decodificar y:
picoCTF{c00k1e_m0nster_l0ves_c00kies_AC8FCD75}
```