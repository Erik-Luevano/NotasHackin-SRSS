Can you read files in the root file?The system admin has provisioned an account for you on the main server:`ssh -p 52713 picoplayer@saturn.picoctf.net`Password: `e3pn6lmvHt`Can you login and read the root file?

Hints:
1.-What permissions do you have?

### Solución
WebShell
```
Basicamente me conecte al puerto con el usuario y contraseña propuestos revise el contenido de la raiz y vi la carpeta challengue que no tenia permisos de nada
con sudo -l vi que podia usar vi lo use con la carpeta challengue y alli aparecia un archivo:
"/challenge/metadata.json"
me meti y salio la bandera
Se me perdio la bandera por copear otra cosa jaja
Connection to saturn.picoctf.net closed by remote host.e": "picoplayer", "password": "e3pn6lmvHt"}
Connection to saturn.picoctf.net closed.                                                                                                                                      
erik616-picoctf@webshell:~$ 
```