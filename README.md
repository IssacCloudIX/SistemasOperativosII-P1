# SistemasOperativosII-P1
Repositorio de la práctica 1 de Sistemas Operativos II, acerca de como particionar una USB.

## Paso 2
Para montar y desmontar una usb, se utilizan los comandos mount y umount respectivamente. 
Al conectar nuestra usb ubuntu la monta automáticamente. En la imagen se puede observar la salida del comando lsblk, donde se ve que se encuentra montado el archivo sdb. 

![Imagen1](imgs/Imagen1.png)

Para desmontarla, ocupamos el siguiente comando:
umount /dev/sdb
donde /dev/sdb es la dirección del archivo bloque que contiene montado al usb.

![Imagen2](imgs/Imagen2.png)
Comando umount /dev/sdb utilizado.
![Imagen3](imgs/Imagen3.png)
Salida de lsblk después de desmontar la usb. 
Para montar la usb, necesitamos crear una carpeta la cual contendrá los archivos necesarios. Crearemos una carpeta en el home, llamada USB, la cual contendrá otra carpeta llamada USBPart. Ahí serán guardados los archivos de bloque. 

![Imagen4](imgs/Imagen5.png)
Creación de la carpeta. 
![Imagen5](imgs/Imagen6.png)
Uso del comando mount, el cual es necesario ejecutar con sudo pues se necesitan permisos de super usuario ya que estos comandos modifican directamente el hardware. 
Al utilizar el comando mount de esta manera, la carpeta no será creada con todos los permisos disponibles para el usuario. Para poder obtener todos los permisos, hay que desmontar la USB, se debe utilizar el umask, y volver a ejecutar el comando mount con parámetros adicionales. 

![Imagen6](imgs/Imagen7.png)
Uso del comando mount con parámetros adicionales, como se puede observar la carpeta ya cuenta con todos los permisos. 


![Imagen8](imgs/Imagen8.png)

![Imagen9](imgs/Imagen9.png)

## Paso 3 Puede cambiar. 
Para el paso 3 se vuelve a desplegar los archivos de bloque, y se mostrarán los archivos incluso los de aquellas unidades que no estén montadas. 

![Imagen7](imgs/Imagen3.png) 
Se puede observar el bloque /dev/sdb aunque no esté montado. 

## Paso 4
Para este paso,  utilizamos el comando fdisk -l /dev/sda. El comando nos permitirá visualizar las particiones de la unidad sda, la cual es el disco duro virtual donde está contenido el sistema operativo. 

![Imagen10](imgs/Imagen4.png)

## Paso 5
Para el paso 5 volveremos a utilizar el comando fdisk -l, pero ahora le pasaremos el archivo de bloques de la USB, para poder observar sus particiones. 

![Imagen11](imgs/Imagen10.png)

## Paso 6
Para realizar el paso 6, utilizaremos ahora el comando fdisk sin el -l, pues así esta herramienta nos permitirá modificar las particiones de la USB. 
Una vez en la herramienta, deberemos presionar la tecla d, y después el número de partición que queremos eliminar. En este caso repetiremos el proceso 4 veces, pues queremos eliminar las 4 particiones.

![Imagen11](imgs/Imagen11.png)

 Por último, se debe presionar la tecla w para guardar cambios. 

![Imagen12](imgs/Imagen12.png)

Se muestra la salida del comando fdisk -l después de borrar las particiones, y como se puede observar, ya no están. 

![Imagen13](imgs/Imagen13.png)

## Paso 7
Para este paso, de igual manera utilizaremos el comando fdisk. Ahora en lugar de utilizar la letra d, utilizaremos la letra n, la cual preguntará que tipo de partición queremos crear. Para crear una primaria (física) se debe escribir la letra p, para crear una extendida se debe escribir una letra e. Después nos preguntará el número de partición, los cuales irán del 1 al 4. Después preguntará el sector donde comenzará la partición, y por último preguntará de qué tamaño será la partición. A las primeras 3 particiones se les asignará el tamaño de 1 GiB.
Ejemplo partición 1 física:


![Imagen14](imgs/Imagen14.png)

Ejemplo partición 2:

![Imagen15](imgs/Imagen15.png)

Ejemplo partición 3:

![Imagen16](imgs/Imagen16.png)

Ejemplo partición 4 (extendida):

![Imagen17](imgs/Imagen17.png)
![Imagen18](imgs/Imagen18.png)
![Imagen19](imgs/Imagen19.png)
![Imagen20](imgs/Imagen20.png)
![Imagen21](imgs/Imagen21.png)
![Imagen22](imgs/Imagen22.png)
![Imagen23](imgs/Imagen23.png)
![Imagen24](imgs/Imagen24.png)
![Imagen25](imgs/Imagen25.png)

