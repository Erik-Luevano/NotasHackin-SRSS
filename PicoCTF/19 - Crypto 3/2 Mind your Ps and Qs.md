In RSA, a small e value can be problematic, but what about N? Can you decrypt this? values

Hints:
1.-Bits are expensive, I used only a little bit over 100 to save money

### Solución

```
se nos dan unas valores para decifrar, con ayuda de factordb sacamos los valores de p y q
a partir de n luego utilizamos las formulas establezidas para sacar el valor de tn d y m
y luego con bytes.fromhex sacamos la bandera de m ya traducida
─(erik㉿kali)-[~/Documentos/PicoCTF/crypto3/2]
└─$ cat solucion2.py   
c = 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n = 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e = 65537

p = 1899107986527483535344517113948531328331
q = 674357869540600933870145899564746495319033

print(p*q)
print(n)


tn = (p-1) * (q-1)
d = pow(e, -1, tn)
print("valor tn: ",tn)
print("valor d: ",d)
m = pow(c,d,n)

print("valor m: ",m)

print(bytes.fromhex(hex(m)[2:]))
                                                                                                             
┌──(erik㉿kali)-[~/Documentos/PicoCTF/crypto3/2]
└─$ 

─(erik㉿kali)-[~/Documentos/PicoCTF/crypto3/2]
└─$ python solucion2.py
1280678415822214057864524798453297819181910621573945477544758171055968245116423923
1280678415822214057864524798453297819181910621573945477544758171055968245116423923
valor tn:  1280678415822214057864524798453297819181234364596418349127352680639289550089776560
valor d:  449332735606084960351204406909610297301574728466820933515942864925459265983556193
valor m:  13016382529449106065927291425342535437996222135352905256639555654677400177227645
b'picoCTF{sma11_N_n0_g0od_05012767}'


```