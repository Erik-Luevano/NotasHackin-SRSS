Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download disk image
    Remote machine: ssh -i key_file -p 65105 ctf-player@saturn.picoctf.net


### Solución

```
Descargamos y descomprimimos el archivo

──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# gzip -d disk.img.gz 
                                                                                                      
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
   
Comenzamos a navegar en el offset y filtramos por ssh como primera opcion
   
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# fls disk.img -o 206848 -r | grep ssh
++ r/r 2147:	sshd
+++ l/l 54:	sshd
++ r/r 2148:	sshd
+ d/d 14:	ssh
++ r/r 15:	ssh_host_ed25519_key
++ r/r 16:	ssh_host_ed25519_key.pub
++ r/r 17:	ssh_host_ecdsa_key
++ r/r 18:	ssh_host_ecdsa_key.pub
++ r/r 19:	ssh_host_dsa_key
++ r/r 20:	ssh_host_dsa_key.pub
++ r/r 21:	ssh_host_rsa_key
++ r/r 22:	ssh_host_rsa_key.pub
++ r/r 2136:	ssh_config
++ r/r 2149:	sshd_config
++ r/r 2084:	ssh-keygen
++ r/- * 0:	ssh-copy-id
++ r/- * 0:	ssh-keyscan
++ r/- * 0:	ssh-pkcs11-helper
++ r/r 2140:	ssh-add
++ r/r 2145:	ssh
++ r/r 2144:	ssh-pkcs11-helper
++ r/r 2143:	ssh-keyscan
++ r/r 2142:	ssh-copy-id
++ r/r 2141:	ssh-agent
++ r/r 2150:	sshd
+++++ r/r 676:	sshd
++ d/d 3907:	ssh
+++ r/r 2152:	ssh-sk-helper
+++ r/r 2151:	ssh-pkcs11-helper
+ r/r 712:	setup-sshd
+ d/d 3916:	.ssh
                
Vemos que tiene .ssh
                
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# fls disk.img -o 206848 3916         
r/r 2345:	id_ed25519
r/r 2346:	id_ed25519.pub

Vemos que tiene 2 llaves la publica y privada las vemos

┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# icat disk.img -o 206848 2346
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGCtd7hso2E7OQItY6aTjMMyKZb1FVmeBfnVjyHcGYos root@localhost
                                                                                                      
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# icat disk.img -o 206848 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                           
Como el comando sujerido del reto guardamos la clave privada en eun archivo llamado key_file
                           
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# icat disk.img -o 206848 2345 > key_file
                      
modificamos los permisos para que ssh la acepte
                      
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# chmod og-r key_file 
                 
Nos conectamos y alli esta la flag para ser catada
                 
┌──(root㉿kali)-[/home/…/Documentos/PicoCTF/forensict3/oni]
└─# ssh -i key_file -p 65105 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:65105 ([13.59.203.175]:65105)' can't be established.
ED25519 key fingerprint is SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[saturn.picoctf.net]:65105' (ED25519) to the list of known hosts.
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_b5066e83}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

picoCTF{k3y_5l3u7h_b5066e83} <--
```