## ¿Cómo desinstalo una distribución de WSL?

Para quitar una distribución de WSL y eliminar todos los datos asociados a esa distribución de Linux, ejecutar
```powershell
wsl --unregister <distroName> 
``` 
Además, puede desinstalar la aplicación de distribución de Linux en la máquina igual que cualquier otra aplicación de la tienda.

![tux](img/tux.png)
## ¿Cómo puedo hacer una copia de seguridad de mis distribuciones de WSL o moverlas de una unidad a otra?

La mejor manera de realizar copias de seguridad o mover las distribuciones es a través de los comandos de exportación e importacióndisponibles en Windows versión 1809 y posteriores. Puedes exportar toda la distribución a un tarball mediante el comando
```powershell  
wsl --export <Distribution Name> <FileName>
```
Después, puede volver a importar esta distribución en WSL mediante el 

```powershell  
wsl --import <Distribution Name> <InstallLocation> <FileName>
```

Puede asignar un nombre a una nueva ubicación de unidad para la importación, lo que le permite realizar copias de seguridad y guardar los estados de (o mover) las distribuciones de WSL.








<a href="README.md"><img src="img/arrow.png" alt="Volver al README" width="100"></a>