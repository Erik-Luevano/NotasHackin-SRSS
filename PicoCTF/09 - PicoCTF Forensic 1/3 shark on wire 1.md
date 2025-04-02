We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

Hints:
1.-Try using a tool like Wireshark
2.-What are streams?

### Solucion

```
Primero descargamos con wget:
──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/sharkonwire1]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2025-04-02 18:42:30--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[===================================================================================>] 233.84K   177KB/s    in 1.3s    

2025-04-02 18:42:32 (177 KB/s) - ‘capture.pcap’ saved [239455/239455]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/PicoCTF/Forensic/sharkonwire1]
└─$ file capture.pcap                                                          
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

Podemos ver que es una captura, podemos ver eltrafico de packetes que capturo con wireshark, al buscar entre los UDP podemos ver que el packete señalado como: udp.stream eq 6 contiene la bandera:
picoCTF{StaT31355_636f6e6e}
```