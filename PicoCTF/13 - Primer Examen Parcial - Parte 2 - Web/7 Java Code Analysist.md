BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:57134/).

Hints:
1.-Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
2.-The 'role' and 'userId' fields in the JWT can be of interest to you!
3.-The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
4.-Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

### Solucion

```
El reto nos da un usuario y contraseña predeterminados tambien un descarganble de una carpeta, en la cual no encontr nada relevante

cuando ingresamos a la pagina y vemos que esta el apartado flag pero solo es para admin checo la network en local storage, veo un token jwt y abajo que puedo modificar mi usuario y rol, este es el token modificado con ayuda de la pagina jwt:

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NDU0NDQzNzMsImlhdCI6MTc0NDgzOTU3MywidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.-EUY2yfVhQkUumU-gPJ3E-zkfbyH4kOOt6pof2zMFKw

Despues de haber puesto Admin, admin y cambiar el id por 2

y modificar aqui tambien:
{"role":"Admin","iss":"bookshelf","exp":1745444373,"iat":1744839573,"userId":2,"email":"admin"}

En el local storage, recargamos pagina y seleccionamos flag y ahora si nos la suelta:

Great job! Here’s your flag:
picoCTF{w34k_jwt_n0t_g00d_42f5774a}
```