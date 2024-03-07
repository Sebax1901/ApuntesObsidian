------------------
- Tags: #explotación #owasp_top10 #web #bash 
-------------------------

# Definición

> Local file intrusion. es una vulnerabilidad de seguridad informática que se produce cuando una aplicación web **no valida adecuadamente** las entradas de usuario, permitiendo a un atacante **acceder a archivos locales** en el servidor web.
> 
>En muchos casos, los atacantes aprovechan la vulnerabilidad de LFI al abusar de parámetros de entrada en la aplicación web. Los parámetros de entrada son datos que los usuarios ingresan en la aplicación web, como las URL o los campos de formulario. Los atacantes pueden manipular los parámetros de entrada para incluir rutas de archivo local en la solicitud, lo que puede permitirles acceder a archivos en el servidor web. Esta técnica se conoce como “**Path Traversal**” y se utiliza comúnmente en ataques de LFI

Cuando una página es vulnerable a este ataque , los archivos se pueden listar y leer mediante [[Wrappers]], y estos a su vez podrían generar una [[RCE]].

