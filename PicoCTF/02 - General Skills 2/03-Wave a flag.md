Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...

Hints:
1.- This program will only work in the webshell or another Linux computer.
2.- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm`
3.- Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
4.- -h and --help are the most common arguments to give to programs to get more information from them!
5.- Not every program implements help features like -h and --help.

### Solución
Python
```
erik616-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
--2025-02-18 22:02:40--  https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm.1'

warm.1                                          100%[======================================================================================================>]  10.68K  --.-KB/s    in 0s      

2025-02-18 22:02:40 (415 MB/s) - 'warm.1' saved [10936/10936]

erik616-picoctf@webshell:~$ 
erik616-picoctf@webshell:~$ ./warm.1 -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
erik616-picoctf@webshell:~$ 
```