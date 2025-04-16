Can you win in a convincing manner against this chess bot? He won't go easy on you! You can find the challenge [here](http://verbal-sleep.picoctf.net:57518/).


Hints:
1.-Try understanding the code and how the websocket client is interacting with the server

### Solucion

```
En la pagina hay un pez y un tablero de ajedres, podemos derrotarlo y nos dara la flag, o inspeccionar el codigo y ver que la funcion sendMessage se puede poner en consola junto con mate o eval y distintos valores, si ponemos sendMessage("eval -1000000000000000000") que eval es como ejecutar codigo
el mensaje del pez dira su texto de derrota:

Huh???? How can I be losing this badly... I resign... here's your flag: picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_c0789e29}
```