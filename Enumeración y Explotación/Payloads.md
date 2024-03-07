-----------------------
- Tags:  #explotación 
-----------------------
# Definición

>El _payload_ es la carga maliciosa que ejecuta un hacker en el ordenador de una víctima durante un ciberataque. Si bien, por medio de la explotación de vulnerabilidades, el atacante consigue infiltrarse en un sistema, el payload es aquel set de instrucciones que ejecutará el daño deseado en el ordenador.
>Los payloads son códigos inyectados en el sistema de la víctima que permiten ejecutar tareas como:

- Ejecución de código remoto y toma del control de la máquina.
- Conexión a una botnet.
- Carga y descarga de archivos.
- Exfiltración de datos sensibles.
- Despliegue de [[Malware]].

Para más información consultar la definición en: [Enlace](https://keepcoding.io/blog/que-es-un-payload/)

### Tipos de payloads

**Payload Staged**: Es un tipo de payload que se **divide en dos** **o más etapas**. La primera etapa es una pequeña parte del código que se envía al objetivo, cuyo propósito es establecer una conexión segura entre el atacante y la máquina objetivo. Una vez que se establece la conexión, el atacante envía la segunda etapa del payload, que es la carga útil real del ataque. Este enfoque permite a los atacantes sortear medidas de seguridad adicionales, ya que la carga útil real no se envía hasta que se establece una conexión segura.

**Payload Non-Staged**: Es un tipo de payload que se envía como **una sola entidad** y **no se divide en múltiples etapas**. La carga útil completa se envía al objetivo en un solo paquete y se ejecuta inmediatamente después de ser recibida. Este enfoque es más simple que el Payload Staged, pero también es más fácil de detectar por los sistemas de seguridad, ya que se envía todo el código malicioso de una sola vez.

