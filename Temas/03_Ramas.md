# **03 RAMAS O BRANCHS**

### **Ramas:** [Ver ilustración](https://github.com/iespino00/Git/blob/master/images/img_branch.PNG "Branch")

### **Merge - Uniones:** 
  * **1.** Fast-forward [Ver ilustración](https://github.com/iespino00/Git/blob/master/images/img_fast.PNG "Fast-forward")

  * **2.** Uniones Automáticas [Ver ilustración](https://github.com/iespino00/Git/blob/master/images/img_automaticas.PNG "Uniones Automáticas")

  * **3.** Manual [Ver ilustración](https://github.com/iespino00/Git/blob/master/images/img_manual.PNG "Manual")

****

****
## **MERGE - "FAST-FORWARD"**
### Une una rama cuando no existe algun punto en el tiempo en donde las modificaciones hayan coinsidido. *(Ver Ilustración Superior)*
****

1. git branch NombreDeLaRama : Nos sirve para crear una rama, veamos el ejemplo:

![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/Newbranch.PNG "New Branch")


  Donde podemos observar que con el comando ``git branch rama-villanos`` Nos esta creando una rama de nombre **"rama-villanos"**, y después usamos un comando **``git branch``** y podemos ver que tenemos la rama master y la nueva que acabamos de crear.

2. **git checkout RamaAMover :** Con este comando nos movemos a la rama que deseamos. Lo podemos ver en la imagen anterior, donde nos movimos a la rama villanos y con el comando git branch podemos ver que nos marca en verde y con un **asterisco** en la rama que estamos. Ahora ya podemos hacer el commit, y dichos commits se irán agregando a la rama donde nos encontremos.

3. **git diff rama1 rama2 :** Este comando nos sirve para ver las diferencias entre 2 ramas.

   * Por ejemplo , vamos a ejecutar el siguiente comando **git diff rama-villanos master**

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/diffBranch.PNG "Diff Branches")

    
    Donde podemos observar que agregamos un archivo de nombde ``villanos.md`` al cual se le agregaron 3 villanos.
  
### **Nota:** *Cuando queremos fusionar ramas, tenemos que estar posicionados en la rama donde queremos unir, por ejemplo, si queremos agregar ramas externas al master, debemos de estar posicionados en el master.*

4. **git checkout master :** Con este comando nos movemos a la rama master, y ejecutamos un log  y vamos a ver que ahora la posición del ``HEAD`` Se encontrará en el último commit de la rama a donde nos movimos en esta caso el **``master``**. Como se ve en la siguiente imagen:


   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/checkoutBranch.PNG "git checkout rama")


5. **git merge rama :** Con este comando, vamos a adicionar la rama a la rama en la que nos encontremos. Si supongamos que estamos en la rama master y usamos este comando -> **``git merge rama-villanos``**, estaremos añadiendo la rama villanos a la rama master. Veamoslo en una imagen


   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/fastForward.PNG "Fast forward")

   Podemos observar que se realizó un **``Fast Forward``**.

   Ahora si realizamos un log, observaremos que se unieron todos los commits, desde los que agregamos en el paso número 1 anterior.

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/logFastF.PNG "Log Fast forward")
   
### **Nota:** *Como buena práctica se recomienda eliminar la rama una vez que se haya unido al master, porque la podemos seguir viendo si hacemos un ``git branch``*

5. **git branch -d rama:** Con este comando podemos borrar la rama.

Veamos un ejemplo completo, una vez que añadimos la rama al master, hacemos un **git branch** y veremos que aun se encuentra la rama villanos, despues de aplicar el comando de delete branch, podremos ver que ya no va existir. 

   ![alt text](https://raw.githubusercontent.com/iespino00/Git/master/images/deleteBranch.PNG "Delete Branch")