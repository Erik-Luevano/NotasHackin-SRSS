We found this packet capture and key. Recover the flag.

Hints:
1.-Try using a tool like Wireshark.
2.-How can you decrypt the TLS stream?

### Solución

```
Descargo la captura y la llave que nos da el problema, la abro en wiresharck
despues agregamos la llave al wiresharck que nos proporcionaron, despues simplemente
en los packetes se busca filtrando por los detalles del paquete TLS la palabra picoCTF
encontrando esta:

Pico-Flag: picoCTF{nongshim.shrimp.crackers}

```