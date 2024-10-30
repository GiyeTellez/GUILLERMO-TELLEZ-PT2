<h1>MANUAL PARA INSTALAR OWNCLOUD EN UBUNTU</h1>

Primero abrimos la terminal desde nuestro dispositivo
  Actualizamos nuestra maquina usando los siguientes comandos en la terminal
<ol>  
<li><h1>"sudo apt update"</h1> La terminal te pedira una contraseña, escribe la contraseña que usas para entrar en tu usuario del pc</li>
<li><img src="Imatge enganxada.png" alt="Contraseña primer comando"></li>
<li>"sudo apt upgrade" Una vez escrito este codigo llegara un momento donde te pregunte si deseas continuar con la instalacion. Pulsa la tecla "S" y "ENTER" para continuar</li>
<li><img src="Imatge enganxada (2).png" alt="Contraseña primer comando"></li>
</ol>

Una vez actualizada la maquina instalaremos el servidor web apache utilizando el siguiente comando 

"sudo apt install -y apache2"

Una vez tenemos el apache instalado es cruicial instalar la base de datos. Para ello escribiremos el siguiente comando de nuevo en la terminal

"sudo apt install -y mysql-server" De nuevo la termnial te pedira una contraseña. 

Escribe la contraseña que utilices para entrar al usuario del pc
<img src="Contraseña Base de datos.png" alt="Contraseña que te pide cuando la base de datos">

Una vez instalado el servidor apache y la base de datos instalaremos algunas librerias de php (el lenguaje principal que usan las aplicaciones). Para ello utilicaremos los siguientes comandos
"sudo apt install -y php libapache2-mod-php"
"sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl"

