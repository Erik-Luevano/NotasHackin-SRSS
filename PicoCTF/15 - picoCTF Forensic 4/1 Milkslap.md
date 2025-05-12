🥛

### Solución 

```
para este reto utilizamos una herramienta de una libreria de ruby: zsteg 
que es para buscar esteganografia en imagenes PNG y BMP la cual busca texto
datos ocultos en ellas:

──(erik㉿kali)-[~/Documentos/PicoCTF/forensict3]
└─$ sudo gem install zpng -v 0.3.0
Fetching zpng-0.3.0.gem
Successfully installed zpng-0.3.0
Parsing documentation for zpng-0.3.0
Done installing documentation for zpng after 0 seconds
1 gem installed
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/forensict3]
└─$ sudo gem install zsteg -v 0.2.2
Fetching zsteg-0.2.2.gem
Fetching zpng-0.4.5.gem
Successfully installed zpng-0.4.5
Successfully installed zsteg-0.2.2
Parsing documentation for zpng-0.4.5
Parsing documentation for zsteg-0.2.2
Installing ri documentation for zsteg-0.2.2
Done installing documentation for zpng, zsteg after 0 seconds
2 gems installed
                                                                                                      
┌──(erik㉿kali)-[~/Documentos/PicoCTF/forensict3]
└─$ zsteg concat_v.png
imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect': stack level too deep (SystemStackError)
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/lib/zsteg/checker/wbstego.rb:41:in `to_s'
	from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/lib/zsteg/checker/wbstego.rb:41:in `to_s'
	from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/lib/zsteg/checker/wbstego.rb:41:in `to_s'
	from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/lib/zsteg/checker/wbstego.rb:41:in `to_s'
	from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
	 ... 10906 levels...
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/lib/zsteg.rb:30:in `run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.2/bin/zsteg:8:in `<top (required)>'
	from /usr/local/bin/zsteg:25:in `load'
	from /usr/local/bin/zsteg:25:in `<main>'


Bandera -> picoCTF{imag3_m4n1pul4t10n_sl4p5}

```