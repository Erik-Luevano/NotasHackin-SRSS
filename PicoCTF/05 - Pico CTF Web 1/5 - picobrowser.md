This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

Hints: You don't need to download a new web browser

### Solucion
web, debian

```
La pagina debia de tener el user agent como picobrowser para obtener la flag se envio una solicitud con este agente y checo la respuesta por medio de curl en consola:
erik@DESKTOP-NC0TP9I:~$ curl -s https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent: picobrowser" |
 grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
Y alli esta la flag
```