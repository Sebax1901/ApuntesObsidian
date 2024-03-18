-------------------
- Tags: #reconocimiento #herramientas #explotación 
-----------
# Definición

> Nmap (“mapeador de redes”) es una herramienta de código abierto para exploración de red y auditoría de seguridad. Se diseñó para analizar rápidamente grandes redes, aunque funciona muy bien contra equipos individuales. Nmap utiliza paquetes IP "crudos" («raw», N. del T.) en formas originales para determinar qué equipos se encuentran disponibles en una red, qué servicios (nombre y versión de la aplicación) ofrecen, qué sistemas operativos (y sus versiones) ejecutan, qué tipo de filtros de paquetes o cortafuegos se están utilizando así como docenas de otras características. Aunque generalmente se utiliza Nmap en auditorías de seguridad, muchos administradores de redes y sistemas lo encuentran útil para realizar tareas rutinarias, como puede ser el inventariado de la red, la planificación de actualización de servicios y la monitorización del tiempo que los equipos o servicios se mantiene activos.

Para más información puedes consultar la web oficial de [Nmap](https://nmap.org/man/es/index.html)

# Modificadores

### Modificadores habituales para el escaneo[^1]

| Modificador | Descripción |
| ----------- | ----------- |
| -p- | Escanea todos los puertos. |
| -Pn | Salta el saludo TCP (No hace Ping). Se salta la detección si el puerto está abierto. |
| -P | Indicar puertos específicos (-p- para escanear todos. 65536). |
| -sX | Paquete Xmas. |
| -sN | Paquete Null (Sin flags). |
| -sV | Analiza Versiones. |
| -T# | 1 - 5 -> siendo 5 más veloz (Entre más rapidez menos sigilo y precisión). |
| -F | Limita a los puertos más comunes. |
| -n | No aplica resolución DNS. Puede ralentizar el escaneo. |
| -v | Verbose |
| --open | Busca Puertos abiertos. |
| --min-rate 5000 | Paquetes no más lentos que 5000 x min. |
| -sT | Saludo TCP (Conexión normalita). |
| -O | Detecta el sistema operativo. |
| -sS | Self Scan (Más fiable en la respuesta de puertos). Es una manera más sigilosa de escanear dado que no responde con ACK sino que se completa el saludo TCP con un RST, por ende no se establece completamente la conexión con el destino|
| --script | Sistema de Scripting de nmap. |
| --top-ports # | Escanea la cantidad de puertos que se le indique de los más comunes |
| -sn | Escanea una red completa para descubrimiento de hosts. |
| -sC | Aplica todos los scripts básicos de reconocimiento. |

### Modificadores orientados a la evasión de firewalls

| Modificador | Descripción |
|  ---------- | ----------- |
| -f | **Fragmented**. Envía paquetes fragmentados para intentar evadir firewalls. |
| --mtu | **Maximum transmition unit** -> Unidad de transmisión máxima: Cuando se incluye un valor menor al que el firewall espera podría llegar a enumerar puertos filtrados por dicho firewall (Múltiplos de 8) |
| -D | **Decoy**. Hace spoofing (Suplantación de IP), para emitir paquetes con una IP falsificada. (También se envía el paquete desde la IP real) |
| --source-port | Puerto de origen. Permite decidir qué puerto del equipo atacante va a ser el que envíe el paquete |
| --data-length | Permite modificar el tamaño del paquete (Length). Siempre de base va a tener 58, si se incluye este parámetro se adicionará el valor que se seleccione a 58. |
| -sS | **Self Scan**. Dado que no se completa la conexión puede que no deje logs en los firewall lo cual lo hace más sigiloso a la par que más rápido |
| --min-rate | Controla la velocidad de paquetes por segundo a enviar al destino para evitar la detección del firewall (S4vitar recomienda 5000). |

### Aplicación de scripts específicos[^2]

Con las siguientes categorías se pueden buscar scripts específicos dependiendo la acción que se busca emplear:

| Categoría  | Descripción |
| ---------- | ----------- |
| Default | Categoría predeterminada que incluye una gran cantidad de scripts de reconocimientos básicos y útiles para la mayoría de escaneos. |
| Discovery | Se enfoca en descubrir información sobre la red, como detección de hosts y dispositivos activos, y la resolución de nombres de dominio. |
| Safe | Incluye scripts que son considerados seguros y que no realizan actividades invasivas que puedan desencadenar una alerta de seguridad en la red. |
| Intrusive | Incluye scripts invasivos quye pueden ser detectados fácilmente por un sistema de etección de intrusos o un firewall, pro que pueden proporcionar infromación valiosa sobre vulnerabilidades y debilidades en los sistemas y sercisios que se están ejecutando en la red |
| Vuln | Se enfoca en la detección de vulnerabilidades y debilidades en los sistemas y servicios que se están ejecutando en la red |

Para aplicar scripts de categorías específicas se puede hacer de dos formas:

1. Aplicando una categoría específica:

```Bash
nmap --script-safe <objetivo>
```

2. Aplicando dos o más categorías al mismo tiempo:

```Bash
nmap --script safe,vuln <objetivo>
```

Por último, si se desea aplicar un script específico, se puede hacer de la siguiente manera:

```Bash
nmap --script http-enum <objetivo>
```

-----------------

### Búsquedas comunes

###### Descubrimiento de puertos

```Shell
nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn [IP] -oG allPorts
```

```Shell
nmap -sCV -p22,80,3306,8080 192.168.20.80 -oN targeted
```

##### Escaneo de los puertos encontrados


## Referencias

[^1]: Para más comandos específicos de nmap consultar el [Enlace]([http://www.csirtcv.gva.es/nmap-6_-listado-de-comandos](http://www.csirtcv.gva.es/nmap-6_-listado-de-comandos))
[^2]: Para más scripts específicos de nmap consultar el [Enlace](https://nmap.org/nsedoc/categories/default.html)

