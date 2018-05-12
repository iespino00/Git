# **02 MÁS ALLÁ QUE LOS FUNDAMENTOS**

## Diferencia entre commits y restauración de archivos:
****

**1.** **git diff** = Nos sirve para mostrar los cambios realizados si aun no se ha hecho el commit. 

  *  **git diff --staged** = Una vez que se hizo el **commit** y quiero ejecutar solamente **git diff**, no aparecerá nada, entonces es cuando se utiliza este comando.

**2.** **git reset HEAD archivo.extension** = Me elimina un archivo del staged por ejemplo ``git reset HEAD README.md`` me va a sacar el archivo readme.md del staged.

**3.** **git checkout -- archivo.extension** = Refresa al commit anterior el archivo que asignemos por ejemplo si ejecuto ``git checkout -- README.md`` me regresará al commit anterior de ese archivo.

**4.** **git commit -am "Agregar Archivos y Commit"** = Se agregan los archivos al stage y posteriormente se hace el commit con ese mensaje.

****
## Actualizar mensajes del commit
****

**5.** **git commit --amend -m "Mensaje de Commit a cambiar"** = Se modifica el mensaje del commit anteriormente agregado.

  * **git commit --amend** = Si no asigno el mensaje como el comando anterior, me abrirá un modo de edición donde tendré que presionar la tecla **A** , para posteriormente corregir el commit, y para guardar y salir del modo de edición presionaré la tecla ``Esc, : , wq + Enter``.Como se muestra en la imagen siguiente:

    ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/commitAmend.PNG "Git Reset --soft HEAD^")

****
## Viajes en el tiempo 
### **reset --soft , reset --mixed y reset --hard**
****

**6.** **Si por accidente ya hice el commit, pero necesito realizar mas cambios en los archivos e incluirlos en el commit ya ejecutado, se utiliza el siguiente comando**

 * **git reset --soft HEAD^** = Nos permite regresar al commit anterior, **sin deshacer cambios**, solo para hacer adiciones a archivos y posteriormente volver a ejecutar el **add y el commit** y el **``HEAD^``** es para referenciar al commit anterior. Por ejemplo:

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_soft.PNG "Git Reset --soft HEAD^")

  **En la imagen anterior podemos observar que aparece una M de color verde y una M de color rojo significa que se modificó y a la vez se agregó.** 

* **git reset --soft NumeroDeHashDelCommit** = Puedo regresar a un commit para hacerle cambios a uno de los archivos agregados en dicho commit, veamos un ejemplo:

  ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/resetHash.PNG "Git Reset --soft HEAD^")

  Donde primeramente hicimos un reset o nos movimos a la linea del tiempo de un commit, para posteriormente modificar el archivo y agregar lineas de codigo, después hicimos un add y un commit actualizando en el cual nos habiamos movido.

  * **git reset --mixed** = Sirve para moverse a un commit cual sea, pero eliminará los commits posteriores al cual nos posicionemos pero **sin perder los cambios realizados en los commits** por ejemplo:

    ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_mixed.PNG "Git Reset --mixed")

    En este ejemplo podemos ver, que con ``git reset --mixed f3da3e9`` Nos movimos a ese has del commit (Agregamos Historias de los Heroes), y una vez ejecutado el comando, nos desapareció los 2 commits anteriores, mas sin embargo, no se eliminaron los cambios hechos en esos 2 commits.
  
  * **git reset --hard HashDelCommit** = Este comando nos posiciona en el has del commit que asignemos, pero eliminando tanto los commits, como los cambios en cada uno de los archivos.Por ejemplo en la siguiente imagen podemos ver que nuestro repositorio se conforma por los siguientes archivos:

      ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/repositorio_demo4.PNG "Repositorio demo 4")

      Entonces ahora ejecutamos el commando y podemos ver como nos elimina tanto los commits como los cambios (o archivos):

      ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_hard.PNG "git reset --hard HashDelCommit")

      ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_hardRepo.PNG "Repositorio despues de Reset hard")

**7.** **git reflog** = Este comando nos sirve, para visualizar el log de commits aunque ya se hayan hecho comandos de **``reset --soft , reset --hard``** , porque si realizamos un git log, no aparecerá, veamos el ejemplo:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reflog.PNG "Git reflog")

Supongamos que siguiendo el paso del punto **6** donde utilizamos el comando ``git reset --hard`` , y nos quedamos solamente con el archivo ``README.md``, y queremos volver a recuperar archivos o cambios, y commits aplicados aun se hayan borrado con el reset hard, podemos aplicar nuevamente el comando **``git reset hard``** una vez ubicando el punto en el tiempo al que queremos regresar con el **``git reflog``** , por Ejemplo:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_hard_backup.PNG "Git reset hard")

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/reset_hard_backupRepo.PNG "Git reset hard repo")

Podemos observar que nos posicionabamos en el commit con mensaje: **"Se agrego el archivo readme"**, y una vez aplicando el reset hard, nos devolvió los cambios a ese punto, inclyendo los archivos en el repositorio.

****
## Cambiar nombre  eliminar archivos mediante Git
****

Para cambiar el nombre a un archivo, podemos ver como se encuentra nuestro repositorio actualmente:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/rename_file.PNG "git mv")

**1.**  **git mv NombreArchivo.extension NewName.extension** = Con este comando indicamos que queremos cambiar el nombre del archivo. En nuestro caso vamos a probar con el siguiente comando **``git mv destruir-mundo.txt salvar-mundo.txt``** 

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/rename.PNG "git mv")

Podemos observar que automaticamente lo cambia, nos ponde una **R** y si vemos con **git status** , podemos observar que hace referencia a **``rename``** . Vemos que efectivamente nos hizo el cambio en el repositorio. Y como ya esta en el staged, solamente hacemos un commit para indicar que estamos renombrando el archivo

**2.** **git rm NombreDelArchivo**

* *****