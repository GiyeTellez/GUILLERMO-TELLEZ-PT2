<h1>MANUAL PARA INSTALAR OWNCLOUD EN UBUNTU</h1>

<h2>Primero abrimos la terminal desde nuestro dispositivo</h2>
  Actualizamos nuestra maquina usando los siguientes comandos en la terminal
<ol>  
<li><h3>"sudo apt update"</h3> La terminal te pedira una contraseña, escribe la contraseña que usas para entrar en tu usuario del pc</li>
<img src="Imatge enganxada.png" alt="Contraseña primer comando">
<li><h3>"sudo apt upgrade"</h3> Una vez escrito este codigo llegara un momento donde te pregunte si deseas continuar con la instalacion. Pulsa la tecla "S" y "ENTER" para continuar</li>
<img src="Imatge enganxada (2).png" alt="Contraseña primer comando">
</ol>

<h2>Una vez actualizada la maquina instalaremos el servidor web apache utilizando el siguiente comando</h2> 

<h3>"sudo apt install -y apache2"</h3>

<h2>Una vez tenemos el apache instalado es cruicial instalar la base de datos. Para ello escribiremos el siguiente comando de nuevo en la terminal</h2>

<h3>"sudo apt install -y mysql-server"</h3> De nuevo la termnial te pedira una contraseña. 

Escribe la contraseña que utilices para entrar al usuario del pc
<img src="Contraseña Base de datos.png" alt="Contraseña que te pide cuando la base de datos">

<h2>Una vez instalado el servidor apache y la base de datos instalaremos algunas librerias de php (el lenguaje principal que usan las aplicaciones). Para ello utilicaremos los siguientes comandos</h2>
<ol>
<li><h3>"sudo apt install -y php libapache2-mod-php"</h3></li>
<li><h3>"sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl"</h3></li>
    De nuevo tendras que volver a poner la contraseña con la que entras al usuario
    <img src="Contraseña Libreria 2.png" alt="Descripció de la imatge">
</ol>
<h2>Una vez hemos echo todos los pasos anteriores reiniciamos el apache con el siguiente comando</h2>
<h3>"sudo systemctl restart apache2"</h3>

<h2>Ahora es momento de entrar en la consola, utiliza el comando...</h2>
<h3>"sudo mysql"</h3>

<h2>Una vez estamos dentro de la consola vamos a crear una base de datos bajo el nombre "bbdd". Es importante recordar ese nombre para un futuro para crearla usa el siguiente codigo</h2>
<h3>"CREATE DATABASE bbdd;"</h3>

<h2>Todavia dentro de la consola...
  <img src="Captura desde 2024-11-06 13-13-31.png" alt="Captura de la consola antes de crear el user">
  
  No hay que olvidarnos de que se tiene que identificar la IP desde donde se accedera a la base de datos. En este caso "localhost" Para ello usa el siguiente comando</h2>
<h3>"CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';"</h3>
La contraseña que escribas entre las ''sera la contraseña de tu base de datos
<img src="Onde Ta la contraseña.png" alt="Ahi esta la contraseña">

<h2>Todavia dentro de la consola tendria que verse algo así...
  <img src="Screen despues de crear el usuario.png" alt="Captura de la consola despues de crear el user">

<h2>Una vez hemos creado el usuario es necesario darle permisos de administrador, para ello utilizamos el siguiente comando sin salir de la consola</h2>
<h3>"GRANT ALL ON bbdd.* to 'usuario'@'localhost';"</h3>
<h2>Si todos los pasos se han realizado correctamente tendria que verse algo asi</h2>

<img src="Captura desde 2024-11-06 13-13-31.png" alt="Descripció de la imatge">

<h2>Ahora ya hemos acabado con la base de datos, solo nos queda salir de ella usando el siguiente sencillo comando</h2>
<h3>"exit"</h3>

<h2>Con la intención de comprobar que sea posible entrar a la base de datos usando la contraseña que anteriormente hemos decidido utilizaremos el siguiente comando</h2>
<h3>"mysql -u usuario -p"</h3>
Una vez ejecutado el comando te pedirá una contraseña, escribe la contraseña que pusiste anteriormente
<img src="Onde Ta la contraseña.png" alt="Ahi esta la contraseña">

<h2>Salgamos de la base de datos para continuar con el siguiente paso usando el comando</h2>
<h3>"exit"</h3>

<h2>Ahora es momento de descargar los archivos de la aplicación web. Primero descarga el siguiente archivo</h2>

<h3>"https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip"</h3>

<h2>Una vez descargado utilizaremos los siguientes comandos para descomprimir en el directorio /var/www/html los archivos de la aplicación web. En el siguiente comando tienes que substituir "Nombre del archivo" por el nombre del archivo que has descargado con el enlace anterior, por ultimo recuerda que se da por hecho que el idioma de su PC es español, en caso de que no lo sea donde pone "Descargas" debera cambiarlo por la palabra traducida al idioma en el que tenga el PC</h2>

<h3>sudo cp ~/Descargas/Nombre del archivo /var/www/html</h3>

<h2>El siguiente paso es entrar en el directorio /var/www/html con el siguiente comando</h2>
<h3>"cd /var/www/html"</h3>
Esto significa que esta dentro del directorio
<img src="Entrao en el directorio.png" alt="Significa que estas dentro del directorio">

<h2>Una vez en el directorio descomprimimos los archivos con este comando pero de nuevo hay que cambiar el "Nombre del archivo" por el nombre del archivo que se ha creado anteriormente con la aplicacion web</h2>
<h3>"sudo unzip "Nombre del archivo"</h3> 

<h2>Una vez descomprimidos toca copiar los archivos en la carpeta "/var/www/html". Para ello utiliza el siguiente comando pero recuerda que tienes que substituir "Nom del directori" por el nombre de la carpeta donde se ha descomprimido el archivo</h2>
<h3>"sudo cp -R "Nom del directori"/. /var/www/html"</h3>

<h2>Ahora debemos eliminar la carpeta que ya esta descomprimida, usa el siguiente comando pero recuerda cambiar "Nombre de la carpeta" por el nombre de tu carpeta</h2>
<h3>"sudo rm -rf "Nombre de la carpeta"/"</h3>

<h2>Ahora elimina el archivo index.html del apache2 con el siguiente comando</h2>
<h3>"sudo rm -rf /var/www/html/index.html"</h3>

<h2>Es necesario aplicar permisos a nuestras aplicaciones web, para ello utilizaremos el primer comando para entrar en "/var/www/html" y posteriormente los dos siguientes para aplicar los permisos</h2>
<h3>"cd /var/www/html"</h3>
<h3>"sudo chmod -R 775 ."</h3>
<h3>"sudo chown -R usuario:www-data ."</h3>

<h2>Por ultimo debemos instalar la vesión 7.4 de PHP a Ubuntu 24.04. Para ello utilizaremos los siguientes comandos para realizar las siguientes funciones</h2>
<h3>"sudo apt install software-properties-common -y"</h3> Instalar los requisitos previos de PPA
<h3>"LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y"</h3> Instalar las herramientas necesarias para trabajar con PPA
<h3>"sudo apt update"</h3> Actualizar el repositorio
<ul>
    <li><h3>"sudo apt install php7.4 -y"</h3></li>
    <li><h3>"sudo apt install -y php libapache2-mod-php7.4"</h3></li>
    <li><h3>"sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl"</h3></li>
    Instalar librerias de PHP de la versión 7.4
</ul>

