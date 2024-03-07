-----------------
- Tags: #linux #comandos #scripting 
----------------------

Aquí se encontrará la recopilación de todos los comandos de linux, detallando la funcionalidad.

| <center> Comando </center> | <center> Funcionalidad </center> |
|---|---|
|;|Separa comandos para hacelos ambos|
|&&|El segundo se ejecuta si el primero es exitoso|
|$? (Echo $?)|Sirve para verificar el estado del comando anterior. 0 exitoso; > 0 fallido|
|\||El segundo se ejecuta si el primero es fallido|
|/dev/null|Agujero negro (Sirve para errores)|
|>|Redirige la salida del comando|
|>>|Redirige la salida del comando. De forma append (Sin borrar lo ya existente)|
|2>|Los errores se redirigen a lo siguiente que se le indique (Por lo general /dev/null)|
|2>&1|Convierte los stder en stdout ('cat /etc/noFile >/dev/null 2>&1')|
|&>|Redirige toda la salida (stder o stdout) ('cat /etc/noFile &>/dev/null')|
|&|Si lo pones al final, corre el comando en segundo plano (Bajo la misma consola)|
|& Disown|Si lo pones al final, corre el comando en segundo plano (Independiente de la consola)|
|chmod|Cambia los permisos (o+w, g-r, u+x)|
|chgrp|Cambia el grupo de un archivo o directorio|
|lsattr|ls pero listando las flags de los items|
|chattr|Cambia las flags de los items:  <br>* +i (Inmutable)|
|du -hc|Conocer el peso de un archivo|
|upx|Hacer a los archivos menos pesados|
|lsb_release -a|Versión del Kernel|
|smbmap|Escanea recursos compartidos con Samba (Puerto 445).  <br>-H [IP]-> indicar la IP del host.  <br>--download -> descargar un recurso compartido a nivel de red.  <br>-r [Ubicación] -> Escanea los recursos compartidos que hay en una ubicación.|
|file|Para saber el tipo de contenido de un archivo|
|Find|. Para buscar todos los archivos  <br>-type para buscar por tipo (f para archivos - files)  <br>-readable -> para buscar archivos legibles  <br>! -executable -> archivos no ejecutables  <br>-size -> para buscar por tamaño (al final del tamaño indicar el tipo: c para bytes)  <br>-user -> para indicar el usuario propietario  <br>-group > para indicar el grupo propietario|
|sort|-u para que elimine repetidos  <br>\| uniq -u -> con el pipe operator para que se liste solo las cadenas unicas|
|Strings|Lista solo los datos legibles de un archivo de texto|
|Tail|-n numero de lineas de abajo hacia arriba|
|base 64|Sirve para codificar en base64  <br>-d para decodificar  <br>Se puede usar con echo y un pipe \||
|lsof|-i:[Puerto] sirve para conocer el proceso que está corriendo en un puerto específico|
|ncat|Netcat  <br>-ssl [ip] [puerto] -> Sirve para conectarse por ssl encriptado|
|Cron|* Minutos (0 - 59)  <br>* Horas (0 - 23)  <br>* Dia del mes (1 - 31)  <br>* Mes (1 - 12)  <br>* Día de a semana (1 a 6 -> lunes a sábado) (0 o 7 -> domingo)|
|Grep|-A [Número] -> Para mostrar las siguientes n lineas|
|tr|-d -> Para eliminar un carácter de un texto|
| id | Permite ver los grupos en los que se encuentra el usuario |
| setcap | Asignar [[Capabilities]] a un binario específico |

### Nvim

| <center> Comando </center> | <center> Funcionalidad </center> |
|---|---|
|w|Moverse entre palabras|
|d|borrar|
|Alt + u|Control z|
|dd|Borrar Lineas|
|v|Modo Visual (Selección)|
|y|Copiar|
|p|Pegar|
|o|Crea una nueva linea|
|/|Busqueda (n para siguiente - N para el anterior)|

### Comandos gráficos del Sistema Operativo

| <center> Comando </center> | <center> Funcionalidad </center> |
|---|---|
|Windows + shift + r | Actualiza la pantalla aplicando los cambios gráficos que se hayan hecho|
|Windows + s|Hacer una pantalla flotante|
|Windows + t|Deshacer pantalla flotante - tamaño normal|
|Windows + clic derecho|Mueve la pantalla flotante|
|Windows + ctrl + flechas|Mueve la pantalla flotante|
|Windows + clic izquierdo|Cambia el tamaño de la pantalla flotante|
|Windows + alt + flechas|Cambia el tamaño de la pantalla flotante|
|Windows + shift + q|Matar Sesión actual|
|Windows + q|Cerrar la ventana actual|
|Control + shift + z|Si la terminal está partida te centra en la que estás (Hace Zoom)|
|Windows + shift + f|Abre el navegador firefox|
|Windows + shift + s|Abre flameshot para hacer capturas de pantalla|


