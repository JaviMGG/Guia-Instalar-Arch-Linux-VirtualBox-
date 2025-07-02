# Guia-Instalar-Arch-Linux-VirtualBox-

## Bloque 1
### 1 Descargar la ISO de la página oficial:
-  https://archlinux.org/download/
  <img src= "Imagenes/0- InstalacionEnVirtualBox/1- isoArch.png" width="800">

### 2 Una vez descargada, crear una nueva Maquina Virtual en VirtualBox pulsando la tecla "Nueva".
- Una vez configurada, seleccionamos "Siguiente"
  <img src= "Imagenes/0- InstalacionEnVirtualBox/2- crearNueva.png" width="800">

### 3 A continuacion, configuramos el tamaño de la RAM, el Nº de CPU virtuales/procesadores.
  <img src= "Imagenes/0- InstalacionEnVirtualBox/3- tamaño1.png" width="800" alt="EJEMPLO: Configuracion de la RAM y los procesadores">

### 4 Escogemos un tamaño de disco duro virtual.
- Por defecto son 8GB 
- Hay que subir más la cantidad (no afecta al tamaño de memoria de nuestro ordenador)
  <img src= "Imagenes/0- InstalacionEnVirtualBox/4- tamaño2.png" width="800" alt="EJEMPLO: Configuracion Del disco duro virtual">
- Por ultimo, nos saldrá una ventana que muestra la configuracion que hemos hecho, si está todo correcto, pulsar "Confirmar"


## Bloque 2
### 1 "Enceder ArchLinux"
- Una vez hemos seleccionado "Iniciar" en VirtualBox, nos aparecerá la siguiente imagen en poco tiempo. 
- Esta imagen es un "instalador", nos permite reiniciar el sistema, apagarlo, instalar ArchLinux.... Por defecto estará en la primera opción que nos permitirá instalar, pulsamos enter. 
- (IMPORTANTE, si queremos subir o bajar, hay que usar las teclas de las flechas del teclado)
  <img src= "Imagenes/1- Inicio/1- inicio1.png" width="800">

### 2 Empezar con la instalacion
- Esta imagen de aquí es Arch Linux que por defecto usa el "super usuario" ROOT
  <img src= "Imagenes/1- Inicio/2- inicio2.png" width="800">
- Ahora, comenzamos con la "Autentica Instalación"



## Bloque 3
- Préviamente a instalar toda las configuraciones de nuestro futuro sistema, tenemos que actualizarlo. Para ello usamos el siguiente comando de consola:
```bash
 sudo pacman -Syu
```
### Comando desglosado:
- sudo:        Ejecuta el comando como superusuario (root), necesario para modificar el sistema.
- pacman:      Es el gestor de paquetes de Arch Linux. Se usa para instalar, eliminar, actualizar y administrar paquetes.
- -S: Opción de "sync": sincroniza paquetes desde los repositorios. Se usa para instalar o actualizar.
- -y: Opción de "refresh": actualiza la base de datos local de paquetes desde los servidores remotos.
- -u: Upgrade. Actualiza todos los paquetes del sistema que tienen una versión más nueva en los repositorios.

A continuacion, ejecutamos el siguiente comando para empezar a instalar:
  ```bash
  archinstall
  ```

## Bloque 4
- Esto es el resultado de ejecutar "archinstall", es una forma "más sencilla" de instalar Arch Linux. 
- Vamos a ir por partes y centrándonos en las "esenciales"
  <img src= "Imagenes/3- ArchInstall/Entorno Grafico/1- perfil1.png" width="800">

### Idioma
- Escogemos el idioma (en mi caso Spanish)
  <img src= "Imagenes/3- ArchInstall/Idioma/idioma.png" width="800">

### Localidades
-  Distribución del teclado: disposición física del teclado dependiendo del pais (españa = es), por defecto es "en" (inglés)
-  Idioma Local: Define el idioma del sistema para mensajes, menús y errores. (es_ES (Español de España), en_US (Inglés de EE.UU.))
-  Codificación local: Establece la codificación de caracteres usada por el sistema. Recomendado: UTF-8
  <img src= "Imagenes/3- ArchInstall/Ubicacion/ubicacion.png" width="800">

### Configuración del disco
-  Seleccionamos "Particionamiento"
  <img src= "Imagenes/3- ArchInstall/Particionamiento/1- particionamiento1.png" width="800">

-  A continuacion vemos 3 de las posibles opciones para particionar:

   #### Utilizar un diseño de partición predeterminado de mejor esfuerzo (escogeré esta)
   - Automatiza el proceso de particionado del disco usando una configuración estándar que intenta ser la más adecuada.
   - Crea automáticamente /, swap, y a veces /home con tamaños razonables según el tamaño del disco.
⚠️ Advertencia: Esta opción puede borrar todo el disco.

   #### Particion manual
   - Permite al usuario definir las particiones manualmente (crear, borrar, cambiar tamaño, asignar puntos de montaje).
   - Requiere conocimiento sobre:
     Tipos de particiones (ext4, swap, etc.).
     Puntos de montaje (/, /home, /boot, etc.).
     Sistemas de archivos.
   #### Configuración premontada
   - Usa una configuración de disco ya existente (ya particionado y montado previamente).
   - Ideal para: Sistemas donde ya hiciste el particionado/montaje manual (por ejemplo, con fdisk + mount).

  <img src= "Imagenes/3- ArchInstall/Particionamiento/2- particionamiento2.png" width="800">
