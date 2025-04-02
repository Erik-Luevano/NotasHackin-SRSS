How about trying to match a regular expression The website is running [here](http://saturn.picoctf.net:54915/).

Hints:
1.-Access the webpage and try to match the regular expression associated with the text field

### Solucion

```
Accedemos a la pagina del reto y se ve un campo para introducir texto,
checamos el codigo fuente y vemos el siguiente codigo que es el que valida el campo:

<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>

En el comentario se puede ver esta exprecion: ^p.....F!?
Que podemos utilisar junto con una pagina de ayuda de expreciones regulares para armar una,
vemos que debe iniciar con p tener 5 caracteres y finalizar con F
comprobamos con p12345F y funciona:
picoCTF{succ3ssfully_matchtheregex_0694f25b}
```