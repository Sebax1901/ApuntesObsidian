-------------------
+ Tags: #web #wordpress #reconocimiento #herramientas 
------------------------

La herramienta **Wpscan**[^1] es comúnmente utilizada para enumerar páginas web que dispongan de un gestor de contenidos [[WordPress]].

Su modo de uso es muy sencillo, podríamos realizar un escaneo a modo de prueba, ejecutando el siguiente comando de Bash:

```Bash
wpscan --url https://tinder.com
```

Si quisiéramos enumerar usuarios válidos existentes detrás de este gestor de contenidos, podríamos ejecutar el siguiente escaneo alternativo:

```Bash
wpscan --url https://tinder.com --enumerate u
```

Otra de las utilidades de esta herramienta es es capaz de aplicar fuerza bruta para descubrir credenciales válidas en los paneles de autenticación:

```Bash
wpscan --url https://tinder.com -U sebax -P /usr/share/wordlists/rockyou.txt
```

Cabe destacar que este procedimiento también puede aplicarse de manera manual[^2], abusando del archivo **xmlrpc.php**, siendo necesario crear para ello un script por ejemplo en Bash o Python.

----------
## Referencias

[^1]: Enlace al proyecto en Github: [Enlace](https://github.com/wpscanteam/wpscan)
[^2]: Procedimiento manual, abusando el XMLRPC: [[XMLRPC]]
