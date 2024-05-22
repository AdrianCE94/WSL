## Instalación de Linux en Windows con WSL
Los desarrolladores pueden acceder a la potencia de Windows y Linux al mismo tiempo en una máquina Windows. Subsistema de Windows para Linux (WSL) permite a los desarrolladores instalar una distribución de Linux (como Ubuntu, OpenSUSE, Kali, Debian, Arch Linux, etc.) y usar aplicaciones, utilidades y herramientas de línea de comandos de Bash directamente en Windows, sin modificar, sin la sobrecarga de una máquina virtual tradicional o una configuración de arranque dual.

## Prerrequisitos

Para ejecutar los siguientes comandos, debe ejecutar Windows 10 versión 2004 y posteriores (compilación 19041 y posteriores) o Windows 11. Si está en versiones anteriores, consulte la [página de instalación manual](https://learn.microsoft.com/es-es/windows/wsl/install-manual).


## Comando de instalación de WSL

Ahora puede instalar todo lo que necesita para ejecutar WSL con un solo comando. Abra PowerShell o el símbolo del sistema de Windows como administrador; para ello, haga clic con el botón derecho y seleccione "Ejecutar como administrador", escriba el comando `wsl --install` y reinicie la máquina.

### PowerShell

```powershell
wsl --install

Este comando habilitará las características necesarias para ejecutar WSL e instalará la distribución Ubuntu de Linux. (Esta distribución predeterminada se puede cambiar).

La primera vez que inicie una distribución de Linux recién instalada, se abrirá una ventana de la consola y se le pedirá que espere a que los archivos se descompriman y se almacenen en el equipo. Todos los inicios posteriores deberían tardar menos de un segundo en completarse.
````poweshell
wsl --list --online para ver una lista de distribuciones disponibles y ejecute 
wsl --install -d <DistroName> para instalar una distribución.
```
## Cambio de la distribución predeterminada de Linux instalada

De forma predeterminada, la distribución de Linux instalada será Ubuntu. Se puede cambiar mediante la marca `-d`.

Para cambiar la distribución instalada, escriba: `wsl --install -d <Nombre de la Distribución>`. Reemplace `<Nombre de la Distribución>` por el nombre de la distribución que desea instalar.

Para ver una lista de las distribuciones de Linux disponibles para descargar a través de la tienda en línea, escriba `wsl --list --online` o `wsl -l -o`.

Para instalar distribuciones de Linux adicionales después de la instalación inicial, también puede usar el comando `wsl --install -d <Nombre de la Distribución>`.

### Sugerencia

Si desea instalar distribuciones adicionales desde dentro de una línea de comandos de Linux/Bash (en lugar de hacerlo desde PowerShell o el símbolo del sistema), debe usar `.exe` en el comando `wsl.exe --install -d <Nombre de la Distribución>` o para enumerar las distribuciones disponibles: `wsl.exe -l -o`.

## Comprobación de la versión de WSL que se está ejecutando

Para enumerar las distribuciones de Linux instaladas y comprobar en qué versión de WSL está establecida cada una, puede escribir el comando `wsl -l -v` en PowerShell o en el Símbolo del sistema de Windows.

Para establecer la versión predeterminada en WSL 1 o WSL 2 cuando se instala una nueva distribución de Linux, use el comando `wsl --set-default-version <Número de Versión>`, reemplazando `<Número de Versión>` por 1 o 2.

Para establecer la distribución predeterminada de Linux que se usa con el comando `wsl`, escriba `wsl -s <Nombre de la Distribución>` o `wsl --set-default <Nombre de la Distribución>`, reemplazando `<Nombre de la Distribución>` por el nombre de la distribución de Linux que le gustaría usar. Por ejemplo, en PowerShell/CMD, escriba `wsl -s Debian` para establecer la distribución predeterminada en Debian. Ahora, al ejecutar `wsl npm init` desde PowerShell, se ejecutará el comando `npm init` en Debian.

Para ejecutar una distribución de WSL específica desde PowerShell o el Símbolo del sistema de Windows sin cambiar la distribución predeterminada, use el comando `wsl -d <Nombre de la Distribución>`, reemplazando `<Nombre de la Distribución>` por el nombre de la distribución que desea usar.

+  más COMANDOS [aqui]( https://learn.microsoft.com/es-es/windows/wsl/basic-commands)

# DIFERENCIAS
## WSL 1

- **Arquitectura:** Basada en una traducción dinámica de llamadas de sistema de Linux a llamadas de sistema de Windows.
- **Kernel:** Utiliza el kernel de Windows para ejecutar binarios de Linux.
- **Rendimiento de E/S:** Limitado por la traducción de llamadas de sistema y la implementación del sistema de archivos.
- **Rendimiento de red:** Depende de la pila de red de Windows.
- **Requisitos del sistema:** Funciona en todas las ediciones de Windows 10.
- **Integración:** Limitada con el sistema de archivos y la red de Windows.
- **Administración de recursos:** No ofrece control sobre la asignación de recursos de CPU y memoria para las distribuciones de Linux.

## WSL 2

- **Arquitectura:** Basada en una máquina virtual ligera.
- **Kernel:** Utiliza un kernel Linux completo.
- **Rendimiento de E/S:** Mejorado gracias a la virtualización de sistemas de archivos y el uso del kernel Linux.
- **Rendimiento de red:** Mejorado gracias a la integración de la pila de red de Linux.
- **Requisitos del sistema:** Requiere Windows 10 versión 1903 o posterior con virtualización habilitada.
- **Integración:** Mayor integración con el sistema de archivos y la red de Windows.
- **Administración de recursos:** Permite controlar la asignación de recursos de CPU y memoria para las distribuciones de Linux.

<br>
<br>
<a href="README.md"><img src="img/arrow.png" alt="Volver al README" width="100"></a>
