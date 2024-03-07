------------------
- Tags: #bash #linux #reconocimiento #enumeración
------------------------------
### SUID

Con el siguiente comando se puede enumerar los binarios que cuentan con permisos SUID[^1], los cuales podrían ser vias potenciales para escalar privilegios.

```Bash
find -perm -4000 2>/dev/null
```

### Capabilities

Con el siguiente comando se pueden enumerar los binarios con [[Capabilities]].

```Bash
getcap -r / 2>/dev/null
```

Busca de manera recursiva (-r) desde la raíz ( / ) y redirige los errores al /dev/null (2>/dev/null).

### Tareas Cron

Con el siguiente comando se pueden listar las tareas cron que corren los usuarios del sistema:

```Bash
crontab -l
```

Con el siguiente comando se pueden listar los tiempos que faltan para la ejecución de alguna tarea programada (Cron):

```Bash
systemctl list-timers
```

Se puede emplear pspy[^2]. Esta es una herramienta que permite visualizar los procesos que se están ejecutando en el sistema con la ubicación del binario que ejecuta la tarea. Sin embargo, con el siguiente comando se puede también representar los procesos que se están ejecutando (command) con el usuario que los está corriendo (user):

```Bash
ps -eo user,command
```

### Herramientas adicionales

- [GFTOBins](https://gtfobins.github.io/)
- [Hacktricks](https://book.hacktricks.xyz/welcome/readme)

Permite ver que se puede llegar a hacer con lo que se encuentre en la enumeración del sistema operativo

------------------------
## Referencias

[^1]: Que al ejecutarse, pese a que se haga desde cualquier usuario del sistema, el comando se ejecuta como root.
[^2]: Link para la descarga del [proyecto](https://github.com/DominicBreuker/pspy/releases/tag/v1.2.1)

