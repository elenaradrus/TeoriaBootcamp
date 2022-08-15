![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Nociones de administración de permisos y usuarios en MySQL 

## Creación 

- Ejemplo: 

```SQL
    CREATE USER 'beatrix'@'localhost'
    IDENTIFIED BY '123456'; 
```

## Permisos

- Sintaxis 

```SQL

GRANT permiso
ON database
TO usuario;

```

- Ejemplo: 

```SQL 

GRANT SELECT
ON weblibros.categoria
TO juanperez;

```

- Suponiendo que la base de datos weblibros contenga dos tablas:

```SQL

mysql> show tables from weblibros;
+---------------------+
| Tables_in_weblibros |
+---------------------+
| categoria |
| libro |
+---------------------+
2 rows in set (0.00 sec)

```

- Si en vez de root la consulta fuese realizada por el usuario juanperez, obtendría lo siguiente:

```SQL 
mysql> show databases;
+--------------------+
| Database |
+--------------------+
| information_schema |
| weblibros |
+--------------------+
2 rows in set (0.00 sec)

mysql> show tables from weblibros;
+---------------------+
| Tables_in_weblibros |
+---------------------+
| categoria |
+---------------------+
1 row in set (0.00 sec)

```

- Y si el usuario juanperez intentara acceder a una tabla no permitida, el acceso le sería denegado:

```SQL

mysql> select * from weblibros.libro;
ERROR 1142 (42000): SELECT command denied to user 'juanperez'@'localhost' for table 'libro'

```

1. Opciones para indicar el tipo de permisos:

```SQL
    GRANT SELECT # un permiso específico
    GRANT SELECT, INSERT, UPDATE # varios permisos
    GRANT ALL # todos los permisos

```
2. Opciones para indicar a qué bases de datos/tablas aplicarán los permisos:
```SQL

ON database.table # a una tabla
ON database.table1, # a varias tablas
 database.table2,
 database2.table
ON database.* # a todas las tablas de la misma DB
```
3. Opciones para indicar a quién/quiénes aplican los permisos:

```SQL 
TO usuario # a un usuario
TO usuario1, usuario2 # a varios usuarios
```

[DOCUMENTACION_MYSQL](https://dev.mysql.com/doc/refman/8.0/en/user-names.html)