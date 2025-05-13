A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here Network Traffic PCAP file and try to get the flag. 

Hints:
1.-Filter your packets to narrow down your search.
2.-Attacks were done in timely manner.
3.-Time is essential

### Solución

```
Para este descargamos la captura y abrimos con 
wiresharck, las pistas nos dicen que el tiempo es imoprtamte asi que
ordenamos por tiempo y vemos que algunos paquetes ordenados pueden pormar unas cadenas ASCII
las cuales son las de 12 bytes en su TCP Payload, son un total de 6 de 12 bytes y 1 de 4:

63476c6a62304e5552673d3d
657a46305833633063773d3d
626e52666447673064413d3d
587a4d3063336c6664413d3d
596d68664e484a665a673d3d
4d7a45345a4749794d673d3d
66513d3d

Las cuales traduje en : https://www.rapidtables.com/convert/number/hex-to-ascii.html

Y me da como resultado una cadena en base 64: cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfZg==MzE4ZGIyMg==fQ==

la cual decodifico en una pagina y me suelta la flag: picoCTF{1t_w4snt_th4t_34sy_tbh_4r_f318db22}


```