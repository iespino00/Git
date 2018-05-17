
# Configurar GIT.
### (Para que git detecte nuestros cambios con nuestros datos)
****

**1.** git config --global user.name "TuUsuario"

**2.** git config --global user.email "TuEmail"

Ver los siguientes registros:
* git config --global -e   = Para ver las configuraciones globales en modo escritura.
  * : + q + Enter = Salirse del comando anterior.
* git config --global -l   = Para ver las configuraciones globales en modo lectura.

**Otros comandos :** 

* **ls -al**  = y los ordena en forma de lista.
* **pwd** = Muestra la ruta en la que estamos.

****
# **Comandos de GIT**
**1.** **git --version** = Versión de Git

**2.** **git help** = Ayuda para ver funcionamiento de un comando

**3.** **git init** = Inicializa un repositorio con git.

**4.** **git status** = visualiza el status del repositorio.
   
   * **git status -s** = Muestra solamente los archivos que han sido modificados y no agregados al stage (rojos) y los que estan en el stage (verdes).O solamente alguno de los dos. Por ejemplo:

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/gitstatus_s.PNG "Git Status -s")

   * **git status -s -b** = Muestra los archivos que han sido modificados y no agregados al stage (rojos) y los que estan en el stage (verdes).O solamente alguno de los dos, Pero además le con **-b** agregará la rama (branch) donde estamos trabajando. Por ejemplo:

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/gitstatus_s_b.PNG "Git status -s -b")

**5.** **git add .** = Agrega todos los archivos para que este al pendiente de los cambios. Si posterior a esto hacemos un **git status** , veremos que se ponen en color verde los archivos que estan listos para hacerles commit.
  
   * **git add \*.png** = Agregará todos los archivos de dicha extensión **(png)** para posteriormente hacerles commit.

   * **git add css/** = Agregará todos los archivos que se encuentren dentro de la carpeta **css** para posteriormente hacerles commit.

   * **git add -A** = Agregará todos los archivos que fueron modificados

     * **git reset \*.xml** = Todos los archivos **XML** que se encuentren en el state (En verde, despues de hacer un git add), se quitarán para excluirlos del commit.

   * **git add "\*.txt"** = Agrega todos los txt de todo el proyecto.

   * **git add \*.txt** = Agrega todos los txt del directorio actual.

   * **git add --all** = Agrega todos los archivos.

   * **git add `<Lista de archivos>`** = Agrega los archivos que listemos, separados por espacio.

   * **git add pdfs/*.pdf** = Agrega todos los archivos de formato pdf que se encuentren dentro del forlder **pdfs**.

**6.** **git commit -m "Primer Commit"** = Se hace un snapshot de los cambios en el repositorio.

  * **git commit -am "Agregar y Commit"** = Se agregan los archivos al stage y posteriormente se hace el commit con ese mensaje.

  * **git commit** = Si yo no especifico el comando ``-m ó -am``Me pondrá en modo de edición. Donde podré teclear el mensaje presionando la tecla **A** , posteriormente para salir del modo de edición se preciona ``Esq, : , wq + Enter``. Puedes veririficar el commit agregado con el log. Veamos como se ve en la consola de comandos lo anteriormencionado:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/gitCommit.PNG "Git commit")


**7.** **git checkout -- .** = Recupera todos los archivos a su anterior commit.

**8.** **git log** = Nos muestra en log de commits, con un has que es un código relacionado al commit, el autor, la fecha, y el mensaje del commit en su momento creado, el listado se muestra del commit mas reciente al más antiguo.

Por ejemplo :

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/gitlog.PNG "Git Log")

****
## Revisando el **LOG**
### A continuación se enlistan los comandos para hacer revisión de LOGS de commits dentro del repositorio.
****


**1.** **git log** = Muestra el registro de logs, con el hash largo, autor, fecha y mensaje del commit.

**2.** **git log -- oneline** = Mostrará los logs con el hash corto y el mensaje del commit. Por ejemplo:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/gitlog_oneline.PNG "Git Log --oneline")

**3.** **git log --online --decorate --all --graph** = Con el **all** se mostrará todo la información referente a las diferentes ramas, el **decorate y el graph** da formato elegante conforme se va trabajando con diferentes ramas.


****
## Shortcuts o Alias.
### Se utilizan para poner un **alias** a comandos que son muy largos, y poder acceder a ellos de una manera más sencilla.
****
**1.** **git config --global alias.TuAlias "El comando a simplificar"** = Asignamos un alias a un comando. Por ejemplo:

`git config --global alias.lg "log --oneline --decorate --all --graph"`

De esta manera ya podemos utilizar el alias, en este caso creamos uno para el log, y lo vemos de la siguiente manera:

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/alias.PNG "Git config --global alias.alias 'comando'")

   link:

[Regresar al Temario](../README.md "MD 2")

[Test](../README.md){.btn.btn-link.btn-sm}

<button onclick="https://github.com/iespino00/Git" class="button-save large">Regresar al Temario</button>

Lorem ipsum dolor sit amet.

[Click me](https://github.com/iespino00/Git){: .btn}