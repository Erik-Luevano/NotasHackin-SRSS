Files can always be changed in a secret way. Can you find the flag? cat.jpg

Hints:
1.-Look at the details of the file
2.-Make sure to submit the flag as picoCTF{XXXXX}

### Solución

```
Descargamos el archivo y vemos los metadatos con exiftool vemos una cadena base 64

──(erik㉿kali)-\[\~/Documentos/PicoCTF/tarea3/information]
└─\$ exiftool cat.jpg
ExifTool Version Number         : 13.10
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2025:05:12 16:38:16-06:00
File Inode Change Date/Time     : 2025:05:12 16:38:16-06:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 < cadena b64
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1

┌──(erik㉿kali)-\[\~/Documentos/PicoCTF/tarea3/information]
└─\$ exiftool cat.jpg | grep Licence

┌──(erik㉿kali)-\[\~/Documentos/PicoCTF/tarea3/information]
└─\$ exiftool cat.jpg | grep License
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

Utilizamos sed para mantener solo lo que nos importa ujnto con una exprecion estandar regular
y traducimos del base 64

┌──(erik㉿kali)-\[\~/Documentos/PicoCTF/tarea3/information]
└─\$ exiftool cat.jpg | grep License | sed -e 's/.\*: //' | base64 -d
picoCTF{the\_m3tadata\_1s\_modified}

```  