Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer. ssh -p 59728 ctf-player@saturn.picoctf.net. The password is af86add3

Hints:
1.-What programs do you have access to?

### Solucion

```
Podemos ver que varios comandos estan bloqueados pero echo no asi que vemos los archivos que estan con ayuda de un comandito y vamos abriendo 1 por 1:
┌──(erik㉿kali)-[~]
└─$ ssh -p 59728 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:59728 ([13.59.203.175]:59728)' can't be established.
ED25519 key fingerprint is SHA256:lMXKIC17ONzyUJx7ZYBY5VSwoxCz20uq5/Nm+IhXKew.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:59728' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Specialer$ ls
-bash: ls: command not found
Specialer$ pwd
/home/ctf-player
Specialer$ echo waldos
waldos
Specialer$ echo */*
abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt
Specialer$ echo "(<abra/cadabra.txt)"
(<abra/cadabra.txt)
Specialer$ echo "$(<abra/cadabra.txt)"
Nothing up my sleeve!
Specialer$ echo "$(<abra/cadaniel.txt)"
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ echo "$(<ala/kazam.txt)"

Hasta abrir el de la flag:
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_a8567b6f}

```