Can you get the flag?Go to this [website](http://saturn.picoctf.net:64620/) and see what you can discover.

Hints:
1.-How is the password checked on this website?

### Solucion

```
Inspeccionamos codigo fuente de la pagina:
<!DOCTYPE html> <html lang="en"> <head> <meta charset="UTF-8"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> <meta http-equiv="X-UA-Compatible" content="ie=edge"> <link rel="stylesheet" href="[style.css](view-source:http://saturn.picoctf.net:64620/style.css)"> <title>Secure Customer Portal</title> </head> <body> <h1>Secure Customer Portal</h1> <p>Only letters and numbers allowed for username and password.</p> <form role="form" action="[login.php](view-source:http://saturn.picoctf.net:64620/login.php)" method="post"> <input type="text" name="username" placeholder="Username" required autofocus></br> <input type="password" name="password" placeholder="Password" required> <button type="submit" name="login">Login</button> </form> </body> </html>

Nos metemos en login.php
luego en secure.js:

function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

podemos ver unas credenciales muy llamativas, probamos:
picoCTF{j5_15_7r4n5p4r3n7_a8788e61}
```