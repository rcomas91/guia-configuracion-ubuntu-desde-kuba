# ☢ 🛠 😛  Pasos para configurar de manera fácil Ubuntu o cualquier variente de esta distribución desde Cuba. ☢ 🛠 😛 #

## Para este caso utilizamos Kubuntu 20.04.

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
    Acquire::https::proxy "http://username:password@proxy-ip:port";
```
**NOTA**: Si quieres una conexión momentánea es suficiente con que ejecutes los siguientes Comandos Linux:
```bash
    export http_proxy=http://username:contraseña@proxy:puerto/
    export https_proxy=https://username:contraseña@proxy:puerto/  
```
Para más detalles visite:  
>[https://www.sysadminsdecuba.com/2017/11/tips-configuracion-de-proxy-para-los-servicios-de-linux/
](URL)

**Paso 3:** Para escoger desde donde vamos a actualizar nuestro sistema sino lo hacemos de los repositorios de Internet que vienen configurados por defecto, tenemos las  opciones que aparecen en esta web.

>[ https://gutl.jovenclub.cu/lista-de-repositorios-disponibles-para-nuestra-comunidad/
](URL)


☕ ☕ **NOTA**: Para que tengan una idea actualizar ubuntu focal desde jovenclub me toma aproximadamente 120 min el update y upgrade la primera vez. ☕ ☕

**Paso 4:** Después de actualizar los repos siempre instalo las herramientas básicas que siempre utilizo para el día a día y para el desarrollo de software que es a lo que me dedico.

**Herramientas básicas (las pongo por separado para que instalen las que ustedes prefieran)**  

   > • apt-get install mc  
    • apt-get install synaptic  
    • apt-get install thunderbird  
    • apt-get install pidgin  
    • apt-get install gparted  
    • apt-get install htop  
    • apt-get install neofetch  
    • apt-get install telegram-desktop  
    • apt-get install gimp  
    • apt-get install wget  
    • apt-get install caffeine  
    • apt-get install curl  
    • wp-office: instrucciones para instalar en: https://comoinstalar.info/wps-office-en-linux/  
    • timeshift: https://www.linuxadictos.com/instalar-timeshift-nuestra-distribucion-gnulinux.html

⚛⚛ **Herramientas de desarrollo**  ⚛⚛
   > • VS code: [ https://ubunlog.com/visual-studio-code-editor-codigo-abierto-ubuntu-20-04/?utm_source=dlvr.it&utm_medium=facebook](URL)  
    • mysql workbench: [https://askubuntu.com/questions/1230752/how-can-i-install-mysql-workbench-on-ubuntu-20-04-lts](URL)  
    • Java: [https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-20-04-es](URL)  
    • mysql-server: [https://ubunlog.com/mysql-8-base-datos-ubuntu/](URL)  
    • xamp:    
    • node: Para instalar node descargamos la última version estable para linux desde el sitio oficial  [https://nodejs.org/en/](URL) y luego seguimos los pasos descritos en la siguiente página [https://www.netveloper.com/instalar-nodejs-desde-un-fichero-.tar.xz-en-linux ](URL)

**NOTA:** Antes de pasar a instalar angular cli y después de instalar node le pasamos el proxy a npm:
```bash
    npm config set proxy http://username:password@proxyserver:puerto
    npm config set https-proxy http://username:password@proxyserver:puerto
```


   > • angular-cli: https://ubunlog.com/angular-instala-framework-ubuntu  
    • virtualbox: apt-get install virtualbox  
    • intellidea:  
    • git: apt-get install git  

Luego le paso el proxy a git:
```bash
git config --global http.proxy http//proxyserver:puerto
git config --global https.proxy https//proxyserver:puerto
```
**En caso de tener conexión directa y necesitemos quitarle la configuración de proxy a git**

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

   > • docker  
    • docker-compose

**NOTA**: si te fijas la mayoría de estas herrmientas son de los repos oficiales pues debido a la velocidad de la conexión muchas veces tenemos problemas para descargar alguna aplicación de terceros, sin hablar de snap que se nos demora un mundazo. Lo que no quiere decir que no use herramientas de tercero. En los links están las instrucciones de como instalar cada herramienta pués si lo incluimos en este tutorial no terminamos nunca.😅😅

**Paso # 5:** Estilos y utilidades

Para mi escritorio KDE el tema que que me gusta es Aptana el cual es bien minimalista para instalarlo solo tenemos que ejecutar:

**NOTA:** Si vas a usar wget y estas detrás de proxy modificamos el etc/wgetrc y adicionamos las siguientes líneas:
```bash
https_proxy = http://usuario:password@proxyserver:puerto/
http_proxy = http://usuario:password@proxyserver:puerto/
ftp_proxy = http://usuario:password@proxyserver:puerto/
```
```bash
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update && sudo apt-get install --install-recommends adapta-kde
sudo apt install papirus-icon-theme
```
En caso de utilizar otra distibución puedes ejecutar:
```
wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/adapta-kde/master/install.sh | sh
```
Para más información puedes visitar el github del proyecto:

[https://github.com/PapirusDevelopmentTeam/adapta-kde
](URL)

En las preferencias del sistema en comportamiento del espacio de trabajo me gusta activar Ventanas tambaleantes el efecto Lámpara mágica y el cambiador de tareas me gusta la opción de selección en rueda.

**NOTA:** El único widget que adiciono aparte a la barra de menú de aplicaciones es el de escritorios virtuales que como vez tengo 4 por defecto. Esto es meramente estético pues casi ni lo uso pero si me facilita cambiar a veces de escritorio para que no vean algo que estoy haciendo.

##Esta guía aún no está finalizada.##
