Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:55434/).

Hints:
1.-Explore backend development with us
2.-The head was dumped.

### Solucion

```
La pagina web tiene un link: [#API Documentation](http://verbal-sleep.picoctf.net:55434/api-docs)

el cual entramos y cickeamos la seccion con el mismo nombre del reto,
damos a ejecutar y nos da un descargable, dicho descargable lo abrimos con algun editor de texto y al buscar con ctr + f "pico" nos da que en la linea 276169 esta la bandera: picoCTF{Pat!3nt_15_Th3_K3y_bed6b6b8}
```