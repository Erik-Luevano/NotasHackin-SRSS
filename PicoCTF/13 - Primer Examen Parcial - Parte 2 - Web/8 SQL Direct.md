Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 51114 -U postgres pico` Password is `postgres`

Hints:
1.-What does a SQL database contain?

### Solucion

```

Nos conectamos y tratamos de ver las tablas, luego seleccionamos todo de flags:

──(kali㉿kali)-[~/Documents/PicoCTF/examen1/ocho]
└─$ psql -h saturn.picoctf.net -p 51114 -U postgres pico
Password for user postgres: 
psql (17.0 (Debian 17.0-1+b2), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags
pico-# select * from flags;
ERROR:  syntax error at or near "select"
LINE 2: select * from flags;
        ^
pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

```