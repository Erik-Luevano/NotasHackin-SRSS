How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 62671
Username: picoplayer 
Password: kZx-HVJKu8
```

### Solución
webshell

```
erik616-picoctf@webshell:~$ ssh -p 62671 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62671 ([13.59.203.175]:62671)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62671' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
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

picoplayer@challenge:~$ ls -la
total 12
drwxr-xr-x 1 picoplayer picoplayer   20 Feb 22 21:10 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Feb 22 21:10 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
picoplayer@challenge:~$ ls -la /
total 0
drwxr-xr-x   1 root   root     51 Feb 22 21:07 .
drwxr-xr-x   1 root   root     51 Feb 22 21:07 ..
-rwxr-xr-x   1 root   root      0 Feb 22 21:07 .dockerenv
lrwxrwxrwx   1 root   root      7 Mar  8  2023 bin -> usr/bin
drwxr-xr-x   2 root   root      6 Apr 15  2020 boot
d---------   1 root   root     27 Aug  4  2023 challenge
drwxr-xr-x   5 root   root    340 Feb 22 21:07 dev
drwxr-xr-x   1 root   root     66 Feb 22 21:07 etc
drwxr-xr-x   1 root   root     24 Aug  4  2023 home
lrwxrwxrwx   1 root   root      7 Mar  8  2023 lib -> usr/lib
lrwxrwxrwx   1 root   root      9 Mar  8  2023 lib32 -> usr/lib32
lrwxrwxrwx   1 root   root      9 Mar  8  2023 lib64 -> usr/lib64
lrwxrwxrwx   1 root   root     10 Mar  8  2023 libx32 -> usr/libx32
drwxr-xr-x   2 root   root      6 Mar  8  2023 media
drwxr-xr-x   2 root   root      6 Mar  8  2023 mnt
drwxr-xr-x   2 root   root      6 Mar  8  2023 opt
dr-xr-xr-x 255 nobody nogroup   0 Feb 22 21:07 proc
drwx------   2 root   root     37 Mar  8  2023 root
drwxr-xr-x   1 root   root     54 Feb 22 21:10 run
lrwxrwxrwx   1 root   root      8 Mar  8  2023 sbin -> usr/sbin
drwxr-xr-x   2 root   root      6 Mar  8  2023 srv
dr-xr-xr-x  13 nobody nogroup   0 Feb 22 21:07 sys
drwxrwxrwt   1 root   root      6 Aug  4  2023 tmp
drwxr-xr-x   1 root   root     18 Mar  8  2023 usr
drwxr-xr-x   1 root   root     17 Mar  8  2023 var
picoplayer@challenge:~$ crontab -l
no crontab for picoplayer
picoplayer@challenge:~$ sudo cd /run/
[sudo] password for picoplayer: 
picoplayer is not in the sudoers file.  This incident will be reported.
picoplayer@challenge:~$ sudo vi
[sudo] password for picoplayer: 
picoplayer is not in the sudoers file.  This incident will be reported.
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Sorry, user picoplayer may not run sudo on challenge.
picoplayer@challenge:~$ crontab -l
no crontab for picoplayer
picoplayer@challenge:~$ ls -lah /home/picoplayer/
total 12K
drwxr-xr-x 1 picoplayer picoplayer   20 Feb 22 21:10 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3.7K Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Feb 22 21:10 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
picoplayer@challenge:~$ ls -lah /tmp/            
total 0
drwxrwxrwt 1 root root  6 Aug  4  2023 .
drwxr-xr-x 1 root root 51 Feb 22 21:07 ..
picoplayer@challenge:~$ ls -lah /var/tmp/
total 0
drwxrwxrwt 2 root root  6 Mar  8  2023 .
drwxr-xr-x 1 root root 17 Mar  8  2023 ..
picoplayer@challenge:~$ cat /etc/crontab 
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
picoplayer@challenge:~$ 
```