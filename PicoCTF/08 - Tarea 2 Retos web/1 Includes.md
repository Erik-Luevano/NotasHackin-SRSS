Can you get the flag?

Can you get the flag? Go to this [website](http://saturn.picoctf.net:61074/) and see what you can discover.

Hints:
1.-Is there more code than what the inspector initially shows?

### Solucion
 web
```
Inspeccionamos el codigo y no encontramos nada, al meterse al CSS Vemos la primera parte de la flag: 
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */

Y en el .js la segunda parte:
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_b8f4b022}

Flag: picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}
``` 