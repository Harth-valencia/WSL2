

# WSL2
## ARQUITECTURA

Ejecución de aplicaciones de GUI de Linux en el Subsistema de Windows para Linux
Artículo.


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

Controlador instalado para vGPU

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

DOCKER

![docker](https://user-images.githubusercontent.com/101934945/187725020-1176f544-a96e-47c9-be70-b20d241ec16b.png)


Arquitectura Docker
La arquitectura Docker es una arquitectura cliente-servidor, dónde el cliente habla con el servidor (que es un proceso daemon) mediante un API para poder gestionar el ciclo de vida de los contenedores y así poder construir, ejecutar y distribuir los contenedores.

El hecho de que el cliente se comunique con el servidor mediante el API hace que el cliente y servidor puedan estar en la misma máquina comunicándose mediante sockets de UNIX o bien en máquinas diferentes comunicándose mediante un end-point en la red.

Arquitectura Docker

Docker está escrito en GO, aunque también se aprovecha de muchas de las capacidades del kernel Linux, como namespaces, cgroups, y el sistema de ficheros UnionFS.

Dentro de los elementos de la Arquitectura Docker encontramos dos, por un lado el elemento principal de la arquitectura Docker que es el Docker Engine y por otro el Registro Docker.

Docker Engine
El Docker Engine es la aplicación cliente-servidor que implementa Docker. Esta aplicación tiene tres componentes:

Servidor, es el proceso principal de Docker y que funciona como proceso demonio del sistema. Es el encargado de gestionar los objetos que hay en Docker como imágenes, contenedores, redes y volúmenes. Se representa mediante el comando dockerd.
API Rest, es un API Rest que nos permite acceder a las capacidades del servidor y ejecutar comandos sobre él. Podemos utilizar un simple curl para acceder a las capacidades del API de Docker
Cliente, es la línea de comandos representada por el comando docker. El cliente habla vía el API Rest para poder ejecutar los comandos. Es lo que utilizaremos para poder ir gestionando el ciclo de vida de nuestras imágenes y contenedores.
Docker Engine
Registros Docker
Además del Docker Engine la Arquitectura Docker contiene otro elemento importante que son los registros Docker.

Los registros Docker (Docker Registry) son los que almacenan imágenes Docker. El Docker Hub es un registro público que almacena múltiples imágenes, algunas de ellas certificadas por Docker.

Por defecto, cuando ejecutamos un comando para crear un contenedor, se buscan las imágenes en Docker Hub. Si bien se pueden crear registros privados de imágenes mediante Docker Datacenter (DDC) y Docker Trusted Registry (DTR)

