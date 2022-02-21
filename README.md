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

![Imagen4](imgs/Imagen4.png)
Creación de la carpeta. 
![Imagen5](imgs/Imagen5.png)
Uso del comando mount, el cual es necesario ejecutar con sudo pues se necesitan permisos de super usuario ya que estos comandos modifican directamente el hardware. 
Al utilizar el comando mount de esta manera, la carpeta no será creada con todos los permisos disponibles para el usuario. Para poder obtener todos los permisos, hay que desmontar la USB, se debe utilizar el umask, y volver a ejecutar el comando mount con parámetros adicionales. 

![Imagen6](imgs/Imagen6.png)
Uso del comando mount con parámetros adicionales, como se puede observar la carpeta ya cuenta con todos los permisos. 
![Imagen7](imgs/Imagen7.png)


## Paso 3
Cambiar aquí !

![Imagen8](imgs/Imagen8.png)

## Paso 4
Para este paso,  utilizamos el comando fdisk -l /dev/sda. El comando nos permitirá visualizar las particiones de la unidad sda, la cual es el disco duro virtual donde está contenido el sistema operativo. 

![Imagen9](imgs/Imagen9.png)
![Imagen10](imgs/Imagen10.png)
![Imagen11](imgs/Imagen11.png)
![Imagen12](imgs/Imagen12.png)
![Imagen13](imgs/Imagen13.png)
![Imagen14](imgs/Imagen14.png)
![Imagen15](imgs/Imagen15.png)
![Imagen16](imgs/Imagen16.png)
![Imagen17](imgs/Imagen17.png)
![Imagen18](imgs/Imagen18.png)
![Imagen19](imgs/Imagen19.png)
![Imagen20](imgs/Imagen20.png)
![Imagen21](imgs/Imagen21.png)
![Imagen22](imgs/Imagen22.png)
![Imagen23](imgs/Imagen23.png)
![Imagen24](imgs/Imagen24.png)
![Imagen25](imgs/Imagen25.png)

