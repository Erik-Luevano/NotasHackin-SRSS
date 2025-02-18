Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

## Solución
Shell

```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/500/files.zip
--2025-02-18 23:27:07--  https://artifacts.picoctf.net/c/500/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: 'files.zip'

files.zip                                       100%[======================================================================================================>]   3.81M  1.82MB/s    in 2.1s    

2025-02-18 23:27:09 (1.82 MB/s) - 'files.zip' saved [3995553/3995553]

erik616-picoctf@webshell:~$ unzip files.zip 
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8   
erik616-picoctf@webshell:~$ ls -ls
total 7068
   8 -rw-r--r--   1 root            root               4443 Feb 18 23:17 README.txt
  44 drwxrwxr-x 121 erik616-picoctf erik616-picoctf   28672 May  3  2020 big-zip-files
3112 -rw-rw-r--   1 erik616-picoctf erik616-picoctf 3182988 Aug  4  2023 big-zip-files.zip
   0 drwxrwxr-x   5 erik616-picoctf erik616-picoctf     124 May 13  2022 files
3904 -rw-rw-r--   1 erik616-picoctf erik616-picoctf 3995553 Aug  4  2023 files.zip
erik616-picoctf@webshell:~$ find files/ - 
-amin                   -execdir                -ignore_readdir_race    -mmin                   -path                   -true                   .bash_logout
-anewer                 -executable             -ilname                 -mount                  -perm                   -type                   .bashrc
-atime                  -false                  -iname                  -mtime                  -print                  -uid                    .profile
-cmin                   -fls                    -inum                   -name                   -print0                 -used                   .python_history
-cnewer                 -follow                 -ipath                  -newer                  -printf                 -user                   .ssh/
-context                -fprint                 -iregex                 -nogroup                -prune                  -version                .wget-hsts
-ctime                  -fprint0                -iwholename             -noignore_readdir_race  -quit                   -warn                   README.txt
-daystart               -fprintf                -links                  -noleaf                 -readable               -wholename              big-zip-files/
-delete                 -fstype                 -lname                  -nouser                 -regex                  -writable               big-zip-files.zip
-depth                  -gid                    -ls                     -nowarn                 -regextype              -xdev                   files/
-empty                  -group                  -maxdepth               -ok                     -samefile               -xtype                  files.zip
-exec                   -help                   -mindepth               -okdir                  -size                   .bash_history           
erik616-picoctf@webshell:~$ find files/ -type f -name "uber-secret.txt"
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
erik616-picoctf@webshell:~$ cat $(find files/ -type f -name "uber-secret.txt")
picoCTF{f1nd_15_f457_ab443fd1}
erik616-picoctf@webshell:~$ 
```