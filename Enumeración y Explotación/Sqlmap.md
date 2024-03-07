------------------------------
- Tags: #explotación #herramientas 
-----------------------------

# Definición

> Sqlmap es una herramienta de código abierto que permite automatizar el proceso de un ataque de inyección de SQL. Gracias a este software, no es necesario aprender este lenguaje de programación para inyectar código malicioso a una base de datos MySQL. Un ciberataque de SQL injection podría resultar en diferentes tipos de consecuencias, como el robo, la modificación o la eliminación de la base de datos o, incluso, la instalación de _malwares_ y la ejecución remota de código en el sistema operativo de la víctima.

Unas de las principales funciones de sqlmap es:
- Identificar las vulnerabilidades de inyección SQL de una máquina y reportárselas al atacante a través de un proceso de detección riguroso y automatizado.
- Atacar bases de datos que utilicen gestores como MySQL, Oracle, Microsoft Access, Microsoft SQL Server, Amazon Redshift o Apache Ignite, entre muchos otros, según su [página web](https://sqlmap.org/).
- Enumerar listas de usuarios, hashes de contraseñas, tablas, qué bases de datos hay y qué privilegios y roles tiene cada perfil.
- Identificar el tipo de hash utilizado para encriptar contraseñas y ofrecer soporte para usar diccionarios que permitan descifrarlas.
- Hacer ejecución remota de código [^1].
- Subir y descargar ficheros a la base de datos, incluyendo softwares maliciosos.
- Eliminar, sustituir y modificar una base de datos entera o cualquier parte de ella.

----------------------------------

### Uso:

Para emplear la herramienta se puede ejecutar por ejemplo de la siguiente manera:

``` Bash
sqlmap -r request.req -p searchitem --batch --dbs -D sqlitraining -T users --columns
```

| Modificador | Funcionalidad |
| ----------- | ------------- |
| -r | Indica el archivo de la petición que se hará a la base de datos, puede tomarse por ejemplo del archivo que se obtiene de Burpsuite al interceptar la petición. **Ejemplo:** -r request.req|
| -p | Cual es el parámetro por el que se va a buscar. Lo da la interceptación del Burpsuite (Nombre del campo que llevará la consulta que se tramite a la base de datos). **Ejemplo:** -p searchitem[^2]  |
| --batch | Sirve para indicarle que salte los payloads para otras bases de datos diferentes a la que detectó en el servicio. |
| --dbs | Sirve para listar las bases de datos existentes en el servicio |
| -D | Sirve para indicar la base de datos que quiero leer. **Ejemplo:** -D sqlitraining |
| --tables | Sirve para enumerar las tablas de la base de datos seleccionada con el comando previo |
| -T | Sirve para indicar la tabla que quiero, dentro de la base de datos seleccionada con el parámetro -D. **Ejemplo:** -T users |
| --columns | Sirve para enumerar las columnas de la tabla indicada con el parámetro anterior. |
| -C | Sirve para indicar la columna que quiero dentro de la tabla indicada con el parámetro -T. **Ejemplo:** -C username,password |
| --dump | Sirve para, como último parámetro del comando, indicar que quiero que me lea el contenido de las columnas indicadas en el comando previo.|

------------------

## Referencias

[^1]: Para ver más acerca de la ejecución remota de comandos: [Enlace](https://keepcoding.io/blog/que-es-la-ejecucion-remota-de-codigo/).
[^2]: Para más claridad ver la siguiente imagen:
![[Pasted image 20230612223544.png]]
