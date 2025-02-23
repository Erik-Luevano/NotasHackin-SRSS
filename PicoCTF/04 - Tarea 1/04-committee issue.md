I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/137/challenge.zip)

Hints:
1.- Version control can help you recover files if you change or lose them!
2.- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
3.- You can 'checkout' commits to see the files inside them
### Solución
WebShell, git

```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/137/challenge.zip
--2025-02-22 22:02:55--  https://artifacts.picoctf.net/c_titan/137/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.93, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19197 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                   100%[======================================================================================================>]  18.75K  --.-KB/s    in 0.008s  

2025-02-22 22:02:55 (2.43 MB/s) - 'challenge.zip' saved [19197/19197]

erik616-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/fc/
 extracting: drop-in/.git/objects/fc/a28bbf8dde2f49246166ae6512a1046fc4cbc3  
   creating: drop-in/.git/objects/61/
 extracting: drop-in/.git/objects/61/db7d05a8b7657aedc1e13320ca53623a364fe7  
   creating: drop-in/.git/objects/ea/
 extracting: drop-in/.git/objects/ea/859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/ef/
 extracting: drop-in/.git/objects/ef/0b7cc6b98367fa168573c931e0f7098ef59182  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
erik616-picoctf@webshell:~$ ls -la
total 56
drwxr-xr-x 5 erik616-picoctf erik616-picoctf  4096 Feb 22 22:03 .
drwxr-xr-x 3 root            root               29 Feb 13 18:05 ..
-rw------- 1 erik616-picoctf erik616-picoctf  1287 Feb 22 20:59 .bash_history
-rw-r--r-- 1 erik616-picoctf erik616-picoctf   220 Feb 13 18:05 .bash_logout
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  3771 Feb 13 18:05 .bashrc
drwxrwxr-x 3 erik616-picoctf erik616-picoctf    19 Feb 20 22:29 .local
-rw-r--r-- 1 erik616-picoctf erik616-picoctf   807 Feb 13 18:05 .profile
-rw------- 1 erik616-picoctf erik616-picoctf  1281 Feb 20 22:57 .python_history
drwx------ 2 erik616-picoctf erik616-picoctf    48 Feb 22 21:26 .ssh
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf   167 Feb 18 21:45 .wget-hsts
-rw-r--r-- 1 root            root             4443 Feb 22 20:59 README.txt
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 19197 Mar 12  2024 challenge.zip
drwxr-xr-x 3 erik616-picoctf erik616-picoctf    37 Mar 12  2024 drop-in
erik616-picoctf@webshell:~$ cd drop-in/
[Aqui busque que esa carpeta son las de git donde se guardan los cambios]
erik616-picoctf@webshell:~/drop-in$ git status
On branch master
nothing to commit, working tree clean
erik616-picoctf@webshell:~/drop-in$ git log --oneline
[Ese comando lo busque y es para mostrar los commits pasados, habia uno que decia create flag]

[2]+  Stopped                 git show ea859bf
erik616-picoctf@webshell:~/drop-in$ 
commit ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    create flag

[1]+  Stopped                 git log --oneline
erik616-picoctf@webshell:~/drop-in$ git show <ea859bf>
-bash: syntax error near unexpected token `newline'
erik616-picoctf@webshell:~/drop-in$ git show ea859bf 
[Mostrar ese commit ya]

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..fca28bb
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_cf09a485}
(END)
```