-----------------
- Tags: #scripting #bash #comandos #linux 
----------------------

### Redirectores de estados

* stder (2)

```bash
cat /etc/host 2> /dev/null
```

* stdout (>)

```bash
cat /etc/hosts > /dev/null
```

También es posible convertir el error en output para redigirirlo (2>&1)

```bash
cat /etc/host > /dev/null 2>&1
```

Por último es posible redirigir todo, tanto output como error

```bash
cat /etc/hosts &>/dev/null
```

### Descriptores de archivos

Se crean con el comando exec, se asigna un número y se indican los permisos:

* *exec* para crear el descriptor de archivo *2* para indicar que se quiere el número 2, *<* para indicar que se quiere permiso de lectura, *>* para indicar que se quiere capacidad de escritura, y por último se indica el archivo en el que se requiere que se almacene.

```bash
exec 2<> file
```

Una vez se crea el descriptor de archivos se le asignan valores con el símbolo de redirección

*En el siguiente ejemplo se asigna el output del comando whoami al descriptor 3 que se almacena en el archivo file*

```bash
whoami >&3
```

Las cosas nuevas que se almacenen en el archivo se guardará en formato append, es decir que no se va a reescribir lo que ya contenga el archivo

##### Copia entre descriptores de archivos

También es posible crear copias entre descriptores de archivos, en el siguiente comando se copia lo que contiene el descriptor de archivo 5 al 8 que se está creando

```bash
exec 8>&5
```

##### Cerrar descriptores de archivos

Para cerrar los descriptores se usa el siguiente comando

```bash
exec 5>&-
```

De igual manera se puede cerrar el descriptor de archivo a la vez que se cierra el original

En el siguiente comando se crea el descriptor 6 a la vez que se cierra el 5

```bash
exec 6>&5-
```
