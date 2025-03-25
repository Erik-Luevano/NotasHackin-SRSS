There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?

Hints
1.-You should have enough hints to find the files, don't run a brute forcer.

### Solucion
web
```
Encontrar las 5 partes
1 html:
|   |   |
|---|---|
||<!doctype html>|
||<html>|
||<head>|
||<title>Scavenger Hunt</title>|
||<link href="[https://fonts.googleapis.com/css?family=Open+Sans\|Roboto](https://fonts.googleapis.com/css?family=Open+Sans\|Roboto)" rel="stylesheet">|
||<link rel="stylesheet" type="text/css" href="[mycss.css](http://mercury.picoctf.net:44070/mycss.css)">|
||<script type="application/javascript" src="[myjs.js](http://mercury.picoctf.net:44070/myjs.js)"></script>|
||</head>|
|||
||<body>|
||<div class="container">|
||<header>|
||<h1>Just some boring HTML</h1>|
||</header>|
|||
||<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>|
||<button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>|
|||
||<div id="tabintro" class="tabcontent">|
||<h3>How</h3>|
||<p>How do you like my website?</p>|
||</div>|
|||
||<div id="tababout" class="tabcontent">|
||<h3>What</h3>|
||<p>I used these to make this site: <br/>|
||HTML <br/>|
||CSS <br/>|
||JS (JavaScript)|
||</p>|
||<!-- Here's the first part of the flag: picoCTF{t -->|
||</div>|
|||
||</div>|
|||
||</body>|
||</html>|
|||

>>picoCTF{t

2 CSS:
div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

>>h4ts_4_l0

3 Robots.txt:
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

>>t_0f_pl4c

4 .htaccess:
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

>>3s_2_lO0k

5 DS_Store:
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}

>>_7a46d25d}
```