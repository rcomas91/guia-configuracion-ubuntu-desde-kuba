# Pasos para instalar y configurar de manera fácil Ubuntu o cualquier variente de esta distribución desde Cuba.

## **Para este caso utilizamos Kubuntu 20.04.**

**Paso 1:** Instalar la distribución deseada desde una unidad extraible. Para grabar la imagen podemos usar Rufus(en Windows) o Startup Disk Creator (Linux). Descargamos el ISO y hacemos la memoria booteable.


**Paso 2:** Después de instalar tu sistema operativo lo primero que hacemos es configurar y actualizar los repos. Si estamos detrás de un proxy lo primero es pasarle el proxy al sistema.

Editar el archivo /etc/environment y agregar estas líneas con los datos correspondientes:

```bash
http_proxy http://username:password@proxy-ip:port/
https_proxy http://username:password@proxy-ip:port/
ftp_proxy http://username:password@proxy-ip:port/
no_proxy="localhost,127.0.0.1,localaddress,.localdomain.com"
Duplicadas en mayusculas
HTTP_PROXY http://username:password@proxy-ip:port/
HTTPS_PROXY username:password@proxy-ip:port/
FTP_PROXY username:password@proxy-ip:port/
NO_PROXY "localhost,127.0.0.1,localaddress,.localdomain.com"
```

Para que se utilize el proxy para apt-get, se deben agregar estas lineas en /etc/apt/apt.conf con los datos correspondientes.

```bash
Acquire::http::proxy "http://username:password@proxy-ip:port";
Acquire::ftp::proxy "http://username:password@proxy-ip:port";
Acquire::https::proxy "http://username:password@proxy-ip:port";```



