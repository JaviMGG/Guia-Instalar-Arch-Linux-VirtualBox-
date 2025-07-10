# Bloque 1
### 1 Descargar la ISO de la página oficial:
- https://archlinux.org/download/
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


# Bloque 2
### 1 "Enceder ArchLinux"
- Una vez hemos seleccionado "Iniciar" en VirtualBox, nos aparecerá la siguiente imagen en poco tiempo. 
- Esta imagen es un "instalador", nos permite reiniciar el sistema, apagarlo, instalar ArchLinux.... Por defecto estará en la primera opción que nos permitirá instalar, pulsamos enter. 
- (IMPORTANTE, si queremos subir o bajar, hay que usar las teclas de las flechas del teclado)
  <img src= "Imagenes/1- Inicio/1- inicio1.png" width="800">

### 2 Empezar con la instalacion
- Esta imagen de aquí es Arch Linux que por defecto usa el "super usuario" ROOT
  <img src= "Imagenes/1- Inicio/2- inicio2.png" width="800">
- Ahora, comenzamos con la "Autentica Instalación"



# Bloque 3
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

# Bloque 4
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

  <img src= "Imagenes/3- ArchInstall/Particionamiento/2- particionamiento2.png" width="800">

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
     
#### Al seleccionar cualquiera de las opciones, veremos la siguiente imagen que muestra la informacion sobre un dispositivo de almacenamiento cuyos detalles son los siguientes:

<img src= "Imagenes/3- ArchInstall/Particionamiento/3- particionamiento3.png" width="800">
 
-  Node1: Indica el nombre del nodo o dispositivo, que en este caso es "RTR URDK HMRD015K" (marcado con > y un checkbox vacío [ ]).
-  Path: La ruta del dispositivo es /dev/sda.
-  Type: El tipo del dispositivo es "sest" (posiblemente un error tipográfico o formato específico).
-  Size: El tamaño total del dispositivo es de 20.2 GiB.
-  Free space: El espacio libre disponible es de 28,917 unidades (no se especifica si son bytes, sectores, etc.).
-  Sector size: El tamaño del sector es de 512 bytes.
-  Read only: El dispositivo no es de solo lectura (False).

#### Clicamos enter y aparecerá la siguiente ventana con distintos tipos de sistemas:
<img src= "Imagenes/3- ArchInstall/Particionamiento/4- particionamiento4.png" width="800">

- Btrfs (ESCOGIDA ESTA): Ideal para backups (hace snapshots fácilmente) y discos en RAID (une varios discos como uno solo).
- ext4: El más usado en Linux, buen equilibrio entre velocidad y estabilidad. Perfecto para discos duros normales.
- XFS: Superrápido para servidores y archivos enormes (como bases de datos o vídeos 4K).
- F2FS: Optimizado para SSD y móviles, alarga su vida y los hace más rápidos.

#### Al escoger la de btrfs nos saldrá la siguientes pestañas:
<img src= "Imagenes/3- ArchInstall/Particionamiento/5- brtfs.png" width="800">
<img src= "Imagenes/3- ArchInstall/Particionamiento/6- brtfs2.png" width="800">

### La diferencia entre cada opcion es:
#### Usar subvolúmenes (Sí): (RECOMENDADO)
- Crea una estructura organizada (ej: /@ para el sistema, /@home para datos).
- Permite hacer snapshots independientes de cada subvolumen (ej: backup de /home sin afectar el sistema).
- Ideal para rollbacks o backups selectivos.

#### No usar subvolúmenes (No):
- Todo se guarda en una sola partición sin división lógica.
- Menos flexible para gestionar snapshots o recuperaciones.

#### Usar compresión:
- Reduce el tamaño de los archivos (ahorra espacio en disco).
- Mejora velocidad de lectura (especialmente útil en SSD).
- Soporta algoritmos como zstd (equilibrio entre compresión y rendimiento).
- Permite snapshots y evita corrupción de datos.
- Pequeña sobrecarga en escrituras (ideal para archivos normales).

#### Desactivar compresión:
- Mayor velocidad en escrituras (útil para bases de datos o VMs).
- Pierdes snapshots y checksums (mayor riesgo de corrupción).

### Cuenta del usuario
- (clicamos con enter para acceder)
  <img src= "Imagenes/3- ArchInstall/Cuenta de Usuario/1- usuario.png" width="800">
- Se nos muestra la siguiente imagen:
  <img src= "Imagenes/3- ArchInstall/Cuenta de Usuario/2- usuario2.png" width="800">

#### Añadir un usuario
- Sirve para crear un nuevo usuario ("crear una cuenta")
- Nombre de usuario (lo dice el nombre)
- Contraseña y "Confirmar contraseña" TIENEN QUE SER LA MISMA PALABRA/CONTRASEÑA
  <img src= "Imagenes/3- ArchInstall/Cuenta de Usuario/3- usuario3.png" width="800">
- Al escribirlo correctamente, nos preguntará si queremos que el usuario sea un "superusuario"(sudo)
  <img src= "Imagenes/3- ArchInstall/Cuenta de Usuario/4- usuario4.png" width="800">

  #### Ser superusuario:
  - Instalar/eliminar software (apt install, dnf remove).
  - Editar configuraciones del sistema (ej: /etc/fstab).
  - Reiniciar servicios (systemctl restart servicio).
  - Cambiar dueños/permisos de cualquier archivo (chown, chmod).
  - Apagar/reiniciar el sistema.

  #### No ser superusuario:
  -  Acceder y modificar solo tus archivos personales (en /home/usuario).
  -  Usar programas instalados para todos los usuarios.
  -  Cambiar configuraciones que no afecten al sistema.
- Independientemente de la opcion escogida, nos mostrará la siguiente escena/situación
  <img src= "Imagenes/3- ArchInstall/Cuenta de Usuario/5- usuario5.png" width="800">
  - Ahora actualizada podemos ver los detalles que hemos configurado:
      - Usuario 
      - Contraseña
      - Permisos de superusuario (True si ES SUPERUSUARIO, False en caso contrario)
  - Clicamos Enter en Confirmar y salir y volvemos a la pestaña original
     
#### Confirmar y salir
- Una vez creado el usuario, poder guardarlo y volver atrás
#### Cancelar
- Volver atrás SIN guardar el usuario

### Perfil
 <img src= "Imagenes/3- ArchInstall/Entorno Grafico/1- perfil1.png" width="800">
 #### Clicamos enter y nos aparece esto:
 <img src= "Imagenes/3- ArchInstall/Entorno Grafico/2- perfil2.png" width="800">
 - Tipo (escoger tipo de entorno grafico)
 - Regresar (volver atras)
 Al escoger "Tipo" nos aparece la siguiente opcion:
 <img src= "Imagenes/3- ArchInstall/Entorno Grafico/3- perfil3.png" width="800">
 - Desktop: Entorno gráfico completo para uso general.
 - Minimal: Sistema básico sin extras, ideal para personalizar.
 - Server: Configuración para servidores sin gráficos.
 - Xorg: Servidor gráfico sin entorno de escritorio predefinido.
 
 
