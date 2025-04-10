We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

### Solucion

```
Descargamos la captura y habrimos con wiresharck
podemos ver que en el tramo del stream 50 vemos "start" y en el 60 "end"

podemos ver que comparten el puerto 22 asi que filtramos:
udp.dstport == 22
Y en la info de esos strings parece ser que se forma la flag

Asi que para no estar checando caracter por caracter e irlo transformando utilizamos scapy y creamos un crip en python:
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag) 

Al ejecutar da la flag:
┌──(venv)─(kali㉿kali)-[~/Documents/PicoCTF/Forensic/sharkonwire2]
└─$ python exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```