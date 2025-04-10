I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

### Solucion

```
Descargamos un archivo que al parecer esta vacio, pero checamos que realmente si tiene caracteres especiales invisibles, y al ver con xxd podemos ver que los codigos corresponden a tipos de espacios, daremos uso de esta herramienta
Instalamos el pwntools que permite modificar esos codigos para intentar pasar a binario:
─(kali㉿kali)-[~/Documents/PicoCTF/Forensic/WhitePages]
└─$ pipx install pwntools
  installed package pwntools 4.14.1, installed using Python 3.12.7
  These apps are now globally available
    - asm
    - checksec
    - common
    - constgrep
    - cyclic
    - debug
    - disablenx
    - disasm
    - elfdiff
    - elfpatch
    - errno
    - hex
    - libcdb
    - main
    - phd
    - pwn
    - pwnstrip
    - scramble
    - shellcraft
    - template
    - unhex
    - update
    - version
done! ✨ 🌟 ✨

Hacemos este codigo:
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)

para procesar los datos remplazar las cadenas por 0 y 1 despues unbits y nos da:
                                                                                                                                                                      
┌──(pwntools-venv)─(kali㉿kali)-[~/Documents/PicoCTF/Forensic/WhitePages]
└─$ python exp.py
bytearray(b'00001010000010010000100101110000011010010110001101101111010000110101010001000110000010100000101000001001000010010101001101000101010001010010000001010000010101010100001001001100010010010100001100100000010100100100010101000011010011110101001001000100010100110010000000100110001000000100001001000001010000110100101101000111010100100100111101010101010011100100010000100000010100100100010101010000010011110101001001010100000010100000100100001001001101010011000000110000001100000010000001000110011011110111001001100010011001010111001100100000010000010111011001100101001011000010000001010000011010010111010001110100011100110110001001110101011100100110011101101000001011000010000001010000010000010010000000110001001101010011001000110001001100110000101000001001000010010111000001101001011000110110111101000011010101000100011001111011011011100110111101110100010111110110000101101100011011000101111101110011011100000110000101100011011001010111001101011111011000010111001001100101010111110110001101110010011001010110000101110100011001010110010001011111011001010111000101110101011000010110110001011111001101110011000100110000001100000011100000110110001100000110001000110000011001100110000100110111001101110011100101100001001101010110001001100100001110000110001101100101001100100011100101100110001100100011010001100110001101010011100000110110011001000110001101111101000010100000100100001001')
                                                                                                                                                                       
┌──(pwntools-venv)─(kali㉿kali)-[~/Documents/PicoCTF/Forensic/WhitePages]
└─$ python exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'
```