-----------------
- Tags: #linux #comandos 
----------------------
Principales funciones para definir en la ZSH

##### Función MKT para creación de carpetas para práctica con máquinas virtuales

``` Shell
function mkt () {
    mkdir {nmap,content,exploits}
}
```

##### Función para copiar los puertos encontrados con un escaneo inicial

``` Shell
function extractPorts() {
  ports="$(cat $1 | grep -oP '\d{1,5}/open' | awk '{print $1}' FS='/' | xargs | tr ' ' ',')"
  ip_address="$(cat $1 | grep -oP '^Host: .* \(\)' | head -n 1 | awk '{print $2}')"
  echo -e "\n[*] Extracting information...\n" > extractPorts.tmp
  echo -e "\t[*] IP Address: $ip_address" >> extractPorts.tmp
  echo -e "\t[*] Open ports: $ports\n" >> extractPorts.tmp
  echo $ports | tr -d '\n' | xclip -sel clip
  echo -e "[*] Ports copied to clipboard\n" >> extractPorts.tmp
  cat extractPorts.tmp -l Java
  rm extractPorts.tmp
}
```

