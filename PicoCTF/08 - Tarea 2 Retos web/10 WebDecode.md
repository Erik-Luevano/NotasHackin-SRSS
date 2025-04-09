Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:49332/) to find the flag

Hints:
1.-Use the web inspector on other files included by the web page.
2.-The flag may or may not be encoded

### Solucion

```
Entramos a la pagina inspeccionamos en el home y parece no haber nada, cuando vemos el about nos topamos esto:

<!DOCTYPE html> <html lang="en"> <head> <meta charset="utf-8"/> <meta content="IE=edge" http-equiv="X-UA-Compatible"/> <meta content="width=device-width, initial-scale=1.0" name="viewport"/> <link href="[style.css](view-source:http://titan.picoctf.net:49332/style.css)" rel="stylesheet"/> <link href="[img/favicon.png](view-source:http://titan.picoctf.net:49332/img/favicon.png)" rel="shortcut icon" type="image/x-icon"/> <!-- font (google) --> <link href="[https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,400&amp;display=swap](view-source:https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,400&display=swap)" rel="stylesheet"/> <title> About me </title> </head> <body> <header> <nav> <div class="logo-container"> <a href="[index.html](view-source:http://titan.picoctf.net:49332/index.html)"> <img alt="logo" src="[img/binding_dark.gif](view-source:http://titan.picoctf.net:49332/img/binding_dark.gif)"/> </a> </div> <div class="navigation-container"> <ul> <li> <a href="[index.html](view-source:http://titan.picoctf.net:49332/index.html)"> Home </a> </li> <li> <a href="[about.html](view-source:http://titan.picoctf.net:49332/about.html)"> About </a> </li> <li> <a href="[contact.html](view-source:http://titan.picoctf.net:49332/contact.html)"> Contact </a> </li> </ul> </div> </nav> </header> <section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9"> <h1> Try inspecting the page!! You might find it there </h1> <!-- .about-container --> </section> <!-- .about --> <section class="why"> <footer> <div class="bottombar"> Copyright © 2023 Your_Name. All rights reserved. </div> </footer> </section> </body> </html>

-->notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9">

Esa cadena parece estar en b64 así que con ayuda de cyberchef vemos que pasa:
picoCTF{web_succ3ssfully_d3c0ded_07b91c79}
```