# Guia-Instalar-Arch-Linux-VirtualBox-

## Bloque 1

### 1 Descargar la ISO de la página oficial:
-  https://archlinux.org/download/
-  <img src= "Imagenes/0- InstalacionEnVirtualBox/1- isoArch.png" width="800">


### 2 Una vez descargada, crear una nueva Maquina Virtual en VirtualBox pulsando la tecla "Nueva".
- Una vez configurada, seleccionamos "Siguiente"
  <img src= "Imagenes/0- InstalacionEnVirtualBox/2- crearNueva.png" width="800">


### 3 A continuacion, configuramos el tamaño de la RAM, el Nº de CPU virtuales/procesadores.
  <img src= "Imagenes/0- InstalacionEnVirtualBox/3- tamaño1.png" width="800" alt="EJEMPLO: Configuracion de la RAM y los procesadores">

### 4 Escogemos un tamaño de disco duro virtual.
- Por defecto son 8GB 
- pero hay que subir más la cantidad (no afecta al tamaño de memoria de nuestro ordenador)
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
 sudo pacman -Sy
```
