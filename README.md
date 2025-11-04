# MailServer
Servidor de correo electrónico escrito en Java puro.<br>
<h1>Este proyecto se encuentra en desarrollo activo, por lo que no posee algunas características que facilitan su uso.</h1>

# Advertencia
  Este servidor tiene características de OpenRelay.<br> El uso indiscriminado puede acarrear acciones legales serias.

# Características  
<p>
  Aunque no está excento de fallos e implementaciones poco rigurosas con la seguridad, el servidor es capaz de operar en la mayoría de los cliente de correo electrónicos modernos. <br>
  Utiliza puertos no convencionales para facilitar su despliegue inmediato así como evitar la necesidad de permisos de administrador necesarios para habilitar los puertos tradicionales.<br>  
  Permite un funcionamiento en modo <b>LOCAL</b>, <b>RELAY</b> y <b>DIRECT</b>.<br> Actualmente opera bajo <b>LOCAL</b> y <b>DIRECT</b>. El modo <b>RELAY</b> depende de credenciales según servidor escogido.<br>
  Implementa protección contra DoS y SPAM, aunque es bastante básica. (Por defecto, se impuso una cantidad máxima de 20 destinatarios por correo)<br>
  Implementa gestión de correos básica con capacidad de almacenamiento en físico.<br>  
  Soporte para comandos: HELO, EHLO, AUTH PLAIN, AUTH LOGIN, STLS, STARTTLS, USER, PASS, APOP, LIST, UIDL, RETR, DELE, CAPA, STAT, DATA, RSET, NOOP y QUIT.
</p>

Los puertos destinados para cada servicio son:

* POP3  - 5556
* SPOP3 - 5557
* SMTP  - 5555
* SSMTP - 465*
  
*- el caso de SSMTP, es funcional, pero está sujeto a cambios en futuras versiones.<br>
Tipos de autenticación permitidas: 
* PLAIN
* LOGIN
* MD5 (APOP)
* SHA-256 (no estándar).

Se incluyó soporte para <b>TLSv1.2</b>, <b>TLSv1.3</b> y <b>STARTTLS</b>. Por defecto está activado <b>TLS</b><br>
  
# Compatibilidad
* Windows
* Linux
* MacOS

# Como usar

<p>    
  Ejecutar la siguiente línea en tu terminal de preferencia: <code>java -jar MailServer.jar</code><br>
  En caso de tener limitados niveles de acceso, el servidor no podrá ejecutarse correctamente.<br>
  Para configurar tu cliente de correo electrónico basta con ingresar los siguientes parámetros en la creación del buzón de cuenta:

  - Usuario: test
  - Contraseña: test
  - Servidor POP3, SMTP, SPOP3 y SSMTP: localhost o ip de tu red local.
</p>

# Por implementar
* UI que permita la gestión y configuración del servidor de forma amigable.
* Añadir soporte para SGBD: <b>MySQL</b>, <b>Postgres</b> o <b>SQLite3</b> (por definir)

# Por mejorar
* La implementación vía <b>RELAY</b> es funcional siempre y cuando poseas las credenciales correctas, ya sea de Google u otro servidor con estas capacidades.
* El modo <b>DIRECT</b> funciona con servidores que admitan direcciones públicas sin firmas válidas.
* Gestión de almacenamiento. Si bien, no hay límite en la cantidad de correos que puede manejar, se impuso un tamaño máximo de 10MB para envío y recibo.
* Protección contra <b>SPAM</b>
 
# Descargo de responsabilidad
<p>   
  No soy responsable por acción directa o indirecta del uso indebido que pueda darle.<br>
  Su implementación tiene exclusivamente un carácter educativo en la enseñanza de asignaturas de redes.
</p>
