There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

Hints:
1.-There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2.-Try to think about how the website verifies your login.
### Solucion
Web
```
Iniciar secion en la pagina con admin'-- contraseña admin
despues de haber inspeccionado la pagina y ver un campo oculto debajo en el boton de login:
<input type="hidden" name="debug" value="0">
Se cambia a 1 y gracias a la ' nos deja entrar y obtener la flag
# Logged in!

	Your flag is: picoCTF{s0m3_SQL_f8adf3fb}
```