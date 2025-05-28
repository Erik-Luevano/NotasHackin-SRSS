Why use p and q when I can use more? Connect with nc jupiter.challenges.picoctf.org 3726.

Hints:
1.-There's more prime factors than p and q, finding d is going to be different.

### Solución

```
En este reto nos dan una n que tiene mas de 2 factores, por suerte existe una pagina
que da el valor de tn directamente al introducuirle n: la cual de de resultado

tn: 6 129646 267538 338983 533559 696223 673684 119518 374048 869575 398575 139267 510959 032164 197023 856564 628219 908411 968853 848449 047596 695882 974167 053440 156235 035864 926348 677394 402334 480243 551002 857978 262872 763969 496023 323171 256105 375638 721951 770769 011866 125094 800406 329473 663118 971801 949504 053126 149374 049345 202060 811767 815869 521465 885222 502400 000000 000000

simplemente decodificamos con otra pagina utilizando nuestos valores: https://www.dcode.fr/rsa-cipher

picoCTF{too_many_fact0rs_8606199}
```