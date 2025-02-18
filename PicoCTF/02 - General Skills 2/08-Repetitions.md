Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/475/enc_flag).

Hints:
1.- Multiple decoding is always good.

### Solución
Shell

```
erik616-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/475/enc_flag
--2025-02-18 23:09:10--  https://artifacts.picoctf.net/c/475/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                                        100%[======================================================================================================>]     349  --.-KB/s    in 0s      

2025-02-18 23:09:10 (22.1 MB/s) - 'enc_flag' saved [349/349]

erik616-picoctf@webshell:~$ ls
README.txt  enc_flag
erik616-picoctf@webshell:~$ ls -ls
total 12
8 -rw-r--r-- 1 root            root            4443 Feb 18 23:06 README.txt
4 -rw-rw-r-- 1 erik616-picoctf erik616-picoctf  349 Mar 16  2023 enc_flag
erik616-picoctf@webshell:~$ chmod +x enc_flag 
erik616-picoctf@webshell:~$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXcE9VazFXV2toT1dHUllDbUY2UWpSWk1GWlhWa2RHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
erik616-picoctf@webshell:~$ base64 -d enc_flag > decoded_flag.txt
erik616-picoctf@webshell:~$ cat decoded_flag.txt 
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JUVWpOUk1WWkhOWGRYCmF6QjRZMFZXVkdGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
erik616-picoctf@webshell:~$ base64 -d decoded_flag.txt > final_flag.txt
erik616-picoctf@webshell:~$ cat final_flag.txt 
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFUd3BTUjNRMVZHNXdX
azB4Y0VWVGFteEVXbm93T1VOblBUMEsK
erik616-picoctf@webshell:~$ base64 -d final_flag.txt.txt > van3.txt
base64: final_flag.txt.txt: No such file or directory
erik616-picoctf@webshell:~$ base64 -d final_flag.txt > van3.txt
erik616-picoctf@webshell:~$ cat van3.txt 
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwpSR3Q1VG5wWk0xcEVTamxEWnowOUNnPT0K
erik616-picoctf@webshell:~$ base64 -d van3.txt > van4.txt
erik616-picoctf@webshell:~$ cat van4.txt 
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZO
RGt5TnpZM1pESjlDZz09Cg==
erik616-picoctf@webshell:~$ base64 -d van4.txt > van5.txt
erik616-picoctf@webshell:~$ cat van5.txt 
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfNDkyNzY3ZDJ9Cg==
erik616-picoctf@webshell:~$ base64 -d van5.txt > van6.txt
erik616-picoctf@webshell:~$ cat van6.txt 
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_492767d2}
erik616-picoctf@webshell:~$ 
```