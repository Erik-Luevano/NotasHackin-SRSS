What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

Hints:
1.- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.
## Solucion 2
python

````
>>> import base64
>>> base64.b64decode('bDNhcm5fdGgzX3IwcDM1')
b'l3arn_th3_r0p35'
>>> 
```