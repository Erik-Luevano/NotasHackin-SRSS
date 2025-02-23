My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)

Hints:
1.-`git branch -a` will let you see available branches
2.-How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
3.-Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

# Solución
WebShell
```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/69/challenge.zip
--2025-02-23 01:39:08--  https://artifacts.picoctf.net/c_titan/69/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.18, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24642 (24K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                   100%[======================================================================================================>]  24.06K  --.-KB/s    in 0.01s   

2025-02-23 01:39:08 (2.27 MB/s) - 'challenge.zip' saved [24642/24642]

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
  inflating: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
 extracting: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
 extracting: drop-in/.git/refs/heads/feature/part-3  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
   creating: drop-in/.git/objects/eb/
 extracting: drop-in/.git/objects/eb/4de2a9826332633c62e44a1a130d9b1a88171a  
   creating: drop-in/.git/objects/6e/
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa  
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c  
   creating: drop-in/.git/objects/ad/
 extracting: drop-in/.git/objects/ad/37f59bfdcb1e8052bf7e12e1d89a2adb315cf9  
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/97/
 extracting: drop-in/.git/objects/97/92a89fa347abc711f84b7208db18d164d45aca  
   creating: drop-in/.git/objects/78/
 extracting: drop-in/.git/objects/78/ac69cf187e7a72fcd8750f3d7435e807f4a61a  
   creating: drop-in/.git/objects/50/
 extracting: drop-in/.git/objects/50/d2c5d928a5b377e0d75093b113707e21ca36d9  
   creating: drop-in/.git/objects/13/
 extracting: drop-in/.git/objects/13/08521d0d0b66df1a73e91d5d9e2d74610002e3  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
erik616-picoctf@webshell:~$ ls -la
total 64
drwxr-xr-x 5 erik616-picoctf erik616-picoctf  4096 Feb 23 01:39 .
drwxr-xr-x 3 root            root               29 Feb 13 18:05 ..
-rw------- 1 erik616-picoctf erik616-picoctf  1287 Feb 22 20:59 .bash_history
-rw-r--r-- 1 erik616-picoctf erik616-picoctf   220 Feb 13 18:05 .bash_logout
-rw-r--r-- 1 erik616-picoctf erik616-picoctf  3771 Feb 13 18:05 .bashrc
drwxrwxr-x 3 erik616-picoctf erik616-picoctf    19 Feb 20 22:29 .local
-rw-r--r-- 1 erik616-picoctf erik616-picoctf   807 Feb 13 18:05 .profile
-rw------- 1 erik616-picoctf erik616-picoctf  1281 Feb 20 22:57 .python_history
drwx------ 2 erik616-picoctf erik616-picoctf    48 Feb 22 21:26 .ssh
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf   167 Feb 18 21:45 .wget-hsts
-rw-r--r-- 1 root            root             4443 Feb 23 01:36 README.txt
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf 24642 Mar 11  2024 challenge.zip
drwxr-xr-x 3 erik616-picoctf erik616-picoctf    33 Mar  9  2024 drop-in
erik616-picoctf@webshell:~$ cd drop-in/
erik616-picoctf@webshell:~/drop-in$ git branch -a

[1]+  Stopped                 git branch -a
erik616-picoctf@webshell:~/drop-in$ ls
flag.py
erik616-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")
erik616-picoctf@webshell:~/drop-in$ man flag.py
No manual entry for flag.py
erik616-picoctf@webshell:~/drop-in$ ls -la
total 8
drwxr-xr-x 3 erik616-picoctf erik616-picoctf   33 Mar  9  2024 .
drwxr-xr-x 5 erik616-picoctf erik616-picoctf 4096 Feb 23 01:39 ..
drwxr-xr-x 8 erik616-picoctf erik616-picoctf  166 Mar  9  2024 .git
-rw-r--r-- 1 erik616-picoctf erik616-picoctf   30 Mar  9  2024 flag.py
erik616-picoctf@webshell:~/drop-in$ sudo -l
-bash: sudo: command not found
erik616-picoctf@webshell:~/drop-in$ python3 flag.py 
Printing the flag...
erik616-picoctf@webshell:~/drop-in$ nano flag.py 
erik616-picoctf@webshell:~/drop-in$ git checkout main
Already on 'main'
erik616-picoctf@webshell:~/drop-in$ git branch -a

[2]+  Stopped                 git branch -a
erik616-picoctf@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
erik616-picoctf@webshell:~/drop-in$ ls -la
total 8
drwxr-xr-x 3 erik616-picoctf erik616-picoctf   33 Feb 23 01:43 .
drwxr-xr-x 5 erik616-picoctf erik616-picoctf 4096 Feb 23 01:39 ..
drwxr-xr-x 8 erik616-picoctf erik616-picoctf  166 Feb 23 01:43 .git
-rw-rw-r-- 1 erik616-picoctf erik616-picoctf   64 Feb 23 01:43 flag.py
erik616-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')erik616-picoctf@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
erik616-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')erik616-picoctf@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
erik616-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")

print("w0rk_e4b79efb}")
erik616-picoctf@webshell:~/drop-in$ 
```