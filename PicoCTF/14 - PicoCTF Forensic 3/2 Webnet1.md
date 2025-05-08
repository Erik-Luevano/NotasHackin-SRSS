We found this packet capture and key. Recover the flag.

Hints:
1.-Try using a tool like Wireshark.
2.-How can you decrypt the TLS stream?


### Solución

```
Descargo la captura y la llave, abro con wiresharck y agrego la llave
para desencriptar paquetes, haciendo un seguimiento de packetes TLS
vemos que se descarga una imagen que en el encabezado tiene la bandera verdadera:
......JFIF..............Exif..MM.*.................J...........R.(...........;.........Z................................picoCTF{honey.roasted.peanuts}......ICC_PROFILE.......lcms....mntrRGB XYZ .........).9acspAPPL...................................-lcms...............................................
desc.......^cprt...\....wtpt...h....bkpt...|....rXYZ........gXYZ........bXYZ........rTRC.......@gTRC.......@bTRC.......@desc........c2..................................................................................text....FB..XYZ ...............-XYZ ...........3....XYZ ......o...8.....XYZ ......b.........XYZ ......$.........curv...............c...k...?.Q.4!.).2.;.F.Qw].kpz....|.i.}...0.....C.................
		
...


```