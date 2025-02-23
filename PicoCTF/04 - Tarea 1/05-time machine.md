What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/163/challenge.zip)

Hints:
1.-The `cat` command will let you read a file, but that won't help you here!
2.-Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
3.-When committing a file with git, a message can (and should) be included.

### Solución
WebShell, Git
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/163/challenge.zip
--2025-02-22 22:24:41--  https://artifacts.picoctf.net/c_titan/163/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.93, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17741 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                   100%[======================================================================================================>]  17.33K  --.-KB/s    in 0.005s  

2025-02-22 22:24:41 (3.64 MB/s) - 'challenge.zip' saved [17741/17741]

erik616-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
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
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/e6/
 extracting: drop-in/.git/objects/e6/5fedb3a72a16c577f4b17023b63997134b307d  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
erik616-picoctf@webshell:~$ ls -la
total 56
drwxr-xr-x 5 erik616-picoctf erik616-picoctf  4096 Feb 22 22:24 .
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
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 17741 Mar 12  2024 challenge.zip
drwxr-xr-x 3 erik616-picoctf erik616-picoctf    37 Mar 12  2024 drop-in
erik616-picoctf@webshell:~$ cd drop-in/
erik616-picoctf@webshell:~/drop-in$ git log --oneline

[3]+  Stopped                 git log --oneline
erik616-picoctf@webshell:~/drop-in$ 
e65fedb (HEAD -> master) picoCTF{t1m3m@ch1n3_88c35e3b}
(END)
```