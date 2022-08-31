![docker](https://user-images.githubusercontent.com/101934945/187725020-1176f544-a96e-47c9-be70-b20d241ec16b.png)

# WSL2
ARQUITECTURA

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


