

# WSL2
## ARQUITECTURA

#### Ejecución de aplicaciones de GUI de Linux en el Subsistema de Windows para Linux.


En este artículo
Instalación de compatibilidad con aplicaciones de GUI de Linux
Ejecución de aplicaciones de GUI de Linux
Solución de problemas
Subsistema de Windows para Linux (WSL) ahora admite la ejecución de aplicaciones gui de Linux (X11 y Wayland) en Windows en una experiencia de escritorio totalmente integrada.

WSL 2 permite que las aplicaciones de GUI de Linux se sientan nativas y naturales para usarlas en Windows.

Inicio de aplicaciones de Linux desde el menú Inicio de Windows
Anclar aplicaciones De Linux a la barra de tareas de Windows
Uso de alt-tab para cambiar entre aplicaciones de Linux y Windows
Cortar y pegar entre aplicaciones de Windows y Linux
Ahora puede integrar aplicaciones de Windows y Linux en el flujo de trabajo para una experiencia de escritorio sin problemas.

Captura de pantalla de las aplicaciones de Linux y Windows abiertas en un escritorio

Instalación de compatibilidad con aplicaciones de GUI de Linux
Prerrequisitos
Tendrá que estar en Windows 11 compilación 22000 o posterior para acceder a esta característica.

#### Controlador instalado para vGPU

Para ejecutar aplicaciones de GUI de Linux, primero debe instalar el controlador que coincida con el sistema siguiente. Esto le permitirá usar una GPU virtual (vGPU) para que pueda beneficiarse de la representación de OpenGL acelerada por hardware.

Intel Controlador de GPU para WSL
AMD Controlador de GPU para WSL
NVIDIA Controlador de GPU para WSL
Instalación nueva: no hay instalación previa de WSL
Ahora puede instalar todo lo que necesita para ejecutar el Subsistema de Windows para Linux (WSL) si escribe este comando en PowerShell o el símbolo del sistema de Windows del administrador y, a continuación, reinicia la máquina.

PowerShell


wsl --install

Una vez que la máquina haya terminado de reiniciarse, la instalación continuará y se le pedirá que escriba un nombre de usuario y una contraseña. Esta será la credencial de Linux para la distribución de Ubuntu.

Ya está listo para empezar a usar aplicaciones de GUI de Linux en WSL.

# DOCKER

![docker](https://user-images.githubusercontent.com/101934945/187725020-1176f544-a96e-47c9-be70-b20d241ec16b.png)


## Arquitectura Docker
La arquitectura Docker es una arquitectura cliente-servidor, dónde el cliente habla con el servidor (que es un proceso daemon) mediante un API para poder gestionar el ciclo de vida de los contenedores y así poder construir, ejecutar y distribuir los contenedores.

El hecho de que el cliente se comunique con el servidor mediante el API hace que el cliente y servidor puedan estar en la misma máquina comunicándose mediante sockets de UNIX o bien en máquinas diferentes comunicándose mediante un end-point en la red.

Arquitectura Docker

Docker está escrito en GO, aunque también se aprovecha de muchas de las capacidades del kernel Linux, como namespaces, cgroups, y el sistema de ficheros UnionFS.

Dentro de los elementos de la Arquitectura Docker encontramos dos, por un lado el elemento principal de la arquitectura Docker que es el Docker Engine y por otro el Registro Docker.

##Docker Engine
El Docker Engine es la aplicación cliente-servidor que implementa Docker. Esta aplicación tiene tres componentes:

Servidor, es el proceso principal de Docker y que funciona como proceso demonio del sistema. Es el encargado de gestionar los objetos que hay en Docker como imágenes, contenedores, redes y volúmenes. Se representa mediante el comando dockerd.
API Rest, es un API Rest que nos permite acceder a las capacidades del servidor y ejecutar comandos sobre él. Podemos utilizar un simple curl para acceder a las capacidades del API de Docker
Cliente, es la línea de comandos representada por el comando docker. El cliente habla vía el API Rest para poder ejecutar los comandos. Es lo que utilizaremos para poder ir gestionando el ciclo de vida de nuestras imágenes y contenedores.
Docker Engine

## Registros Docker
Además del Docker Engine la Arquitectura Docker contiene otro elemento importante que son los registros Docker.

Los registros Docker (Docker Registry) son los que almacenan imágenes Docker. El Docker Hub es un registro público que almacena múltiples imágenes, algunas de ellas certificadas por Docker.

Por defecto, cuando ejecutamos un comando para crear un contenedor, se buscan las imágenes en Docker Hub. Si bien se pueden crear registros privados de imágenes mediante Docker Datacenter (DDC) y Docker Trusted Registry (DTR)


## Ventajas de WSL
El Subsistema de Windows para Linux puede ser útil tanto para usuarios aficionados que empiezan a dar los primeros pasos en este sistema operativo como para usuarios avanzados y administradores de sistemas.

La finalidad principal de WSL es permitir a los administradores de sistemas, y a los programadores, usar todas las herramientas y todos los servicios de Linux directamente desde Windows sin tener que virtualizar nada más ni montar infraestructuras complicadas. Al final, vamos a poder hacer todo lo que podríamos hacer si instalásemos Linux en una máquina virtual o en otro PC, y lo usáramos desde terminal o TTY. Todos los comandos de Linux deberían funcionar sin problema en Windows, como apt o dpkg. Incluso podremos compilar código directamente desde aquí con las ventajas que aporta Linux en este sentido.

Pero esta implementación también es útil para los usuarios que están dando sus primeros pasos dentro de los sistemas Linux. Gracias a ella, cualquier usuario podrá tener a su alcance todas las herramientas de Linux sin necesidad de tener que configurar ni virtualizar nada. Y, además, tendrá la seguridad de que, si algo sale mal, solo tendrá que reinstalar la distro en WSL, ya que Windows no se verá comprometido.

También hay que tener en cuenta que un problema persistente cuando ejecutamos Linux en su versión de escritorio es el soporte de hardware, especialmente en portátiles. Este problema es algo que no tendremos con WSL, ya nos aseguramos una compatibilidad total. Otra ventaja interesa es que, WSL nos va a permitir una verdadera interoperabilidad entre Windows y Linux, ya que vamos a poder explotar el sistema de archivos de Linux desde Windows y viceversa, así como iniciar programas desde las líneas de comando de uno y otro. Además, aunque aún no está disponible, en un futuro se podrán incluso ejecutar programas con interfaz gráfica.

WSL ya se ejecuta en Windows, por lo que no es necesario iniciar una máquina virtual cada vez que necesitamos de Linux, siempre y cuando no dependamos de una interfaz gráfica. Aunque una máquina virtual es más rápida y fácil de configurar, sigue siendo una máquina independiente al sistema operativo, aunque las limitaciones se reducen si activamos las opciones para compartir unidades y archivos entre el sistema operativo anfitrión y el invitado.

A la hora de compartir datos desde Windows con unidades con formato ext4, aunque Windows no ofrece soporte para este sistema de archivos, si lo vamos a encontrar en WSL, por lo que si, en algún momento nos vemos en la necesidad de acceder a unidades de nuestro equipo gestionados por el sistema de archivos de Linux, podemos recurrir a WSL para acceder sin necesidad de instalar ninguna aplicación adicional.

Si optamos por el arranque dual, debemos reservar espacio en el disco duro para instalar el sistema y asegurarse de tener medios de respaldo por si algo falla. Si queremos pasar de Windows a Linux o viceversa, la única solución para por reiniciar el equipo y arrancar con el sistema operativo que necesitamos en ese momento. Sin embargo, no es necesario si queremos acceder a los archivos que tengamos almacenados en ambas unidades, ya que Linux es compatible con el sistema de archivos NTFS y Windows es capaz de acceder a unidades ext4 a través de WSL, reduciendo así la obligación de reiniciar el equipo.
