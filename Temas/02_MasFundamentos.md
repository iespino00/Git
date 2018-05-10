# **02 MÁS ALLÁ QUE LOS FUNDAMENTOS**

## Diferencia entre commits y restauración de archivos:
****

**1.** **git diff** = Nos sirve para mostrar los cambios realizados si aun no se ha hecho el commit. 

  *  **git diff --staged** = Una vez que se hizo el **commit** y quiero ejecutar solamente **git diff**, no aparecerá nada, entonces es cuando se utiliza este comando.

**2.** **git reset HEAD archivo.extension** = Me elimina un archivo del staged por ejemplo ``git reset HEAD README.md`` me va a sacar el archivo readme.md del staged.

**3.** **git checkout -- archivo.extension** = Refresa al commit anterior el archivo que asignemos por ejemplo si ejecuto ``git checkout -- README.md`` me regresará al commit anterior de ese archivo.

**4.** **git commit -am "Agregar Archivos y Commit"** = Se agregan los archivos al stage y posteriormente se hace el commit con ese mensaje.


**5.** **git commit --amend -m "Mensaje de Commit a cambiar"** = Se modifica el mensaje del commit anteriormente agregado.

  * **git commit --amend** = Si no asigno el mensaje como el comando anterior, me abrirá un modo de edición donde tendré que presionar la tecla **A** , para posteriormente corregir el commit, y para guardar y salir del modo de edición presionaré la tecla ``Esc, : , wq + Enter``.Como se muestra en la imagen siguiente:

  ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/commitAmend.PNG "Git Reset --soft HEAD^")


**Si por accidente ya hice el commit, pero necesito realizar mas cambios en los archivos e incluirlos en el commit ya ejecutado, se utiliza el siguiente comando**

 * **git reset --soft HEAD^** = Nos permite regresar al commit anterior, **sin deshacer cambios**, solo para hacer adiciones a archivos y posteriormente volver a ejecutar el **add y el commit** y el **``HEAD^``** es para referenciar al commit anterior. Por ejemplo:

  ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_soft.PNG "Git Reset --soft HEAD^")

  **En la imagen anterior podemos observar que aparece una M de color verde y una M de color rojo significa que se modificó y a la vez se agregó.** 

* **git reset --soft NumeroDeHashDelCommit** = Puedo regresar a un commit para hacerle cambios a uno de los archivos agregados en dicho commit, veamos un ejemplo:

  ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/resetHash.PNG "Git Reset --soft HEAD^")

  Donde primeramente hicimos un reset o nos movimos a la linea del tiempo de un commit, para posteriormente modificar el archivo y agregar lineas de codigo, después hicimos un add y un commit actualizando en el cual nos habiamos movido.