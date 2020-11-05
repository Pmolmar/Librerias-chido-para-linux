# Utilidades basicas para Linux
En este repo tratare algunas funciones y herramientas que podemos anadir facilmente a Linux.

## Creacion de ejecutables (accesos directos)
Si tenemos un archivo que queremos ejecutar como si de un programa se tratara en el escritorio:
- El archivo ha de tener permisos de ejecucion.
- Crear con su mismo nombre un .desktop ej(script.sh.desktop).
- El .desktop tambien a de tener permisos de ejecucion y contener lo siguiente:

Codigo para poder crear un fichero ejecutable:
~~~bash
[Desktop Entry]	
Type=Application,Link o Directory #define el tipo de uso que queremos darle
Encoding=UTF-8	#Codificacion usada
Name= #Nombre
Comment= #Comentario
Exec= #Comando con el que se inicia el fichero ejecutable, ej: bash /home/desktop/pepe/script.sh
Icon= #Icono
Terminal= #Indican si la terminal es usada (true or false)
~~~
De todo lo anterior para que puede funcionar solo es nesesario el Type,Exec,Terminal y Name

## Configuracion de drive (outdated)
`grive`, libreria para poder sincronizar carpetas con Google Drive.

Descargar grive
~~~bash
sudo apt-add-repository ppa:nilarimogard/webupd8
sudo apt-get update
sudo apt-get install grive 
~~~
- `grive -a` en el directorio que quieras sincronizar.
- `grive sync` para sincronizarlas o.
- `grive --dry-run` para ver lo que se va a sincronizar.


Si no funcinoa seguir pasos en: 
http://yourcmc.ru/wiki/Grive2#Installation

## Autocompletar mayus terminal
Esto permite poder ignorar si se empieza por mayusculas o minusculas al tabular.  
En el fichero --> `/etc/inputrc: set completion-ignore-case on`

## Generacion de SSH para GH
Un paso: `ssh-keygen -t rsa -b 4096 -C "correo@mail.com"`, elegimos nombre y si queremos contrasena.  
Despues en ~/.ssh/ tendremos el .pub que nesecitaremos para GH.