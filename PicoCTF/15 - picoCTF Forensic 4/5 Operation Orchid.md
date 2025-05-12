Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download compressed disk image

### Solución
```
descargamos y descomprimimos el archivo, vemos las particiones, despues montamos una seccion en temp
calculando en bits donde comienza la particion:

──(erik㉿kali)-[~/Documentos/PicoCTF/orchid]
└─$ mv disk.flag.img.gz /tmp          
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/orchid]
└─$ cd /tmp 
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ ls
disk.flag.img.gz
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-colord.service-p8t5Ob
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-haveged.service-UDMx5o
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-ModemManager.service-Rzupnn
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-pcscd.service-Ah2tsR
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-polkit.service-CI8Fkj
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-power-profiles-daemon.service-klMwhX
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-systemd-logind.service-3MLRU1
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-upower.service-iMyIHi
Temp-a5a151a5-c521-4ff8-94db-15f7833cc588
VMwareDnD
vmware-root_751-4290559920
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ gzip -d disk.flag.img.gz 
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ mmls disk.flag.img      
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ mkdir foolder
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ sudo mount disk.flag.img /tmp/foolder -o offset=$((411648*512)) 
[sudo] contraseña para erik: 
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ ls
disk.flag.img
foolder
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-colord.service-p8t5Ob
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-fwupd.service-6Q8uTT
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-haveged.service-UDMx5o
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-ModemManager.service-Rzupnn
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-pcscd.service-Ah2tsR
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-polkit.service-CI8Fkj
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-power-profiles-daemon.service-klMwhX
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-systemd-logind.service-3MLRU1
systemd-private-76ffb28394ac4d018f48772ca1f6ff4e-upower.service-iMyIHi
Temp-a5a151a5-c521-4ff8-94db-15f7833cc588
VMwareDnD
vmware-root_751-4290559920
                                                                                                      
┌──(erik㉿kali)-[/tmp]
└─$ cd foolder   
                                                                                                      
┌──(erik㉿kali)-[/tmp/foolder]
└─$ ls
bin   dev  home  lost+found  mnt  proc  run   srv   sys  usr
boot  etc  lib   media       opt  root  sbin  swap  tmp  var
                       
Vemos con root un archivo
                       
┌──(erik㉿kali)-[/tmp/foolder]
└─$ sudo su                                                        
┌──(root㉿kali)-[/tmp/foolder]
└─# cd root
                                                                                                      
┌──(root㉿kali)-[/tmp/foolder/root]
└─# ls
flag.txt.enc
                             
 Despues checamos el historial del sistema y vemos como fue encriptada la flag
                             
┌──(root㉿kali)-[/tmp/foolder/root]
└─# cat .ash_history 
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567 <--
shred -u flag.txt
ls -al
halt
                                       
Al saber la contraseña usada la desencriptamos y guardamos el resultado en un archivo decrypt.txt
                                       
┌──(root㉿kali)-[/tmp/foolder/root]
└─# openssl aes256 -d -in flag.txt.enc -out decrypt.txt 
enter AES-256-CBC decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40E7A396A57F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                      
┌──(root㉿kali)-[/tmp/foolder/root]
└─# ls
decrypt.txt  flag.txt.enc
                                                                                                                                                                                                     
┌──(root㉿kali)-[/tmp/foolder/root]
└─# cat decrypt.txt 
picoCTF{h4un71ng_p457_0a710765} <-- flag desencriptada  
                                   
```