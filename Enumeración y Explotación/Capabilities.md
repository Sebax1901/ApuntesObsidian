---------------
- Tags: #linux #enumeración #bash #comandos 
------------------------

# Definición 

> En el contexto de los binarios en Linux, las "capabilities" se refieren a un conjunto de permisos más granulares que se pueden otorgar a los archivos ejecutables, en lugar de los permisos tradicionales de lectura, escritura y ejecución. Las capabilities permiten establecer políticas de seguridad más precisas y restringir el acceso a ciertas funcionalidades del sistema operativo.
> 
> En lugar de otorgar privilegios completos de superusuario (root) a un archivo ejecutable, las capabilities permiten otorgar solo los privilegios necesarios para que el programa funcione correctamente. Esto reduce el riesgo de exposición a vulnerabilidades de seguridad, ya que el programa solo tendrá acceso a los recursos y funciones específicas que se le han concedido

Algunas de las capabilites son:

|<center> **Nombre** </center>|<center> **Uso** </center>|
|---|---|
|CAP_CHOWN|Cambiar el propietario de archivos.|
|CAP_DAC_OVERRIDE|Anular controles de acceso a archivos.|
|CAP_DAC_READ_SEARCH|Leer y buscar en archivos independientemente de los permisos.|
|CAP_FOWNER|Establecer propietario arbitrario en archivos propios.|
|CAP_FSETID|Establecer bits SUID y SGID en archivos.|
|CAP_KILL|Borrar procesos arbitrarios.|
|CAP_SETGID|Establecer el GID efectivo.|
|CAP_SETUID|Establecer el UID efectivo.|
|CAP_SETPCAP|Establecer otras capacidades.|
|CAP_LINUX_IMMUTABLE|Establecer atributo de archivo inmutable.|
|CAP_NET_BIND_SERVICE|Enlazar sockets a puertos privilegiados.|
|CAP_NET_BROADCAST|Enviar y recibir paquetes de difusión.|
|CAP_NET_ADMIN|Administración avanzada de configuración de red.|
|CAP_NET_RAW|Enviar o recibir paquetes IP crudos.|
|CAP_IPC_LOCK|Bloquear páginas en la memoria principal.|
|CAP_IPC_OWNER|Establecer atributos de IPC de otro usuario.|
|CAP_SYS_MODULE|Cargar y descargar módulos del kernel.|
|CAP_SYS_RAWIO|Realizar operaciones de E/S de E/S sin restricciones.|
|CAP_SYS_CHROOT|Cambiar el directorio raíz.|
|CAP_SYS_PTRACE|Depurar procesos de otros usuarios.|
|CAP_SYS_PACCT|Ver cuentas de proceso.|
|CAP_SYS_ADMIN|Administración del sistema.|
|CAP_SYS_BOOT|Reiniciar o apagar el sistema.|
|CAP_SYS_NICE|Establecer prioridades de planificador de alta prioridad.|
|CAP_SYS_RESOURCE|Cambiar límites de recursos del sistema.|
|CAP_SYS_TIME|Cambiar la hora del sistema.|
|CAP_SYS_TTY_CONFIG|Configurar dispositivos terminales.|
|CAP_MKNOD|Crear archivos especiales.|
|CAP_LEASE|Establecer y borrar arrendamientos de archivos.|
|CAP_AUDIT_WRITE|Enviar registros de auditoría.|
|CAP_AUDIT_CONTROL|Control de auditoría.|
|CAP_SETFCAP|Establecer capacidades de archivo.|
|CAP_MAC_OVERRIDE|Ignorar política de seguridad de Mandatory Access Control (MAC).|
|CAP_MAC_ADMIN|Administrar políticas de seguridad de MAC y de etiquetas.|
|CAP_SYSLOG|Enviar mensajes de registro a través de syslog.|
|CAP_WAKE_ALARM|Configurar alarmas RTC.|
|CAP_BLOCK_SUSPEND|Bloquear suspensión y hibernación del sistema.|
|CAP_AUDIT_READ|Leer entradas de registro de auditoría.|
|CAP_PERFMON|Acceder a contadores de rendimiento del hardware.|
|CAP_BPF|Usar programas BPF para extender funcionalidades del kernel.|

