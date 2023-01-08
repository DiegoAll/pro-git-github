# Course Notes 


## 0. Introducción

Deja de versionar tus proyectos usando tu propio sistema de control de versiones. Mejor usa Git, el sistema de control de versiones por excelencia que utiliza la industria tecnológica. Aprende a trabajar con git, conceptos básicos, clonar un repositorio y gestionar tus proyectos alojándolos en tu repositorio local y en GitHub. 

- Llevar un Control de Versiones en tus Proyectos con Git 

- Trabajar en Equipos de Forma Colaborativa 

- Utilizar Dominios Personalizados con GitHub Pages 

- Instalar Git en tu sistema operativo 


https://www.youtube.com/watch?v=1RKPsALUGn8


**"Git es mucho más que add, commit, pull, push".** (J.F Vega)


## 1. ¿Por qué usar un sistema de control de versiones como Git?

Un sistema de control de versiones como Git nos ayuda a guardar el historial de cambios y crecimiento de los archivos de nuestro proyecto.

En realidad, los cambios y diferencias entre las versiones de nuestros proyectos pueden tener similitudes, algunas veces los cambios pueden ser solo una palabra o una parte específica de un archivo específico. Git está optimizado para guardar todos estos cambios de forma atómica e incremental, o sea, aplicando cambios sobre los últimos cambios, estos sobre los cambios anteriores y así hasta el inicio de nuestro proyecto.

- El comando para iniciar nuestro repositorio, o sea, indicarle a Git que queremos usar su sistema de control de versiones en nuestro proyecto, es **git init**. 
- El comando para que nuestro repositorio sepa de la existencia de un archivo o sus últimos cambios es **git add.** Este comando no almacena las actualizaciones de forma definitiva, únicamente las guarda en algo que conocemos como “Staging Area” (área de montaje o ensayo). 
- El comando para almacenar definitivamente todos los cambios que por ahora viven en el staging area es **git commit**. También podemos guardar un mensaje para recordar muy bien qué cambios hicimos en este commit con el argumento -m "Mensaje del commit". 
- Por último, si queremos mandar nuestros commits a un servidor remoto, un lugar donde todos podamos conectar nuestros proyectos, usamos el comando **git push.**

### Comandos básicos de git

- git init: inicializa un repositorio de GIT en la carpeta donde se ejecute el comando.

- git add: añade los archivos especificados al área de preparación (staging).

- git commit -m “commit description”: confirma los archivos que se encuentran en el área de preparación y los agrega al repositorio.

- git commit -am “commit description”: añade al staging area y hace un commit mediante un solo comando. (No funciona con archivos nuevos)

- git status: ofrece una descripción del estado de los archivos (untracked, ready to commit, nothing to commit).

- git rm (. -r, filename) (–cached): remueve los archivos del index.

- git config --global user.email tu@email.com: configura un email.

- git config --global user.name <Nombre como se verá en los commits>: configura un nombre.

- git config --list: lista las configuraciones.

### Analizar cambios en los archivos de un proyecto Git

- git log: lista de manera descendente los commits realizados.

- git log --stat: además de listar los commits, muestra la cantidad de bytes añadidos y eliminados en cada uno de los archivos modificados.

- git log --all --graph --decorate --oneline: muestra de manera comprimida toda la historia del repositorio de manera gráfica y embellecida.

- git show filename: permite ver la historia de los cambios en un archivo.

- git diff <commit1> <commit2>: compara diferencias entre en cambios confirmados.

### Volver en el tiempo con branches y checkout

- git reset <commit> --soft/hard: regresa al commit especificado, eliminando todos los cambios que se hicieron después de ese commit.

- git checkout <commit/branch> <filename>: permite regresar al estado en el cual se realizó un commit o branch especificado, pero no elimina lo que está en el staging area.

- git checkout – <filePath>: deshacer cambios en un archivo en estado modified (que ni fue agregado a staging)

### git rm y git reset

git rm:
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

git rm no puede usarse por sí solo, así nomás. Se debe utilizar uno de los flags para indicar a Git cómo eliminar los archivos que ya no se necesitan en la última versión del proyecto:

- git rm --cached <archivo/s>: elimina los archivos del área de Staging y del próximo commit, pero los mantiene en nuestro disco duro.
- git rm --force <archivo/s>: elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos aplicar comandos más avanzados).

### git reset
Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir.

- git reset --soft: Vuelve el branch al estado del commit especificado, manteniendo los archivos en el directorio de trabajo y lo que haya en staging considerando todo como nuevos cambios. Así podemos aplicar las últimas actualizaciones a un nuevo commit.
- git reset --hard: Borra absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
- git reset HEAD: No borra los archivos ni sus modificaciones, solo los saca del área de staging, de forma que los últimos cambios de estos archivos no se envíen al último commit. Si se cambia de opinión se los puede incluir nuevamente con git add.

### Ramas o Branches en git
Al crear una nueva rama se copia el último commit en esta nueva rama. Todos los cambios hechos en esta rama no se reflejarán en la rama master hasta que hagamos un merge.

- git branch <new branch>: crea una nueva rama.
- git checkout <branch name>: se mueve a la rama especificada.
- git merge <branch name>: fusiona la rama actual con la rama especificada y produce un nuevo commit de esta fusión.
- git branch: lista las ramas generadas.


## 2. ¿Qué es Git?

Git es un sistema de control de versiones distribuido, diseñado por Linus Torvalds. Está pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando estas tienen un gran número de archivos de código fuente.

- Git está optimizado para guardar cambios de forma incremental.

- Permite contar con un historial, regresar a una versión anterior y agregar funcionalidades.

- Lleva un registro de los cambios que otras personas realicen en los archivos.

Git fue diseñado para operar en un entorno Linux. Actualmente, es multiplataforma, es decir, es compatible con Linux, MacOS y Windows. En la máquina local se encuentra Git, se utiliza bajo la terminal o línea de comandos y tiene comandos como merge, pull, add, commit y rebase, entre otros.

**Características de Git**

- Git almacena la información como un conjunto de archivos.

- No existen cambios, corrupción en archivos o cualquier alteración sin que Git lo sepa.

- Casi todo en Git es local. Es difícil que se necesiten recursos o información externos, basta con los recursos locales con los que cuenta.

- Git cuenta con 3 estados en los que es posible localizar archivos: Staged, Modified y Committed.


**Para qué proyectos sirve Git**

Con Git se obtiene una mayor eficiencia usando archivos de texto plano, ya que con archivos binarios no puede guardar solo los cambios, sino que debe volver a grabar el archivo completo ante cada modificación, por mínima que sea, lo que hace que incremente demasiado el tamaño del repositorio.

“Guardar archivos binarios en el repositorio de Git no es una buena práctica, únicamente deberían guardarse archivos pequeños (como logos) que no sufran casi modificaciones durante la vida del proyecto. Los binarios deben guardarse en un CDN”.


**¿Qué es un sistema de control de versiones?**

El SCV o VCS (por sus siglas en inglés) es un sistema que registra los cambios realizados sobre un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas llevar el historial del ciclo de vida de un proyecto, comparar cambios a lo largo del tiempo, ver quién los realizó o revertir el proyecto entero a un estado anterior.

Cualquier tipo de archivo que se encuentre en un ordenador puede ponerse bajo control de versiones.


**¿En qué se diferencia de Github?**

Github es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. Se emplea principalmente para la creación de código fuente de programas de computadora.

Puede considerarse a Github como la red social de código para los programadores y en muchos casos es visto como un curriculum vitae, pues aquí se guarda el portafolio de proyectos de programación.


**Características de Github**

- GitHub permite alojar proyectos en repositorios de forma gratuita y pública, pero tiene una forma de pago para privados.

- Puedes compartir fácilmente tus proyectos.

- Permite colaborar para mejorar los proyectos de otros y a otros mejorar o aportar a los tuyos.

- Ayuda a reducir significativamente los errores humanos, a tener un mejor mantenimiento de distintos entornos y a detectar fallos de una forma más rápida y eficiente.

- Es la opción perfecta para poder trabajar en equipo en un mismo proyecto.

- Ofrece todas las ventajas del sistema de control de versiones Git, pero también tiene otras herramientas que ayudan a tener un mejor control de los proyectos.


https://www.youtube.com/watch?v=DinilgacaWs


## 3. Instalando Git y GitBash en Windows

Windows y Linux tienen comandos diferentes, graban el enter de formas diferentes y tienen muchas otras diferencias. Cuando instales Git Bash en Windows debes elegir si prefieres trabajar con la forma de Windows o la forma de UNIX (Linux y Mac). Ten en cuenta que, normalmente, los entornos de desarrollo profesionales tienen personas que usan sistemas operativos diferentes. Esto significa que, si todos podemos utilizar los mismos comandos, el trabajo resultará más fácil para todos en el equipo. Los comandos de UNIX son los más comunes entre los equipos de desarrollo. Así que, a menos que trabajes con tecnologías nativas de Microsoft (por ejemplo, .NET), la recomendación es que elijas la opción de la terminal tipo UNIX para obtener una mejor compatibilidad con todo tu equipo.

**Cómo instalar Git en Windows**

Para instalar este sistema de control de versiones en Windows, simplemente vas al [repositorio de descarga](https://git-scm.com/downloads). Luego de descargarlo, lo ejecutas como cualquier otra aplicación de Windows. Al momento de iniciar el instalador, asegúrate de haber marcado la opción de instalar Git Bash en el computador (que es lo que nos permitirá correr comandos de Linux en la consola sin problemas para trabajar con Git). Otra forma de obtener Git fácilmente en tu computador, es descargando GitHub para Windows. Aquí puedes encontrar el [instalador de GitHub](https://desktop.github.com/).



## 4. Instalando Git en OSX

En Mac, Git está instalado en el sistema operativo por defecto. Este instalador no es realmente necesrario.
Puedes verificar que tienes instalado Git desde el terminal usando el comando: 

$ git --version

Esto deberia generar una respuesta similar a esta:

$ git version 1.9.3 (Apple Git-50)

Cómo actualizar Git en Mac

Si quieres actualizar Git a su última versión, se puede hacer de manera simple usando Homebrew, al que accedes también desde la consola. Lo actualizas con el siguiente código:

$ brew upgrade git

En caso de necesitarlo, la instalación de GIT en Mac es un poco más sencilla. No debemos instalar GitBash porque Mac ya trae por defecto una consola de comandos (la puedes encontrar como “Terminal”). Tampoco debemos configurar OpenSSL porque viene listo por defecto.

OSX está basado en un Kernel de UNIX llamado **BSD**. Estos significa que hay algunas diferencias entre las consolas de Mac y Linux. Pero no vas a notar la diferencia a menos que trabajes con acceso profundo a las interfaces de red o los archivos del sistema operativo. Ambas consolas funcionan muy parecido y comparten los comandos que vamos a ver durante el curso.

Puedes descargar Git aquí: https://git-scm.com  Puedes verificar que Git fue instalado correctamente con el comando 

$ git --version.


## 5. Instalando Git en Linux

Cada distribución de Linux tiene un comando especial para instalar herramientas y actualizar el sistema. Aquí veremos un ejemplo de los comandos para instalar Git en Linux

$ sudo apt-get update; sudo apt install git

$ git --version

Sudo significa **Super User DO**. Se utiliza para correr comandos con credenciales de super usuario (sin restricciones).

En las distribuciones derivadas de Debian (como Ubuntu) el comando especial es apt-get, en Red Hat es yum y en ArchLinux es pacman. Cada distribución tiene su comando especial y debes averiguar cómo funciona para poder instalar Git. Antes de hacer la instalación, debemos hacer una actualización del sistema. En nuestro caso, los comandos para hacerlo son sudo apt-get update y sudo apt-get upgrade. Con el sistema actualizado, ahora sí podemos instalar Git y, en este caso, el comando para hacerlo es sudo apt-get install git. También puedes verificar que Git fue instalado correctamente con el comando git --version.


## 6. Editores de código, archivos binarios y de texto plano

Un editor de código o IDE es una herramienta que nos brinda muchas ayudas para escribir código, algo así como un bloc de notas muy avanzado. Los editores más populares son VSCode, Sublime Text y Atom, pero no es obligatorio usar alguno de estos para programar. Conoce más a fondo sobre qué es un IDE.

### Tipos de archivos y sus diferencias:

- Archivos de Texto (.txt): Texto plano normal y sin nada especial. Lo vemos igual sin importar dónde lo abramos, ya sea con el bloc de notas o con editores de texto avanzados.
- Archivos RTF (.rtf): Podemos guardar texto con diferentes tamaños, estilos y colores. Pero si lo abrimos desde un editor de código, vamos a ver que es mucho más complejo que solo el texto plano. Esto es porque debe guardar todos los estilos del texto y, para esto, usa un código especial un poco difícil de entender y muy diferente a los textos con estilos especiales al que estamos acostumbrados.
- Archivos de Word (.docx): Podemos guardar imágenes y texto con diferentes tamaños, estilos o colores. Al abrirlo desde un editor de código podemos ver que es código binario, muy difícil de entender y muy diferente al texto al que estamos acostumbrados. Esto es porque Word está optimizado para entender este código especial y representarlo gráficamente.
Recuerda que debes habilitar la opción de ver la extensión de los archivos, de lo contrario, solo podrás ver su nombre. La forma de hacerlo en Windows es Vista > Mostrar u ocultar > Extensiones de nombre de archivo.

**Conceptos importantes de Git**

Bug: Error en el código

Repository: Donde se almacena todo el proyecto, el cual puede vivir tanto en local como en remoto. El repositorio guarda un historial de versiones y, más importante, de la relación de cada versión con la anterior para que pueda hacerse el árbol de versiones con las diferentes ramas.

Fork: Si en algún momento queremos contribuir al proyecto de otra persona, o si queremos utilizar el proyecto de otro como el punto de partida del nuestro. Esto se conoce como “fork”.

Clone: Una vez se decide hacer un fork , hasta ese momento sólo existe en GitHub. Para poder trabajar en el proyecto, toca clonar el repositorio elegido al computador personal.

Branch: Es una bifurcación del proyecto que se está realizando para anexar una nueva funcionalidad o corregir un bug.

Master: Rama donde se almacena la última versión estable del proyecto que se está realizando. La rama master es la que está en producción en cada momento (o casi) y debería estar libre de bugs. Así, si esta rama está en producción, sirve como referente para hacer nuevas funcionalidades y/o arreglar bugs de última hora.

Commit: consiste en subir cosas a la versión local del repositorio. De esta manera se puede trabajar en la rama de forma local sin tener que modificar ninguna versión en remoto ni tener que tener la última versión remota, cosa muy útil en grandes desarrollos trabajados por varias personas.

Push: Consiste en enviar todo lo que se ha confirmado con un commit al repositorio remoto. Aquí es donde se une nuestro trabajo con el de los demás.

Checkout: Acción de descargarse una rama del repositorio GIT local (sí, GIT tiene su propio repositorio en local para poder ir haciendo commits) o remoto.

Fetch: Actualiza el repositorio local bajando datos del repositorio remoto al repositorio local sin actualizarlo, es decir, se guarda una copia del repositorio remoto en el local.

Merge: La acción de merge es la continuación natural del fetch. El merge permite unir la copia del repositorio remoto con tu repositorio local, mezclando los diferentes códigos.

Pull: Consiste en la unión del fetch y del merge, esto es, recoge la información del repositorio remoto y luego mezcla el trabajo en local con esta.

Diff: Se utiliza para mostrar los cambios entre dos versiones del mismo archivo.


## 7. Introducción a la terminal y línea de comandos

La línea de comandos nos permite interactuar con nuestro computador sin necesidad de utilizar una interfaz gráfica. Sin embargo, los computadores emplean distintos sistemas de archivos y manejan diferentes comandos, dependiendo del sistema operativo que utilicen.

### Diferencias entre la estructura de archivos de Windows, Mac o Linux

- La ruta principal en Windows es C:\, en UNIX es solo /.
- Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.
Recuerda que GitBash usa la ruta /c para dirigirse a C:\ (o /d para dirigirse a D:\) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es /c/Users/Nombre de tu usuario

### Comandos básicos en la terminal

- pwd: Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
- mkdir: Nos permite crear carpetas (por ejemplo, mkdir Carpeta-Importante).
- touch: Nos permite crear archivos (por ejemplo, touch archivo.txt).
- rm: Nos permite borrar un archivo o carpeta (por ejemplo, rm archivo.txt). Mucho cuidado con este comando, puedes borrar todo tu disco duro.
- cat: Ver el contenido de un archivo (por ejemplo, cat nombre-archivo.txt).
- ls: Nos permite cambiar ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser -- + el nombre del argumento o - + una sola letra o shortcut por cada argumento).
- ls -a: Mostrar todos los archivos, incluso los ocultos.
- ls -l: Ver todos los archivos como una lista.
cd: Nos permite navegar entre carpetas.
- cd /: Ir a la ruta principal:
- cd o cd ~: Ir a la ruta de tu usuario
- cd carpeta/subcarpeta: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.
- cd .. (cd + dos puntos): Regresar una carpeta hacia atrás.
- Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar cd . (cd + un punto).
history: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
! + número: Ejecutar algún comando con el número que nos muestra el comando history (por ejemplo, !72).
clear: Para limpiar la terminal. También podemos usar los atajos de teclado Ctrl + L o Command + L.
Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla Tab para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla Arriba puedes ver el último comando que ejecutamos.

Recuerda que podemos descubrir todos los argumentos de un comando con el argumento --help (por ejemplo, cat --help).


## 8. Crea un repositorio de Git y haz tu primer commit


git init **(Desamboguar si adentro o afuera del folder)** Es adentro !! Probar

touch history.txt; echo -e " Esta es la historia de Diego \n Diego tiene 32 años y nació en Colombia. \n Hoy hablaremos de su historia." > history.txt

git status

No hay commits todavia
```
No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
```

git add history.txt

Fredy
```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   history.txt

```

Diego
```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   history.txt
```
Al parecer hacen lo mismo, pero en un escenario particular son diferentes.

~~~~
git rm --cached vs git git restore --staged <file>
https://stackoverflow.com/questions/65434544/whats-the-difference-between-git-rm-cached-git-restore-staged-and-gi#:~:text=%40pavel_orekhov%3A%20git%20rm%20%2D%2Dcached,do%20not%20include%20this%20file%22.

Tiene que ver con los HEADS (Ahondar)
~~~~

$ git rm history.txt

```
error: the following file has changes staged in the index:
    src/historia.txt
(use --cached to keep the file, or -f to force removal)
```

git rm --cached <file> : Elimina de RAM (staging) pero conserva en el sistema de archivos (Quitar ese git add) 

git rm -f <file>: Elimina el archivo del directorio

git commit **MALA PRACTICA: Debe dejarse un mensaje de que se envia al repositorio.**

~~~~
NOTA: 
Primero se debe setear la identidad de quien realiza el commit.
Si no se indica nada obtiene por defecto el valor de las variables de entorno del SO.
~~~~

Ver donde estan las configuraciones guardadas

$ git config --list --show-origin  (Para casos avanzados)

**De forma sencilla**

$ git config [--local|--global] --list

$ git config --local user.email "dposadallano@gmail.com" (Local al interior del repositorio - Diego)

$ git config --local user.name "DiegoAll" (Local al interior del repositorio - Diego)

**Config file location**

$ git commit -m "Este es el primer commit de este archivo"

Luego se modifica el archivo,

~~~~
Esta es la historia de Diego 

Diego tiene 32.5 años y nací en Colombia, 

viviendo en mi mente. 
~~~~
 
$ git status $

```
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   src/history.txt
no changes added to commit (use "git add" and/or "git commit -a")
```
$ git add .

$ git commit -m "Cambios al archivo de historia para reflejar la edad correcta"

Para ver la historia del archivo:

$ git log history.txt $

```
commit 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda   (Tag, "Hash", nombre interno del commit, donde estoy en este momento)

(HEAD -> main)  Version HEAD en la rama main 

Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 23 00:32:56 2022 -0500
```

Si por algún motivo te equivocaste en el nombre o email que configuraste al principio, lo puedes modificar de la siguiente manera:

git config --global --replace-all user.name “Aquí va tu nombre modificado”

O si lo deseas eliminar y añadir uno nuevo

git config --global --unset-all user.name :Elimina el nombre del usuario

git config --global --add user.name “Aquí va tu nombre”


<img src="/assets/CrearRepo_JoseLuisMendozaMogollon.jpeg" align="center" />



## 9. Analizar cambios en los archivos de tu proyecto con Git

El comando git show nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuándo se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser más detallados. Por que antes funcionaba y ahora a no funciona, hacer la trazabilidad de que fue lo que paso

$ git show history.txt $

Muestra el último commit, se esta en la cabecera de la rama master. (Version mas reciente) y **basicamente hace un diff** Diferencia entre la version anterior y la version nueva. index es un indicador dentro de la base de datos de git, @@ -1,3 +1,6 @@  cuantos bytes cambiaron y en que lugares cambiaron.

```
commit 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 23 00:32:56 2022 -0500

    Cambios al archivo de historia para reflejar la edad correcta

diff --git a/src/history.txt b/src/history.txt
index d5c0bcf..65fac0e 100644
--- a/src/history.txt
+++ b/src/history.txt
@@ -1,3 +1,6 @@
```

Se agrega el siguiente parrafo a history.txt

~~~~
En camara parece alto y realmente lo es.
~~~~



$ git commit (pero sin mensaje y aparece el editor configurado, en este caso es Vim, se agrega el mensaje)

$ ESC + SHIFT + ZZ ; :w ; :wq  (Para salir cualquiera de estos dos comandos)

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git commit
[main dc00a13] Se agrega un cambio a su estatura
 1 file changed, 2 insertions(+)
```

Se agrega un nuevo parrafo a history.txt

~~~~
Hoy es CS Engineer en Mercado Libre.
~~~~

$ commit $

Nuevamente aparece el editor de código basado en línea de comandos Vim, derivado de Vi. Nunca se puede enviar un commit vacio.
Se agregan enters, cabe aclarar que se utiliza para salvar nuevamente **ESC + SHIFT + ZZ** edto lo que hace es forzar a que guarde.

```
commit d051905d38cd89b9ea322b36a5d5105313ce6518 (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 23 22:46:39 2022 -0500

    Agregamos el cargo de la persona
    
    La persona es Diego
```

Si queremos ver la diferencia entre una versión y otra, no necesariamente todos los cambios desde la creación del archivo, podemos usar el comando git diff commitA commitB. Recuerda que puedes obtener el ID de tus commits con el comando git log.

Se va a comparar el cambio mas reciente con la primera version.

$ git diff d051905d38cd89b9ea322b36a5d5105313ce6518 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda

(Muestra en verde cual era la versión original y en rojo la última version)


$ git diff 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda d051905d38cd89b9ea322b36a5d5105313ce6518

Si se compara la primera con la mas reciente se obtienen los últimos cambios.

~~~~
 Hoy hablaremos de su historia.
+
+En camara parece alto y realmente lo es.
+
+Hoy es CS Engineer en Mercado Libre.
\ No newline at end of file
~~~~

En conclusión para ver los cambios más recientes entre versiones es la mas antigua vs la mas reciente.

¿Como vuelvo a una version vieja? Ejemplo en la que tenia 32 años.



## 10. ¿Qué es el staging?

El staging es el lugar donde se guardan temporalmente los cambios, para luego ser llevados definitivamente al repositorio. El repositorio es el lugar donde se guardan todos los registros de los cambios realizados a los archivos. Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, solo debes ejecutar el comando git init.

¿Qué es el área de staging?
El área de staging se puede ver como un limbo donde nuestros archivos están por ser enviados al repositorio o ser regresados a la carpeta del proyecto.

¿Qué es git init?
git init es el comando que activa git en nuestro proyecto creando un espacio en memoria RAM llamado staging y una carpeta .git.

Este comando se encargará de dos cosas: primero, crear una carpeta .git, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; segundo, crear un área que conocemos como staging, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

<img src="/assets/gitWorkspace.jpeg" align="center" />

Cómo funciona el staging y el repositorio: ciclo básico de trabajo en git:
El flujo de trabajo básico en git es algo así:

Modificas una serie de archivos en tu directorio de trabajo.
Preparas los archivos, añadiéndolos a tu área de preparación (staging).
Confirmas los cambios (commit), lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de git.
Veamos a detalle las 3 secciones principales que tiene un proyecto en git.

Working directory
El working directory es una copia de una versión del proyecto. Estos archivos se sacan de la base de datos comprimida en el directorio de git y se colocan en el disco para que los puedas usar o modificar.

Staging area
Es un área que almacena información acerca de lo que va a ir en tu próxima confirmación. A veces se le denomina índice (index).

.git directory (repository)
En el repository se almacenan los metadatos y la base de datos de los objetos para tu proyecto. Es la parte más importante de git (carpeta .git) y es lo que se copia cuando clonas un repositorio desde otra computadora.

<img src="/assets/gitBasicWorkflow.jpeg" align="center" />

Ciclo de vida o estados de los archivos en git
Cuando trabajamos con git, nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):

Archivos tracked
Son los archivos que viven dentro de git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.

Archivos staged
Son archivos en staging. Viven dentro de git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.

Archivos unstaged
Entiéndelos como archivos “tracked pero unstaged”. Son archivos que viven dentro de git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.

Archivos untracked
Son archivos que NO viven dentro de git, solo en el disco duro. Nunca han sido afectados por git add, así que git no tiene registros de su existencia.

Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de staging (con el comando git add), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de staging.

Comandos para mover archivos entre los estados de Git
Estos son los comandos más importantes que debes conocer:

Git status
git status nos permite ver el estado de todos nuestros archivos y carpetas.

Git add
git add nos ayuda a mover archivos del untracked o unstaged al estado staged. Podemos usar git nombre-del-archivo-o-carpeta para añadir archivos y carpetas individuales o git add -A para mover todos los archivos de nuestro proyecto (tanto untrackeds como unstageds).

Git reset HEAD
Nos ayuda a sacar archivos del estado staged para devolverlos a su estado anterior. Si los archivos venían de unstaged, vuelven allí. Y lo mismo se venían de untracked.

Git commit
Nos ayuda a mover archivos de unstaged a tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento m para escribirlo (git commit -m "mensaje").

Git rm
Este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente:

git rm --cached: mueve los archivos que le indiquemos al estado untracked.
git rm --force: elimina los archivos de git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
Contribución creada con los aportes de: Diego Camacho, Jesús Sarabia y Angelo Yenque.


## 11. ¿Qué es branch (rama) y cómo funciona un Merge en Git?

Una rama o branch es una versión del código del proyecto sobre el que estás trabajando. Estas ramas ayudan a mantener el orden en el control de versiones y manipular el código de forma segura. En otras palabras, un branch o rama en Git es una rama que proviene de otra. Imagina un árbol, que tiene una rama gruesa, y otra más fina, en la rama más gruesa tenemos los commits principales y en la rama fina tenemos otros commits que pueden ser de hotfix, devlopment entre otros.ㅤ

<img src="/assets/branch-merge-git.jpeg" align="center" />

Clases de branches o ramas en Git
Estas son las ramas base de un proyecto en Git:

1. Rama main (Master)
Por defecto, el proyecto se crea en una rama llamada Main (anteriormente conocida como Master). Cada vez que añades código y guardas los cambios, estás haciendo un commit, que es añadir el nuevo código a una rama. Esto genera nuevas versiones de esta rama o branch, hasta llegar a la versión actual de la rama Main.

2. Rama development
Cuando decides hacer experimentos, puedes generar ramas experimentales (usualmente llamadas development), que están basadas en alguna rama main, pero sobre las cuales puedes hacer cambios a tu gusto sin necesidad de afectar directamente al código principal.

3. Rama hotfix
En otros casos, si encuentras un bug o error de código en la rama Main (que afecta al proyecto en producción), tendrás que crear una nueva rama (que usualmente se llaman bug fixing o hot fix) para hacer los arreglos necesarios. Cuando los cambios estén listos, los tendrás que fusionar con la rama Main para que los cambios sean aplicados. Para esto, se usa un comando llamado Merge, que mezcla los cambios de la rama que originaste a la rama Main.

Todos los commits se aplican sobre una rama. Por defecto, siempre empezamos en la rama Main (pero puedes cambiarle el nombre si no te gusta) y generamos nuevas ramas, a partir de esta, para crear flujos de trabajo independientes.

Cómo crear un branch o rama en Git
El comando git branch permite crear una rama nueva. Si quieres empezar a trabajar en una nueva función, puedes crear una rama nueva a partir de la rama master con git branch new_branch. Una vez creada, puedes usar git checkout new_branch para cambiar a esa rama.

Recuerda que todas tus versiones salen de la rama principal o Master y de allí puedes tomar una versión específica para crear otra rama de versiones.

Cómo hacer merge
Producir una nueva rama se conoce como Checkout. Unir dos ramas lo conocemos como Merge.

Cuando haces merge de estas ramas con el código principal, su código se fusiona originando una nueva versión de la rama master (o main) que ya tiene todos los cambios que aplicaste en tus experimentos o arreglos de errores.

Podemos generar todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para producir ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.

Solo ten en cuenta que combinar estas ramas (hacer “merge”) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos a mano.

Contribución creada con los aportes de: Diego García, Andres Avalos, Jessica Ortiz y Edgar Rodriguez.



## 12. Volver en el tiempo en nuestro repositorio utilizando reset y checkout


Imaginar que se desea volver a donde se estuvo en el segundo commit que seria el siguiente:

commit 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda
Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 23 00:32:56 2022 -0500

    Cambios al archivo de historia para reflejar la edad correcta


git reset nos permite volver a una version anterior.

hay dos tipos de reset 

-- hard todo vuelve al estado anterior, **es el mas peligroso** pero el que mas comunmente ocurre.

-- soft se vuelve a la version anterior pero lo que se tenga en staging (Es decir si has hecho cambios y le has dado git add eso sigue ahi disponible para el proximo commit. Simplemente que en el directorio de trabajo vuelvr a la version anterior).


para este caso como lo que se quiere realmente es volver en el tiempo. Se le va a dar --hard. (.... pendiente)

$ git reset 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda

Y de repente todo se cambia. E indica que ahora la cabeza es otro commitID. Si se verifica con un editor de texto se retorno a una version anterior.

CO0C02GD0T7MD6M:pro-git-github dposada$ git reset 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda
Unstaged changes after reset:
M       notes/COMMANDS.md
M       notes/EXTRAS.md
M       notes/NOTES.md
M       src/history.txt

En este caso sin flags se conserva el archivo en el directorio. (Esta igual.)

commit 960a55d3b5a903ef76bbb5c99dddd3e3debd0eda (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 23 00:32:56 2022 -0500

    Cambios al archivo de historia para reflejar la edad correcta


Ahora el HEAD apunta al commitID que se le indicó.


Esta es la magia de git reset.

~~~~
Tener cuidado por que esto realmente borra todo lo que se hizó previamente,puede ser peligroso ejecutarlo. Es una forma de volver al pasado de una manera agresiva. 
~~~~

TENER CUIDADO QUE SOLO SE HIZO git reset, falto el hard 

Para entender mejor  estos cambios, se va a crear un nuevo archivo, un html estandar llamado blogpost.html con una estructura de pagina muy basica.

git add src/blogpost.html

Antes de hacer commit se va a crear otro archivo nuevo de estilos llamado css/estilos.css  relativa a la ruta donde esta el blogpost.html. Lo importante es que esos cambios no han ocurrido todavia, se le hicieron cambios al archivo blogpost, eso significa que en staging hay unos cambios pero no estan los nuevos de enlazar a la hoja de estilos, estos solo estan en el directorio.

$ git status $ 

```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   src/blogpost.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)

        modified:   src/blogpost.html
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        src/css/
```
En este momento en status indica que se tiene un nuevo archivo para blogpost.html en staging que fue guardado previamente, pero acaba de ser modificado. Aparte de eso se creo una carpeta css. Ahora se tienen cosas en el diorectrorio de trabajo, staging y repositorio distintas se puede utilizar git diff. 
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git diff src/blogpost.html 
diff --git a/src/blogpost.html b/src/blogpost.html
index c945c64..eebd4d9 100644
--- a/src/blogpost.html
+++ b/src/blogpost.html
@@ -1,9 +1,10 @@
 <html>
     <head>
         <title>Diego BlogPost</title>
+        <link rel="stylesheet" href="css/estilos.css" />
     </head>
     <body>
-        <h1>Aqui vamos a hacer un blog post</h1>
+        <h1>Aqui vamos a hacer un blog post </h1>
         <p>Y este es el parrafo de inicio</p>
     </body>
 </html>
```
Estos son los cambios lo que usted tiene en staging lo que esta en memoria RAM, vs lo que está en el disco duro, es decir el último cambio realizado enlazando al blogpost la hoja de estilos.  **Ver diferencias entre directorio actual y el staging** 
```
+        <link rel="stylesheet" href="css/estilos.css" />
```
Finalmente se pueden agregar a staging los ultimos cambios realizados 

$ git add <files> $

A Git solo le importan los archivos, guarda las carpetas como rutas y automaticamente las crea.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log
commit a1ab30140eb9d98348b05ada960bb54bbfaba3bf (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Sun Dec 25 23:02:34 2022 -0500

    Cambios post-reset a Cambios al archivo de historia para reflejar la edad correcta. Se conserva los commits eliminados evitando el hard.
    
    Agregamos un cambio a su estatura
    
    Agregamos el cargo de la persona
    La persona es Diego
```

En la teoria todos los cambios previos a la version del reset debieron haber desaparecido, pero se sostuvieron por que no se hizo un --hard. Se haran unos nuevos cambios rápidos a history.txt

~~~~
Hoy hablaremos de su vida.
~~~~

$ git add src/history.txt 

$ git commit -m "Cambio de vida"

Se realiza otro cambio nuevamente:

~~~~
Hoy hablaremos de su vida y obra maestra.
~~~~

$ git add src/history.txt 

$ git commit -m "Cambio de maestria"

Ahora se visualizan los logs para ver los nuevos cambios con el flag --stat , para ver los cambios especificos que se hicieron, a cuales archivos a partir del commit.

$ git log --stat $

Se agregaron 10 bytes a blogpost y 6  estilos.css

```
src/blogpost.html   | 10 ++++++++++
src/css/estilos.css |  6 ++++++
```

Se tiene hasta la vida y obra maestra, pero digamos que quiero ver como era originalmente este archivo, en su primer commit.

$ git checkout a83b6365d0aa2ab6fa972aa904a66776e92a0451 src/history.txt $

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git checkout a83b6365d0aa2ab6fa972aa904a66776e92a0451 src/history.txt 
Updated 1 path from 3288ed6
```
En efecto se puede ver como era el archivo antes.
~~~~
 Esta es la historia de Diego 
 Diego tiene 32 aos y naci   en Colombia. 
 Hoy hablaremos de su historia.
~~~~
Si se revisa con git status, indica que se modificó history.txt y se está por delante de origin/main por 6 comits.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch main
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   src/history.txt
```
Si en vez del comando anterior se le indica que traiga el de main, se actualiza y retorna a la version main de history.txt que es la  última version commiteada, que es donde se hablaba de la vida y la obra maestra.

$ git checkout main history.txt  $

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git checkout main src/history.txt
Updated 1 path from 0e33502
```
En efecto retorna a la version requerida.
~~~~
Esta es la historia de Diego

Diego tiene 32.5 años y nací en Colombia,
viviendo en mi mente.

Hoy hablaremos de su vida y obra maestra.

En camara parece alto y realmente lo es.

Hoy es CS Engineer en Mercado Libre.
~~~~

Esto es muy peligroso, por que aca se puede ver lo que habia antes y lo que habia después, esta es la forma normalmente de volver a una versión anterior con git checkout y si se desea mantener permanente ese cambio. Simplemente se hace de la siguiente manera, se hace nuevamente el git checkout a la version inicial. 

$ git checkout a83b6365d0aa2ab6fa972aa904a66776e92a0451 src/history.txt  $

Y retorna a la parte donde aparece **Hoy hablaremos de su historia.**  Se va a cambiar por completo.

~~~~
Esta es la historia de Diego

Diego tiene 32 años y nacío en Colombia.

Mañana nos enfocaremos en su vida laboral.
~~~~

Ahora se trackear y se commitea el archivo.

$ git add src/history.txt

$ git commit -m "Reemplazo de una version por otra de la historia"

Se valida con git log --stat se puede ver que los cambios que se hicieron fueron 9 bytes en el archivo de src/history.txt y no se tocaron los otros archivos blogpost.html o estilos.css. Esta es la forma en que se puede volver atrás en los cambios, y luego volverlos a enviar a mi rama principal.

```
src/history.txt | 9 ++-------
```

<img src="/assets/git_rm_vs_git_reset.jpeg" align="center" />

interesante tiene un errorsito

<img src="/assets/git_rm_vs_git_reset2.jpeg" align="center" />

git rm vs git reset

<img src="/assets/git_rm_vs_git_reset3.jpeg" align="center" /> fredy barreiro



## 13. Git reset vs. Git rm

<img src="/assets/gitReset_RonDamon.jpeg" align="center" />

Git reset y git rm son comandos con utilidades muy diferentes, pero se pueden confundir muy fácilmente.

git rm
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

Recuerda que git rm no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

git rm --cached: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado untracked.
git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
git reset
Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
¡Pero todavía falta algo!

git reset HEAD: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.
La relevancia de estos comandos
Imagina el siguiente caso:

Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando git add. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo, pero ese cambio no debe ir en el próximo commit por ahora.

¿Qué podemos hacer?

Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

¡Al usar git rm lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

En cambio, si usamos git reset HEAD, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios, pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

Conclusión: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.

Aporte creado por: Juan David Castro



tree movements visualized

<img src="/assets/gitTreeMovementsVisualized.jpeg" align="center" />


### RESUMEN HASTA ACA
 
ahrcode

<img src="/assets/comandosBasicosGit.jpeg" align="center" />


### Flujo de trabajo básico en Git


## 14. Flujo de trabajo básico con un repositorio remoto


Flujo Git 

<img src="/assets/flujoGit.jpeg" align="center" />


"Tracked rastreado": 

"Untracked" o no rastreado" : Estaran en un lugar temporal, en caso de no hacer nada con dichos archivos eventualmente va a desaparecer por algo que se llama **Garbage collector**.

**¿Que pasa cuando trabajas con otras personas?**

Repositorio remoto: Típicamente puede ser Github, GitLab, BitBucket, servidor montado a mano ...

$ git clone (Trae una copia del main al directorio de trabajo y crea la base de datos de todoso los cambios en el repositorio local)

$ git push (Enviar al servidor remoto **Y si hay conflictos.. Lidio con ellos**)

Estoy conectado al remoto, ya lo clone pero quiero traer una actualizacion por que alguien cambió algo, ahí lo que se hace es:

$ git fetch  (Lo trae al repositorio local, pero no lo copia a los archivos)

Para que lo copie a los archivos se debe fusionar la ultima version que esta en repositorio local, con mi version actual y esto se llama un merge.

<img src="/assets/git_pull_fetch_merge.jpeg" align="center" />

**¿Para que debo hacer fetch y merge al mismo tiempo si en general yo lo que quiero es que me traiga al repositorio y al directorio?** 

Hay un comando que fusiona ambos conceptos, el comando pull.

$ git pull 

Se copia el repositorio local, la base de datos de cambios y a su vez al directorio de trabajo. De esta manera siempre tengo una copia actualizada de lo último que paso en el repositorio remoto.  


**Hay varios comandos de git log previamente** REVALIDAR

Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:

git log --oneline:Te muestra el id commit y el título del commit.
git log --decorate: Te muestra donde se encuentra el head point en el log.
git log --stat: Explica el número de líneas que se cambiaron brevemente.
git log -p: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
git shortlog: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
git log --graph --oneline --decorate y
git log --pretty=format:"%cn hizo un commit %h el dia %cd": Muestra mensajes personalizados de los commits.
git log -3: Limitamos el número de commits.
git log --after=“2018-1-2”
git log --after=“today” y
git log --after=“2018-1-2” --before=“today”: Commits para localizar por fechas.
git log --author=“Name Author”: Commits hechos por autor que cumplan exactamente con el nombre.
git log --grep=“INVIE”: Busca los commits que cumplan tal cual está escrito entre las comillas.
git log --grep=“INVIE” –i: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
git log – index.html: Busca los commits en un archivo en específico.
git log -S “Por contenido”: Buscar los commits con el contenido dentro del archivo.
git log > log.txt: guardar los logs en un archivo txt



## 15. Introducción a las ramas o branches de Git


En tu trabajo al principio se tiene una rama llamada main. Las ramas son formas en las que se pueden hacer cambios sin afectar la principal rama. Se va a hacer algo distinto con el blogpost.

Mientras la rama maestra va cambiando en blogpost normalmente habra una rama paralela que va a crearle un header. Esa rama se va a llamar cabecera, luego sera fusionada con main y asi entender el flujo de ramas dentro de git.

(HEAD) Commit mas reciente. Cuando se ven errores, por ejemplo Detach HEAD es por que se está viendo un commit mas viejo y la forma de volverlo a conectar es haciendole un checkout al HEAD del main.

Cuan do se crea una rama se crea una copia del ultimo commit en otro lado y todos los cambios que se hagan durante esta rama, no los va a ver la rama main, hasta que no se vuelva a fusionar con un proceso llamado merge.

Para ser mas claros que se va a cambiar la rama main y se va a crear una nueva rama donde va a estar la cabecera, se va a ajustar el blogpost, inicialmente el color rosado por un color negro, y se le van a haer unos cambios adicionales de diseño, para que se note cuando la cabecera entre, todo esto se hará en master. 

Se crea un contenedor donde se agrega un post, con un titulo y un parrafo. Y se modifica el estilo correspondiente color gris oscuro al texto y centrado, un container y al h1 se le redujo el tamaño. Con estos cambios se va a hacer un commit a master.

$ git commit -m "Commit al master del blogpost en su version mas reciente"

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log --stat
commit 2a9f6c9ac8ea8754e174e7796b59def82b70404b (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Tue Dec 27 00:34:00 2022 -0500

    Commit al master del blogpost en su version mas reciente

 src/blogpost.html   |  8 ++++++--
 src/css/estilos.css | 22 ++++++++++++++++++++--
 2 files changed, 26 insertions(+), 4 deletions(-)
```

La rama se va a crear desde el lugar donde estoy, actualmente el HEAD le esta apuntando a main. 

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch cabecera
CO0C02GD0T7MD6M:pro-git-github dposada$ git show
commit 2a9f6c9ac8ea8754e174e7796b59def82b70404b (HEAD -> main, cabecera)
```
Aparentemente no pasó nada, pero con git show se puede ver que indics que se tiene un HEAD que le indica a master y a la cabecera.
Es decir el ultimo commit esta pegado a 2 ramas distintas y todavia estoy trabajando en main.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch main
```
Ahora bien, para moverse a la rama cabecera se hace con:
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git checkout cabecera
M       notes/COMMANDS.md
M       notes/EXTRAS.md
M       notes/NOTES.md
Switched to branch 'cabecera'
```
IMPORTANTE:
~~~~
Si se está en MAC para visualizar mejor se recomienda instalar la consola zsh o iterm. Tambien puede usar git status.
~~~~

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch cabecera
```
Se va a hacer un cambio se va a crear la cabecera por primera vez en el blogpost y se commitea.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git commit -m "Estructura inicial de la cabecera"
```
luego con git show se puede evidenciar que:
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git show
commit f07a006b3d47445a4de140a7540303deccaa30a8 (HEAD -> cabecera)
```
Al utilizar git log se puede ver que el apuntador del HEAD estaba en main y pasó a la cabecera.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log
commit f07a006b3d47445a4de140a7540303deccaa30a8 (HEAD -> cabecera)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Tue Dec 27 00:54:09 2022 -0500

    Estructura inicial de la cabecera

commit 2a9f6c9ac8ea8754e174e7796b59def82b70404b (main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Tue Dec 27 00:34:00 2022 -0500

    Commit al master del blogpost en su version mas reciente
```
Ahora se va a retornar a la rama main y se observa que desaparecio el id de cabecera, al hacer un git log se evidencia que el ultimo commit fue la version mas reciente de blogpost y el HEAD ahora le apunta a master.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log
commit 2a9f6c9ac8ea8754e174e7796b59def82b70404b (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Tue Dec 27 00:34:00 2022 -0500

    Commit al master del blogpost en su version mas reciente
```
Entonces los cambios que se hagan acá, solamente van a ocurrir en master. Si se realiza nuevamente un checkout a cabecera se puede como cambian los archivos inmediatamente. Esta es la magia de Git, se pueden tener múltiples archivos cambiando, solo se guardan los cambios e inmediatamente se ven acá en cabecera. 

Si C2 es donde se tenian los cambios al blogpost, donde simplemente se creo la estructura básica, cuando se creó el branch cabecera se hizó una copia exacta de C2.  HEAD estaba apuntando a ambos commits porque en teoría son el mismo commit, **(HEAD -> main, cabecera)** Una vez se empezó a hacer cambios, y se hizo un commit nuevo C3, donde se agrego el div cabecera, esto ya no se ve en la rama master. Aqui el HEAD deja de estar acá, y va a apuntar al último cambio commiteado (HEAD de la cabecera). Cuando se hace un proceso de checkout para retornar a master, lo que se está haciendo es que todos los archivos en el directorio de trabajo, cambian al último commit de la rama a la que yo le estoy apuntando, y de repente el HEAD vuelve a estar acá. HEAD al final del dia es un indicador de cual versión de commit estoy viendo de los últimos archivos. 

<img src="/assets/intro_branches.jpeg" align="center" />

Las ramas (branches) son la forma de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

La cabecera o HEAD representan la rama y el commit de esa rama donde estamos trabajando. Por defecto, esta cabecera aparecerá en el último commit de nuestra rama principal. Pero podemos cambiarlo al crear una rama (git branch rama, git checkout -b rama) o movernos en el tiempo a cualquier otro commit de cualquier otra rama con los comandos (git reset id-commit, git checkout rama-o-id-commit).

Repasa: ¿Qué es Git?

Cómo funcionan las ramas en GIT
Las ramas son la manera de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

git branch -nombre de la rama-: Con este comando se genera una nueva rama.

git checkout -nombre de la rama-: Con este comando puedes saltar de una rama a otra.

git checkout -b rama: Genera una rama y nos mueve a ella automáticamente, Es decir, es la combinación de git brach y git checkout al mismo tiempo.

git reset id-commit: Nos lleva a cualquier commit no importa la rama, ya que identificamos el id del tag., eliminando el historial de los commit posteriores al tag seleccionado.

git checkout rama-o-id-commit: Nos lleva a cualquier commit sin borrar los commit posteriores al tag seleccionado.

<img src="/assets/git_data_transport_commands.jpeg" align="center" />



## 16. Fusión de ramas con Git merge

Se tiene la rama master y la rama cabecera, se va a crear un nuevo commit dentro de la rama cabecera, donde se van a hacer modificaciones al css y al html para que la cabecera se vea bonita, pero al mismo tiempo voy a crear un nuevo commit en master donde le voy a agregar contenido al blogpost, y al final se va a er que pasa cuando los dos archivos son distintos, y tenemos que fusionarlos en una version final donde esten ambos códigos, para digamos enviarlos a producción y hacer el merge. 

**Spoiler:** 

~~~~
Cuando se hace un merge realmente no se crea una tercera rama, lo que ocurre es que la rama desaparece (llega al final) y se une a su ruta final y el master continua con su vida. Luego se podrá crear otra rama en otra ocación, también puede que no se muera, y se sigan haciendo otras cosas y simplemente en algún futuro, se vuelva a hacer un merge. 
~~~~
El anterior es el tipico flujo de trabajo en la vida de Git, actualmente se esta en la rama cabecera **On branch cabecera** , se van a hacer unos cambios reales a la cabecera. Se agrega un tagline utilizando un span para poder usar estilos especiales dentro del css, color de fondo azul, negrita al titulo, ajustes normales pequeños en general, pero en resumen son cambios significativos al html y al css. **Si en este momento se hace checkout al master, se pueden perder los archivos, se necesita agregar a la cabecera estos cambios.** Ahora se commitean los cambios realizadas para esta rama.

git commit -m "Finalizada la cabecera con diseno azul"

git checkout master 

ya se sabe lo que va a ocurrir, se va a perder todo el avance que se ha hecho hasta ahora, en este momento el container sigue exactamente igual, no se han hecho casi nada de cambios, inicialmente se pretendia hacer un cambio de contenido. Ahora se va a agregar un nuevo parrafo dentro del contenido, y se va a agregar otro parrafo adicional.
Al refrescar y revisa en el browser se puede notar que se perdió la cabecera. ¿Porque? Por que estoy en este momento en la version main, peros e le agrego este parrafo y no se ha hecho ningun cambio en el css, pero hagamos un cambio ahora en el css, se va a cambiar la fuente de Arial por Courier, y al recargar el post ahora se ve horrible ... por que es courier ... pero se hizo un pequeño cambio donde ahora la versión de main esta en Courier y la version final tiene un parrafo adicional. 

Recordar si no se hace un add y un commit se van a perder estos cambios. Ahora se commitea a la rama main.

git commit -m "Finalizada la cabecera con diseno azul"

Ahora se retorna a la rama cabecera, y si se recarga el browser vuelve a aparecer la cabecera, la fuente sigue siendo Arial y no se tiene el segundo parrafo, es decir se tiene otra cosa. ¿Que se quiere ahora? La fuente en Courier, que es el cambio realizado en main, y el parrafo adicional ... pero se quiere tener este diseño super cool que se hizo en la rama cabecera, entonces **¿Como es que hago un merge?** Para esto, debo cambiar en donde estoy, el merge siempre va a ocurrir en la rama donde estoy y es a donde me voy a pegar. Si estando en cabecera hago un merge con main, lo que se hace es mandar C3 de la rama main a apuntar a la cabecera y se pierde todo esto (c1 + c2). Realmente no se pierde sino que este (C4) se vuelve el principal. 

<img src="/assets/git_merge_branch_fusion.jpeg" align="center" />

Esto no es lo que queremos, lo que yo quiero es traerme a main lo que se hizo en cabecera. Entonces se debe hacer un checkout de main, y poner el HEAD en main y acá se invoca el comando merge de cabecera y esto lo que va a hacer es crear un commit nuevo dentro de main que va a traer el último commit de main, y el último commit de cabecera y los va a fusionar. Si llega a haber un conflicto, por ejemplo que 2 lineas hayan sido afectadas por la misma persona va a disparar un conflicto y alguien lo tiene que arreglar y no va a permitir hacer el merge. En este caso no se creó ningun conflicto entonces el merge va a trabajar magicamente. Este es el final de la rama cabecera, y esta es la continuación de la rama main.

<img src="/assets/git_merge_cabecera.jpeg" align="center" />

La rama principal es main, por ende:

$ git checkout main 

La rama main tiene este diseño terrible pero tambien el parrafo adicional.

<img src="/assets/main_with_courier.jpeg" align="center" />

La rama cabecera es la del diseño super cool y la cabecera.

<img src="/assets/branch_cabecera.jpeg" align="center" />

Y ahora lo que se hace es git merge con el nombre de la rama. 

git merge cabecera

Si se recuerda bien un merge es un commit a la rama donde se esta haciendo la fusión, en este caso la rama main por ende tiene un mensaje.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git merge cabecera
Auto-merging src/blogpost.html
Auto-merging src/css/estilos.css
Merge made by the 'ort' strategy.
 src/blogpost.html   |  4 ++++
 src/css/estilos.css | 24 +++++++++++++++++++++++-
 2 files changed, 27 insertions(+), 1 deletion(-)

```

$ git log

```
commit d523138aa92e1bdda16293dd6db4f25dca624ea2 (HEAD -> main)
Merge: e3ef15b 0f7e06a
Author: DiegoAll <dposadallano@gmail.com>
Date:   Thu Dec 29 00:13:53 2022 -0500

    Merge branch 'cabecera'

commit e3ef15b841319df3f7cf26f75523b98ac3f13cc2
Author: DiegoAll <dposadallano@gmail.com>
Date:   Wed Dec 28 23:21:09 2022 -0500

    Agregado el contenido adicional del blog y una mejor tipografia

commit 0f7e06a6707d16b76013316e537f61554e13cf9f (cabecera)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Wed Dec 28 01:37:47 2022 -0500

    Finalizada la cabecera con diseno azul

```
Este es el resultado, el ultimo commit de la rama cabecera, el ultimo commit de la rama main y el nuevo commit que es un merge de ambos. Se tiene la cabecera, y el tagline, se tiene el parrafo inicial y el que se habia creado por otro lado, y en estilos me mantuvo el courier que se modifico, pero tambien agrego todos los estilos de tagline, container etc. Quedó perfectamente fusionado.
Ahora se tiene una version canonica y definitiva en el nnuevo commit generado por el merge.

<img src="/assets/git_merge_main_cabecera.jpeg" align="center" />


```
Merge: e3ef15b 0f7e06a
```
Observar que en el commit del merge no se tienen los hash largos sino una porción, Opcionalmente se puede usar todo el hash o solo un pedazo del hash, por que estos son lo suficientemente distintos. Esto no es verdad a medida que el proyecto se hace mas grande, pero por ahora si.

Si se quiere hacer un cambio adicional, se puede volver a una fuente que no sea tan terrible como Courier ... Arial no es que sea perfecta pero pues sirve ... y nuevamente se hace lo debido un commit. 

$ git commit -m "Volvi a una tipografia menos controversial"

¿Que pasa cuando hay un conflicto?

¿Que pasa cuando 2 programadores cambiaron las mismas lineas de codigo y son diferentes?


## 17. Resolución de conflictos al hacer un merge

ya se hizo el merge entre master y cabecera, pero como quedo cabecera? Master quedo super bien. Si se retorna a la rama anterior.

git checkout cabecera 

Y no es como que se borre por que Git nunca borra nada, todo sigue existiendo en la historia de tus ramas, se corrobora y es el mismo post que habia anteriormente. Entonces algo que se puede hacer es hacer el merge al reves, traernos lo de master a cabecera, se hace exactamente igual. Desde cabecera se hace un git merge con master.

$ git merge main

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git merge main
Updating 0f7e06a..82ae293
Fast-forward
 src/blogpost.html | 1 +
 1 file changed, 1 insertion(+)

```

Al recargar se puede ver que se tiene todo lo que se tenia antes, y observar que la fuente por defecto es arial no es courier, trajo incluso el otro commit que se habia hecho antes, teniendo en mente que se tuvo un commit que quito el courier y se volvio a colocar arial, entonces este es el ultimo commit que se tiene en master. Cuando se hace un merge, desde cabecera se hace en la otra dirección, y se trajo el contenido ultimo, mas el contenido que se habia cambiado para retornar a la tipografia arial, y se mega en un nuevo commit, basicamente en ambos lugares se tiene lo mismo. Los merge funcionan en una u en otra dirección.

Se va a simular un conflicto, en la cabecera se va a crear un nuevo commit, donde se va a modificar el css y el html,  y en el master se va a crear otro commit donde se va a modificar las mismas lineas en el css y en el html. Cuando se haga el merge y se trate de unir esos cambios hacia main, git va a retornar un error.

Se va a arrancar desde la rama cabecera cambiando la cabecera, en vez de decirle que es Mi blog de confianza en la linea 10 se va a indicar que es mi blog de cabecera. y en el css en vez de decir que elcolor es gris oscuro, se va a color en un color rojo. Se refresca y se pueden evidenciar los cambios realizados. Ahora se commitean estos nuevos cambios.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git commit -m "Modifique la cabecera y el color del texto"
[cabecera 64aa64e] Modifique la cabecera y el color del texto
 2 files changed, 2 insertions(+), 2 deletions(-)
```

Ahora vamos a la rama main, aca no se colocara en el tagline que es tu blog de confianza sino que es tu blog maestro, para recordar que esta es la rama master, y aca en vez de mantenerlo gris se va a colocar azul. Se recarga y se reflejan los cambios realizados.

Es decir tengo 2 conflictos, simplemente por practicar voy a hacer algo mas y es que en el blog maestro, se va a gregar un parrafo adicional, donde diga suscribete y dale like.  Ahora se vuelve a hacer un commit.

git commit -m "Agregue suscripcion, cambie la cabecera maestra y puse todo azul"

Ahora vamos a retornar a cabecera que dice ahora, tu blog de cabecera y todo esta en rojo.

El parrafo agregado en main no deberia de dar ningun problema por que es una adicion.
```
<p> Suscribete y dale like </p>
```
Pero esta linea del blogpost si que deberia generar problemas, 
```
<span id="tagline">Tu blog maestro</span>
```
Y esta linea del archivo de estilos tambien.
```
  color: blue;
```
Se esta en main, se van a fusionar los cambios de cabecera a los cambios main. Todos los cambios que se hicieron en cabecera van a generar conflicto. Mientras que los cambios main no deberia generar conflicto el nuevo parrafo. Desde main se van a traer los cambios de cabecera es decir fusionar cabecera.

$ git merge cabecera

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git merge cabecera
Auto-merging src/blogpost.html
CONFLICT (content): Merge conflict in src/blogpost.html
Auto-merging src/css/estilos.css
CONFLICT (content): Merge conflict in src/css/estilos.css
Automatic merge failed; fix conflicts and then commit the result.

```
<img src="/assets/main_cabecera_conflict.jpeg" align="center" />

en los archivos se puede ver lo siguiente, tanto en los estilos:

<img src="/assets/conflict_estilos.jpeg" align="center" />

Y en el blogpost el siguiente conflicto:

Si se observan los logs se puede ver el ultimo cambio que se hizo

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log
commit fd7397b35419b9ec674d91b7d66ce17cb83dfdf5 (HEAD -> main)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Thu Dec 29 23:04:02 2022 -0500

    Agregue suscripcion, cambie la cabecera maestra y puse todo azul
```
Fue lo ultimo que se hizo y en este momento no se tiene un merge completo. Se esta en un estado muy raro, main merging significa que el merge no se completo, para que se complete un merge tiene que ocurrir un commit. 


Los links que aparecen en las imagenes son una forma en la que VS Code facilita el proceso. Se puede ir a revisar y aparece la sintaxis de un conflicto para ambos archivos.

```
<<<<<<< HEAD

=======

>>>>>>> cabecera
```
Lo que se haria es resolver a mano este conflicto es borrar las lineas implicadas al cambio y decidir con que color me quiero quedar para el css. En este caso se elegira de color #333 por que es el color mas adecuado.

Pero que pasa con el otro? ese proceso de borrar las lineas lo hace automaticamente VSCode, y pregunta quiero aceptar el cambio actual o el cambio que viene. En este caso se va a aceptar el cambio que viene. "Tu blog de cabecera". Borra todo y automaticamente me deja blog de cabecera. Se corrobora con git status para saber que fue lo que paso:

```
On branch main
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   src/blogpost.html
        both modified:   src/css/estilos.css
```
Indica que ambos cambios fueron modificados, no esta todavia el merge completo. Esto es importante, como se hicieron cambios 
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git commit -m "Solucione el conflicto de las ramas al fusionar"
[main 99b5a9e] Solucione el conflicto de las ramas al fusionar
```
Y listo se soluciono el conflicto de las ramas. Se revisa con git status y se corrobora el merge.
```
commit 99b5a9ec5a2a3e27a92403318d7b7a1c7d541fa7 (HEAD -> main)
Merge: fd7397b 64aa64e
Author: DiegoAll <dposadallano@gmail.com>
Date:   Fri Dec 30 00:11:13 2022 -0500

    Solucione el conflicto de las ramas al fusionar
```
Si se le hace un checkout a cabecera, se identifica que se continua con la version anterior por que el merge se mando a main. Continua de color rojo con el blog de cabecera.

Esta es la manera en que se solucionan conflictos en Git, son lo mas natural del mundo. No entrar en panico cuando aparezca un conflicto. Es tan sencillo de arreglar como esto. Los conflictos son parte normal del proceso de trabajo, imagina que se trabaja con 2 personas mas, y a una de esas personas le toco hacer un cambio de ultima hora en el mismo lugar del codigo donde tu lo estabas haciendo, y no te enteraste por que ese cambio a ultima hora lo necesitaba el cliente. Digamos que cambio por completo el logo de la empresa y el nombre entonces se debe modificar de una forma muy rapida, ellos probablemente van a crear una rama que se llama hotfix, o arreglo de bugs, y luego le van a hacer un merge con master una vez terminan ese arreglo. Y tu sigues trabajando tranquilo y no te enteras de estos cambios.
Lo correcto en ocaciones es tratar de traer estos cambios, para que te enteres del conflicto, y lo arregles antes de hacer el merge.
Pero si no ocurre, y vas a hacer el merge y te encuentras con ese conflicto, lo que hay que hacer es pararte de tu puesto, ir a hablarle a la persona,  entender cual fue el cambio y modificarlo. Al final del dia git te va a traer el codigo de la otra persona, y lo va a comparar con tu codigo, y va a mostrartelo en cada una de estas partes, estos conflictos pasan todo el tiempo y tambien pueden pasar al reves, tu puedes crear codigo que luego le genere un conflicto a alguien mas, y alguien tiene que decidir si borrar tu codigo, o si aceptar el codigo  que tu tenias, estas cosas normalmente se solucionan con comunicación entre el equipo. Recordar que en git nunca se va a borrar nada, se puede ver un registro preciso, perfecto y exacto, de quien hizo cuales cambios, donde y de que manera.


### Trabajando con repositorios remotos en GitHub

## 18. Cambios en GitHub: de master a main

Por lo anterior podemos afirmar que los sinónimos no expresan lo mismo, no tienen el mismo “color” ni el mismo “peso”.
Sí, esta lectura es parte del curso profesional de Git & GitHub. Quédate conmigo.

Desde el 1 de octubre de 2020 GitHub cambió el nombre de la rama principal: ya no es “master” -como aprenderás en el curso- sino main. Este derivado de una profunda reflexión ocasionada por el movimiento #BlackLivesMatter.

La industria de la tecnología lleva muchos años usando términos como master, slave, blacklist o whitelist y esperamos pronto puedan ir desapareciendo.

Y sí, las palabras importan.

Por lo que de aquí en adelante cada vez que escuches a Freddy mencionar “master” debes saber que hace referencia a “main”


https://platzi.com/blog/cambios-en-github-master-main/



## 19. Uso de GitHub

Sitio web tiene por dentro un superservidor de Git en el que cualquiera puede crear o clonar un repositorio y compartirlo con otras personas. Es una especie de interfaz visual de los repositorios, es una de las herramientas colaborativas mas importantes que existen en el mundo del desarrollo. Comunmente conocida como la red social de los programadores, por que los repositorios son tu "portafolio" de proyectos como programador.

Opcion principal  **( + )**

<img src="/assets/github_principal_option.jpeg.jpeg" align="center" />

- New Repository:

- Import repository: Solo funciona si el repositorio está online. Los obtiene de otros sistemas, ej (Subversion).

- New Organization: Significa que es como tu empresa, puedes trabajar para multiples empresas ... 

- New project: es como un grupo de repositorios que puedes tener dentro de una empresa, o no.

- New gist: Es una porción de código que se puede compartir.

Se va a crear un repositorio nuevo que va a ser el que determine nuestro proyecto, se llamara hyperblog en mi caso **pro-git-github** con una descripción. 

Se elige la opción de inicializar un repositorio con un readme, es una muy buena práctica. Crea en la raiz del proyecto un archivo que se llama readme.md, este archivo de texto le permite wexplicr a las personas que abren el repositorio, ¿Qué es el repositorio?
Luego pregunta si se desea agregar un git ignore o una licencia. Hay muchas licencias a través de las cuales se puede publicar el código, por ejemplo licencias de código abierto, semiabierto, por ahora se le dice que no y se hará luego. Se deja público el repositorio. Se crea y ya se tiene una dirección:

https://github.com/DiegoAll/pro-git-github


En el readme se puede ver que aparece raw, blame, history

- code: Vista de código.

- raw: muestra el código plano que creo este texto.

- blame: quien tiene la culpa de las cosas que se han hecho.

- history: Muestra la historia de este archivo. Esto es lo mismo que hacer un log dentro del repositorio.


**¿Pero como le traemos al hyperblog todas las cosas cool que se han hecho?**

Primero que todo, donde dice Code / Local / Clone / HTTPS para clonar el repositorio, se puede utilizar HTTP o SSH.
Se le va a decir a Git que se va a agregar un origen remoto de nuestros archivos:

$ git remote add origin https://github.com/DiegoAll/pro-git-github.git

Pareciera que no paso nada pero, si se ejecuta el comando:

$ git remote

Se puede ver que existe algo llamado origin.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git remote
origin
```
~~~~
Nota: El repositorio fue creado inicialmente desde Github, por ende ya tenia el remoto configurado.
Cuando se crea de forma local si requiere la configuración del remoto.
~~~~

Y si se ejecuta el comando:

$ git remote -v   (verbose)

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git remote -v
origin  git@github.diegoall:DiegoAll/pro-git-github.git (fetch)
origin  git@github.diegoall:DiegoAll/pro-git-github.git (push)
```
Muestra que se tiene un origin para hacer fetch (traernos cosas) y se tiene un origin para hacer push (enviar cosas).
Con eso ya estamos listos. Ahora para poder enviar el hyperblog al repositorio remoto se ejecuta:

$ git push origin main

Indica a Git que le envie al origen, es decir a la URL seteada como parametro en los comandos anteriores la rama main.

Si se está en Windows utilizando git bash va a aparecer una ventana para autenticarse, o en consola aparece un indicador para especificar nombre de usuario y contraseña de Git es todo lo que se debe hacer. Actualmente debe generarse un Token.

Luego empezará a hacer el push.

Observar el error que aparece. Las actualizaciones fueron rechazadas, por que el remoto contiene trabajo que no tienes localmente,  
esto normalmente es causado porque otro repositorio está empujando al mismo lugar, LO primero que debe hacer es integrar los cambios remotos, antes de volver a hacer un push. Y esto es completamente verdad, por que tu no sabes que paso en el miundo remoto.
Yo si se en el mundo remoto se tiene un archivo que se llama README.md y ahora este es el main. Teniendo en cuenta que esto pasa, hay que traerlo al repositorio local primero. 

Se puede hacer git fetch y luego git merge, o se hace lo que todo el mundo hace git pull.

$ git pull origin main

```
warning: no common commits
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/diegoall/hyperblog
* branch        main    -> FETCH_HEAD
* [new branch]  main    -> origin/main
fatal: refusing to merge unrelated histories
```

delta son basicamente los cambios que existen, a los servidores no se les envia todo el código sino los cambios mínimos necesarios.

La rama main es el FETCH_HEAD que es lo que se esta trayendo, el fetch es de donde vienn todos estos archivos, y ahora se tiene una nueva rama main que es origin/main, basicamente ya se esta conectado. Y entrega el siguiente error. "Me rehuso a fusionar historias no relacionadas" ¿Que significa eso? qie ña historia de todos estos commits, el README.md es una historia distinta. Una historia es un grupo de commits, la historia remota distinta a la historia local. Hay una forma en la que se puede forzar a que esto ocurra:

$ git pull origin main --allow-unrelated-histories

De esta manera permite fusionar lo que habia allá, con la rama que se tiene local (homologarlas). Esto es un caso super aislado y tiene que ver mucho con la estructura en que github crea estos primeros archivos, se ejecuta el comando y aparece una ventana donde se visualiza que si esta permitiendo hacer el merge con la rama main de hyperblog. Acto seguido debe traer el README.md. 

En mi caso como ya habia realizado push no aparece este error. Empieza a comprimir, resuelve los deltas, el main local se envia al main de Github.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin main
Enumerating objects: 78, done.
Counting objects: 100% (78/78), done.
Delta compression using up to 6 threads
Compressing objects: 100% (67/67), done.
Writing objects: 100% (77/77), 7.08 KiB | 426.00 KiB/s, done.
Total 77 (delta 34), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (34/34), completed with 1 local object.
To github.diegoall:DiegoAll/pro-git-github.git
   9be2b8d..99b5a9e  main -> main
```
Se puede corroborar en el repositorio remoto que los cambios fueron subidos.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch main
Your branch is up to date with 'origin/main'.
```
Ahora se puede evidenciar a nivel local que no hay nada que enviar.

En el repositorio remoto se le puede dar a blame y se visualiza quien realizó los cambios. (Aparece la información seteada en el repositorio local).

```
user.email=dposadallano@gmail.com
user.name=DiegoAll
```

<img src="/assets/git_blames.jpeg" align="center" />

También puede realizar desde Github es decir el entorno web cambios en los archivos, por ejuemplo en el blogpost.html se va a editar el título, simplemente un cambio pequeño.

```
<title>Bievenido al blog</title>
```
Ahora bien, puede realizar un **Preview** a los cambios y posteriormente un **commit**. Tambien puede seleccion el correo desde el cual realizara el commit y donde se quiere hacer, se creará una rama nueva? o si se hará directamente sobre la rama main. No hay que hacer add, con el commit es suficiente y el cambio queda aplicado. 

<img src="/assets/commit_from_Github.jpeg" align="center" />

Entonces cual es el status en este momento? se tiene una historia en Github en la que el main está acá con el último cambio reciente. Pero eso no se ve reflejado en el repositorio local. Si se observa el blogpost sigue con el título antiguo:

```
<title>Diego BlogPost</title>
```

**¿Qué es lo que se debe hacer?**

Recordar

$ git pull origin main

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git pull origin main
From github.diegoall:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
Updating 99b5a9e..27ede0b
Fast-forward
 src/blogpost.html | 4 ++--
 1 file changed, 2 insertions(+), 2 deletions(-)

```
Y en efecto actualizó el archivo, ahora aparece **Bievenido al blog** , ahora se ejecuta un git log.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log
commit 27ede0ba50a8c895bfd0d1cfe4fa1ed824bd31b5 (HEAD -> main, origin/main, origin/HEAD)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Mon Jan 2 21:42:38 2023 -0500

    Cambie el titulo del blogpost
    
    Porque puedo
```
Muestra el correo seleccionado para el commit, e indica que en este momento el HEAD está actualizado con main, y con el main que está en el origin. Origin se refiere a lo que se tiene arriba en Github. Con este ya se tiene todo lo necesario para que todos los proyectos vivan en internet. Se puede acceder desde la url **https://github.com/DiegoAll/pro-git-github**
Si se le da click a commits, se puede ver toda la historia incluyendo, la historia entera inicial que se creo en el proyecto local, al enviar el proyecto local a github subió todo.


## 20. Cómo funcionan las llaves públicas y privadas

Se pretende que nadie se entere de este mensaje secreto, en el proceso de transmision puede ser interceptado. Lo que se hace es cifrar este mensaje utilizando una contraseña para esto, el problema es ¿Como enviar esta contraseña para cifrar este mensaje? y eliminar el riesgo de que esta tambien sea interceptada. Inventaron un algoritmo que se llama llaves publicas, y llaves privadas. Tambien conocido como cifrado asimétrico, de un solo camino. 
Si yo quiero que me envien algun mensaje secreto, yo creare algo llamado llave publica y una llave privada. Estas llaves se crean con un proceso algorirmico, algo relativamente sencillo. Las llaves estan vinculadas matematicamente una con la otra.  Esto implica que lo que yo cifre con mi llave publica solo lo abre mi llave privada. La llave privada no se comparte por nada del mundo. Se comparte la llave publica, tu la recibes. Dicha llave es como un proceso matematico, es convertir ese mensaje secreto en algo completamente oculto. Esta llave publica puede ser interceptada, incluso puede ser publicada en interne, en un blog o sitio web.
Esta llave publica sigue conectada matematicamente con tu llave privada, ambas fueron creadas al mismo tiempo. 

Acá esta la magia, tu copias una version de la llave publica tomada de algun lugar, con esta llave publica se hace un proceso matematico, se cifra el mensaje con la llave publica que yo genere. A partir de este proceso se genera un nuevo mensaje. Al pasar el mensaje secreto por mi llave publica, queda algo completamente imposible de descifrar, es decir un mensaje cifrado. 

No importa que lleve un hacker de internet y logre interceptar todo. Tanto la llave publica y el mensaje. Pasaran años, cientos ade años, milenios y con estos parametros no podran descifrar este mensaje secreto. Esa es la magia de todo este proceso, no import que tomen estos valores no van a poder tomar el mensaje cifrado sin la llave privada.

¿Pero como lo obtengo yo?

Se copia este mensaje que llega de internet a través de un mensaje o algún otro método, y usas tu llave privada para transformarlo (descifrarlo) en el mensaje que fue enviado inicialmente. Esta es la magia de una llave publica y privada. 


<img src="/assets/llavespubpriv.jpeg" align="center" />


Este es un cifrado tan poderoso que asi funcionan todas las finanzas del mundo. 


## 21. Configura tus llaves SSH en local

Al conectarte a Github, se utilizo el nombre de usuario y contraseña, esto tiene 2 problemas.

1. Siempre debe estarse haciendo. (Autenticación)

2. En principio es una conexión segura (HTTPS), sin embargo el nombre de usuario y contraseña se estan guardando en tu entorno local. 

Implica que si el laptop es robado, eres vulnerable a password cracking. Es muy critico si entran al codigo fuente, pueden acceder al servidor, al proyecto o al de los clientes, realizar cambios, agregar huecos de seguridad, esta es la forma en que los sitios web son hackeados. Para evitar esto, se debe agregar una capa de seguridad mucho mas fuerte, como ya se aprendio que son llaves publicas y privadas se puede crear ese entorno en Git y Github. Tiene otra ventaja, no solamente la seguridad es mas fuerte, sino que ademas no se tienen que volver a colocar las credenciales. 

En tu entorno local (laptop) se va a crear una llave privada y una llave publica. Una vez son creadas se envia es llave publica al repositorio de Github. Se le indica a Github, para este repositorio, quiero que se use esta llave pública de mi llave privada (va a seguir siendo privada en mi laptop) y se establece la conexión por protocolo SSH. 

En la primera conexión Github se da cuenta que fue enviada una llave pública que está correlacionada con la llave privada. Y te va a enviar cifrado con tu llave pública, **su propia llave pública de Github.** Por que Github tambien tiene una llave privada. Todo esto es automatico, no hay que hacer nada. Github envia esta llave publica y yo la voy a conectar. Como yo tengo la llave pública de Github cifrada, y Github tiene tu llave publica, entonces a partir de ahora puede haber una conexión de doble camino, 100 % cifrada por SSH y ya nunca más se debe agregar contraseña.

```
(base) MBPdeDiego:pro-git-github mac$ cat ~/.ssh/known_hosts

192.168.64.2 ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBMGZBAXo/ottjCw0n7nS+1yumW/Mtz150a1l5svIUXlPCilRwMWjNPQQ483jnUQoB1xVHTcAquWbtnKKrdDs7Dw=

167.99.227.196 ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFPP/mKjxrB49hCEM7oW++bWYfGsoGT39zpSu60RGURdllMIqyTaGX/md1I9Rjq1zmblYJAg3ijE9s0bXj7smD8=

192.168.1.5 ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBMDuoTtkHDpKXupGt8xBiLbYm+x4UwukzpSLdD8H1O7n0TX6UvF5vPsbvXL49T1xynW0rb6SoA6Lw3Slbg9Tbus=

github.com,140.82.112.4 ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBEmKSENjQEezOmxkZMy7opKgwFB9nkt5YRrYMjNuG5N87uRgg6CLrbo5wAdT/y6v0mKV0U2w0WZ2YB/++Tpockg=
```

Algo a agregar es que a la llave privada que se cree se le puede crear una llave simétrica encima para hacerla aun mas fuerte y aún mas poderosa. Y adicionalmente a esto, se debe estar cifrando tu disco, en Windows se cifra con BitLocker o en MAC como una opción en la configuración de seguridad. 

Ahora en la práctica, se tiene un repositorio pro-git-hub en mi Github DiegoAll al que eventualmente se van a conectar y empezaran a hacer algo llamado **Pull Request**, por ahora primero SSH.

Las llaves SSH no son por repositorio o por proyecto, sino por persona. Se van a crear una serie de llaves exclusivas para tu usuario.


#### Generar llaves para pro-git-github


Actualmente el repositorio tiene configurado estos correos (diego58229@hotmail.com ; dposadallano@gmail.com)

Se utilizará el correo dposadallano@hotmail.com desde MacbookPro Ancestro

$ git config --global user.name "Diego All"

$ git config --global user.email "dposadallano@hotmail.com"

$ git config -l


Crear llave SSH

$ ssh-keygen -t rsa -b 4096 -C "dposadallano@hotmail.com"

-t algoritmo con el que se creara la llave

-b que tan compleja es la llave

-C a que email va a estar conectada esta llave

Luego solicita un passphrase (password sin espacios) contraseña adicional de texto qu se le va a colocar a la llave pública y privada.

Para efectos del curso se puede dejar sin passphrase, por temas de seguridad le voy a colocar por ser un correo personal antiguo.

Finalmente genera el par de llaves en la ruta /Users/mac/.ssh/

```
(base) MBPdeDiego:~ mac$ ssh-keygen -t rsa -b 4096 -C "dposadallano@hotmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/mac/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/mac/.ssh/id_rsa.
Your public key has been saved in /Users/mac/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:7/fvBXwiG2unp/CMVhJwDEbyl7BF0/wojP9IV7gvpUY dposadallano@hotmail.com
The key's randomart image is:
+---[RSA 4096]----+
|      ..=++o     |
|       +.+ooo    |
|        o=o  +   |
|        ..+ o.o  |
|        S. ooo+ .|
|         .+ E=.+ |
|         .oB++. .|
|         .o**oo .|
|         .oo==.oo|
+----[SHA256]-----+
```

fingerprint es basicamente una forma de confirmar de que la llave es de verdad. randomart image es otra forma de saber que la llave es de verdad, y otra forma de compartir la llave.

Para ver con que correo fue generada la llave publica se puede visualizar el archivo de la llave pública.

$ cat /Users/mac/.ssh/id_rsa.pub.

Ahora se pretende llevar esta llave pública a Github, se copia la llave al portapapeles.

No es suficiente lo que se hizo, el proceso es diferente en Windows, Linux y Mac. Curiosamente en Windows y Linux es identico el proceso, pero en Mac es leve diferente. Porque una vez se tiene la llave se debe agregar al entorno, es basicamente que el SO donde se tabaja sepa que la llave existe. Revisar que el "servidor de llaves ssh" esté activado, basicamente un pequeño programa que este revisando que las llaves esten corriendo, y que las conecte para hacer la conexión doble, cuando se realice la conexión a un servidor remoto o a GitHub.

$ eval $(ssh-agent -s)

Significa que el servidor de ssh está corriendo. Ahora se agrega la llave a nuestro sistema, es agregarla a ese servidor. Que la llave exista no es suficiente, debe indicarse que existe. Se puede utiliza el simbolo de la Ñ para acceder al HOME, es simplemente una variable **~** (shortcut)

```
CO0C02GD0T7MD6M:pro-git-github dposada$ ~ 
bash: /Users/dposada: is a directory
```
$ ssh-add ~/.ssh/id_rsa


**Para Mac**

Evaluar si esta corriendo el ssh-agent

$ eval "$(ssh-agent -s)"

```
(base) MBPdeDiego:~ mac$  eval "$(ssh-agent -s)"
Agent pid 3995
```

Si estás usando macOS Sierra 10.12.2 o una versión posterior, deberás modificar tu archivo ~/.ssh/config para cargar las claves automáticamente en el agente ssh-agent y almacenar las contraseñas en tu cadena de claves (Propio de MacOS). De no existir debe ser creado.

$ touch ~/.ssh/config

Modifica el archivo para que contenga las líneas siguientes.

~~~~
Host *.github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
~~~~

$ ssh-add -K ~/.ssh/id_rsa

-K keychain (Acceso a llaveros es propio de MacOS, app del SO donde se guardan los nombres de usuario y contraseñas para compartir por ICloud) 

```
(base) MBPdeDiego:~ mac$ cat ~/.ssh/config
cat: /Users/mac/.ssh/config: No such file or directory
(base) MBPdeDiego:~ mac$ ssh-add -K ~/.ssh/id_rsa
Enter passphrase for /Users/mac/.ssh/id_rsa: 
Identity added: /Users/mac/.ssh/id_rsa (dposadallano@hotmail.com)
```

En el Macbook-home no fue necesario agregar el archivo config.

**Notas**

Si decides no agregar una frase de contraseña a la clave, debes omitir la línea UseKeychain.

Si ves un error Bad configuration option: usekeychain, agrega una línea adicional a la sección Host *.github.com de la configuración.

Host *.github.com
  IgnoreUnknown UseKeychain

[Generación de una nueva clave SSH y adición al agente SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)



## 22. Conexión a GitHub con SSH

Las llaves estan creadas, se tiene una carpeta -ssh en el HOME de la carpeta del usuario en el entorno local. Importante aclarar algo, cada usuario, cada pc, cada persona, tiene que tener una llave unica. Si tienes 3 laptops, se deben tener 3 llaves conectadas con el repositorio remoto, o no va a funcionar. No es buena idea compartir estas llaves, se puede pero no es buena idea.
Debes crear una llave publica y privada por cada repositorio. ¿Por que no es buena idea? Por que es tu llave privada, si en algun punto fue transferida de un PC a otro, existe la oportunidad de que la hayan interceptado, asi haya sido transferida en una USB, se podria revisar que bits habian antes, Se recomienda siempre que haya una llave privada y una llave publica por cada laptops que uses.

[Agregar una clave SSH nueva a tu cuenta de GitHub](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

$ pbcopy < ~/.ssh/id_rsa.pub

Se copia este contenido de la llave publica en la configuracion de Github y listo ya esta, indica que la llave fue agregada y nunca ha sido usada. Ya se tiene conectado el repositorio de Github con la llave publica generada para la cuenta dposadallano@hotmail.com en el (Diego All macbookpro-home)

<img src="/assets/github_id_rsa_conf.png" align="center" />

Ahora se va a probar, se clonara el repositorio utilizando SSH. 

$ git clone git@github.com:DiegoAll/pro-git-github.git

En efecto el repositorio pudo ser clonado exitosamente.


**Nota:**

Ahora bien el objetivo de la clase era utilizar conexiones SSH con Github, por ende la configuracion del repositorio remoto debe ser ajustado ya que previamente se habia configurado con HTTPS.

$ git remote -v

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git remote -v
origin  https://github.com/DiegoAll/pro-git-github.git (fetch)
origin  https://github.com/DiegoAll/pro-git-github.git (push)
```

El repositorio que se viene usando se llama origin, cabe aclarar que origin es simplemente un estandar de la industria se hubiera podido llamar perfectamente "pepe", se pueden tener multiples repositorios remotos a los cuales conectarse. Dependiendo del proyecto, por ejemplo de codigo abierto muy complejos eso es muy normal, pero en la gran mayoria de los flujos de trabajo la palabra es origin. Entonces lo que se hara es cambiar la URL de origin, esto en teoria no deberia generar ningun problema, 

$ git remote set-url origin git@github.com:DiegoAll/pro-git-github.git

Despues del cambio se corrobora el cambio.

$ git remote -v 

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git remote -v
origin  git@github.com/DiegoAll/pro-git-github.git (fetch)
origin  git@github.com/DiegoAll/pro-git-github.git (push)
```

**¿Como saber si funciona?** Haciendo cambios por supuesto entonces se retornara a la programación habitual.

Se va a hacer un pequeño cambio en el blogpost, en el titulo se pondra.

**Utilizando ancestro**

```
<title>Bievenido al blog</title>
```

Lo primero que hay que hacer antes de hacer un commit es traerme la ultima version del servidor.

$ git pull

**¿Porque no uso git pull origin main? Debe ser por el remote configurado.**

Observar que por primera vez esta diciendo, la autenticidad de ese tal github.com .. esta de acuerdo con esto? yes

```
pendiente esta en el correo
```
En el ancestro funciono correctamente y actualizo los fuentes.

Pero en el curso aparece lo siguiente:

```
There is no tracking information for the currect branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.
    git pull <remote> <branch>

If you wish yo set tracking information for this branch you can do so with:

    git branch --set-upstream-to_origin/<branch> main
```

Se va a hacer lo mismo que se hizo antes , un git pull origin por que se va a traer del origen (nombre del repositorio remoto), y se va a fusionar con la rama actual que es main.

$ git pull origin main

```
From github.com:freddier/hyperblog
 * branch         main    > FETCH_HEAD
Already up to date
```

En general todo va a estar actualizado, simplemente es una buena practica. 


Homologar esta vaina ...

~~~~
BRUJA!!!! ya habia pasado antes git pull <> git pull origin main presento inconveniente

Se va a dejar solo con git pull para experimentar. a mi no me aparecio el --set-upstream-
~~~~

```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```

**¿Ahora como envio el cambio?** Antes de hacer el cambio, se deberia hacer nuevamente git pull origin main. Por que en lo que hice el commit, depronto cambiaron cosas. Simplemente para no tener conflictos.

se hace el git pull sencillo y aparece el error

```
(base) MBPdeDiego:pro-git-github mac$ git pull origin main
Enter passphrase for key '/Users/mac/.ssh/id_rsa':
Desde github.com:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
ayuda: Hacer un pull sin especificar c'omo reconciliar las ramas es poco
ayuda: recomendable. Puedes eliminar este mensaje usando uno de los
ayuda: siguientes comandos antes de tu siguiente pull:
ayuda:
ayuda:   git config pull.rebase false  # hacer merge (estrategia por defecto)
ayuda:   git config pull.rebase true   # aplicar rebase
ayuda:   git config pull.ff only       # aplicar solo fast-forward
ayuda:
ayuda: Puedes reemplazar "git config" con "git config --global" para aplicar
ayuda: la preferencia en todos los repositorios. Puedes tambi'en pasar --rebase,
ayuda: --no-rebase, o --ff-only en el comando para sobrescribir la configuraci'on
ayuda: por defecto en cada invocaci'on.
ayuda:
Ya est'a actualizado.
```

Se revisa en en repositorio remoto y se puede visualizar el cambio realizado en el archivo blogpost.html

```
<title>Bievenido al blog 2.0</title>
```

En history se puede corroborar quienes han hecho cambios, antes el cambio lo hacia DiegoAll (diego58229@hotmail.com) por que asi estaba configurado el usuario. El cambio **Cambie el titulo del blogpost** se realizó desde DiegoAll (diego58229@hotmail.com) utilizando Github por ende aparece **Verified**, y el cambio "Una version de el blogpost (ancestro)" tambien aparece a pesar que fue realizo de forma local.

**Hipotesis:** Quizás fue firmado el commit por el tema de haber sido realizado desde Github internamente.

Es como si ambos usuarios fueran el mismo, solo que uno trabaja en el repositorio remoto y el otro trabaja desde el entorno local.
En el ejercicio del curso ambos usuarios tienen el mismo email, es decir son la misma persona. En mi ejercicio genere una llave para otro dispositivo creada a partir de otro correo, finalmente dposadallano@hotmail.com hizó el cambio desde el equipo ancestro.
Ahora se puede ver toda la historia del archivo, se puede ver todo, se tiene conectado git con Github, ya se tiene funcionando SSH, la vida es perfecta.

**Hallazgo:**

No se tiene cuenta en Github con dposadallano@hotmail.com pero aparece como author del cambio para el label, es mapeada mi cuenta diegoall que es la que configuro la llave.

<img src="/assets/git_history_verified_other_device.jpeg" align="center" />
 
**Conclusión** 

Las llaves son para autenticar y hacer una conexión de doble via. Se recomienda generar llave por dispositivo (freddier)
Siempre van ligadas a una cuenta de usuario, este es el que aparece en el remoto.
El parametro user.email puede ser modificado facilmente de forma local.
En resumen importa es la cuenta del usuario y la llave que sea agregada.

**Riesgo**

- Se podria generar unas llaves y añadirlas a la cuenta de otra persona (Obviamente teniendo acceso a la misma), y quizas sustraer o modificar los repos. Cabe aclarar que al telefono movil llega una solicitud para aprobar dicha autenticación entonces este vector es poco probable.

- repojacking (poco probable)  [Big de Github podria permitir Suplantar repositorios](https://unaaldia.hispasec.com/2022/11/bug-github-podria-permitir-suplantar-repositorios.html)

- Chainjacking  [Chainjacking](https://github.com/checkmarx/chainjacking)


Se prueba nuevamente con otro commit desde Github y esta vez no se ejecuta git pull sino git pull origin main y ya no aparece el warning.

```
(base) MBPdeDiego:pro-git-github mac$ git pull origin main
Enter passphrase for key '/Users/mac/.ssh/id_rsa':
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (4/4), done.
Desempaquetando objetos: 100% (4/4), 914 bytes | 182.00 KiB/s, listo.
remote: Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
Desde github.com:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
   7e1d3df..13b0c0b  main       -> origin/main
Actualizando 7e1d3df..13b0c0b
Fast-forward
 src/blogpost.html | 1 +
 1 file changed, 1 insertion(+)
```

Se replica el escenario, incialmente se utilizó git pull, se hizó un cambio bienvenido al blogpost 2.0.1, git add, git commit.
Por buena practica, se vuelve a hacer git pull origin main y se reproduce el warning ... sugiere git config pull.rebase false

Duda

1. Aparece por que ya tengo actualizada la rama?

2.  Por que inicie haciendo git pull y al final corrobore con git pull origin main


Se vuelve a replicar el escenario, incialmente se utilizó git pull origin main, se hizó un cambio bienvenido al blogpost 2.0.2, git add, git commit. Por buena practica, se vuelve a hacer git pull origin main y se reproduce el warning ... sugiere git config pull.rebase false


Por ahora se concluye que al reproducir el escenario se replica el warning, pudiera ser por:

1. Porque se hace git pull origin main despues del git push origin main y no tiene sentido antes es una buena práctica.

2. Al parecer debe ser configurado un parametro en gitconfig  puede ser: 
  - git config pull.rebase false
  - git config pull.rebase true
  - git config pull.ff only

Se revisan parámetros conocidos en gitconfig local y global y no estan seteados. Se probará luego.

Se pullea desde el macbookpro y funciona correctamente.
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git pull origin main
From github.diegoall:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
Updating 27ede0b..54185c8
Fast-forward
 src/blogpost.html | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

Se vuelve a pullear a modo de exploración y funciona correctamente:

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git pull origin main
From github.diegoall:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
Already up to date.
```

Recordar git pull <>  git pull origin/main <>  git pull origin main  a veces dicen que son equivalentes ...

~~~~~
Remember, a pull is a fetch and a merge.

git pull origin master fetches commits from the master branch of the origin remote (into the local origin/master branch), and then it merges origin/master into the branch you currently have checked out.

git pull only works if the branch you have checked out is tracking an upstream branch. For example, if the branch you have checked out tracks origin/master, git pull is equivalent to git pull origin master
~~~~~


Cambiar o remover phassphrase from ssh key

https://www.simplified.guide/ssh/set-remove-passphrase







## 23. Tags y versiones en Git y GitHub

En los proyectos de código abierto, tienen como version 0.1, 1.5, 2.4 versiones especificas, releases? hasta acá llegó el proyecto esto es lo que se va enviar. Para esto se debe revisar la historia del proyecto. 

Se puede utilizar el siguiente comando **git log --all** para ver todo lo que se ha hecho historicamente, porque en ocaciones no muestra todo dependiendo de que branches han ocurrido. 

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log | wc -l
     148
CO0C02GD0T7MD6M:pro-git-github dposada$ git log --all | wc -l
     148
```
Otro escenario de un repo de mayor tamaño.
```
CO0C02GD0T7MD6M:fury_charts-monsec dposada$ git log | wc -l   
    1780
CO0C02GD0T7MD6M:fury_charts-monsec dposada$ git log --all | wc -l   
    1997
```

Resulta que hay una opción gráfica:

$ git log --all --graph 

```
* commit 82ae293d9a011e0b76433a98ea9e02160281d823
| Author: DiegoAll <dposadallano@gmail.com>
| Date:   Thu Dec 29 00:35:00 2022 -0500
| 
|     Volvi a una tipografia menos controversial
|   
*   commit d523138aa92e1bdda16293dd6db4f25dca624ea2
|\  Merge: e3ef15b 0f7e06a
| | Author: DiegoAll <dposadallano@gmail.com>
| | Date:   Thu Dec 29 00:13:53 2022 -0500
| | 
| |     Merge branch 'cabecera'
| | 
| * commit 0f7e06a6707d16b76013316e537f61554e13cf9f
| | Author: DiegoAll <dposadallano@gmail.com>
| | Date:   Wed Dec 28 01:37:47 2022 -0500
| | 
| |     Finalizada la cabecera con diseno azul
| | 
| * commit f07a006b3d47445a4de140a7540303deccaa30a8
| | Author: DiegoAll <dposadallano@gmail.com>
| | Date:   Tue Dec 27 00:54:09 2022 -0500
| | 
| |     Estructura inicial de la cabecera
| | 
* | commit e3ef15b841319df3f7cf26f75523b98ac3f13cc2
|/  Author: DiegoAll <dposadallano@gmail.com>
|   Date:   Wed Dec 28 23:21:09 2022 -0500
|   
|       Agregado el contenido adicional del blog y una mejor tipografia
| 
```
Empieza a mostrar unas rayitas de como han funcionado las ramas, se ve de una manera mas o menos visual.


$ git log --all --graph --decorate --oneline

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git log --all --graph --decorate --oneline
* 7e1d3df Una version de el blogpost (ancestro)
* 27ede0b Cambie el titulo del blogpost
*   99b5a9e Solucione el conflicto de las ramas al fusionar
|\  
| * 64aa64e (cabecera) Modifique la cabecera y el color del texto
* | fd7397b Agregue suscripcion, cambie la cabecera maestra y puse todo azul
|/  
* 82ae293 Volvi a una tipografia menos controversial
*   d523138 Merge branch 'cabecera'
|\  
| * 0f7e06a Finalizada la cabecera con diseno azul
| * f07a006 Estructura inicial de la cabecera
:...skipping...
```

Con este va a mostrar todo un poco mas comprimido y se ve todo el historico de cambios. Como el comando es tan largo se le va a crear un aliases.

$ alias ramas="git log --all --graph --decorate --oneline"

$ ramas

```
CO0C02GD0T7MD6M:pro-git-github dposada$ ramas
|\  
| * 64aa64e (cabecera) Modifique la cabecera y el color del texto
* | fd7397b Agregue suscripcion, cambie la cabecera maestra y puse todo azul
|/  
* 82ae293 Volvi a una tipografia menos controversial
*   d523138 Merge branch 'cabecera'
|\  
| * 0f7e06a Finalizada la cabecera con diseno azul
| * f07a006 Estructura inicial de la cabecera
* | e3ef15b Agregado el contenido adicional del blog y una mejor tipografia
|/  
```
Ahora que se tiene esto claro, seria interesante crear un tag, justamente acé en el commit **\* 689f66d Reemplazo de una version por otra de la historia**

Aca se tiene la version mas reciente de la historia, es como la version 0.1 del proyecto, entonces se va a crear un tag ahi. La forma en que se crea un tag es la siguiente: Primero se copia el hash: **689f66d**  Se puede colocar cualquier nombre, la convención mas normal es colocar **v0.1** , similar a un commit se le debe agregar un mensaje con el parámetro -m, el tag está en el hash. 

$ git tag -a v0.1 -m "Resultado version mas reciente de la historia" 689f66d

Aparentemente no pasa nada, ahora se va a ver cuales son los tags que se tienen. Con git tag va a mostrar la lista de todos los tags.

$ git tag

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git tag
v0.1
```
Pero como git es especial y es de codigo abierto donde muchas personas le han metido mano, la forma de saber a que hash o a que commit esta conectado un tag es con el comando:

$ git show-ref --tags

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git show-ref --tags
26e385f9fd8eb4fa7282b82a86a9475358fa616f refs/tags/v0.1
```
Y al hacerlo va a mostrar que se tienen un tag llamado v0.1 que está asignado al commit referenciado con el hash.

Revisando los hashes se nota que son distintos:

- 26e385f9fd8eb4fa7282b82a86a9475358fa616f (Con el cual esta siendo referenciado)
- 689f66d (utilizado para crear el tag)

Porque esta es la referencia al momento en que fue el tag creado **(26e385f9fd8eb4fa7282b82a86a9475358fa616f)** , 

$ git status

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch main
Your branch is up to date with 'origin/main'.
```
Aparentemente no hay nada que enviar porque los tags no son cambios. Pero si que hay algo que enviar, por que no importa que en este momento se tenga un tag, la idea es que los tags los pueda ver alguien. Los tags son utiles en Github en el sitio web, porque es la forma en que usuarios de código abierto, u otras personas pueden ver que version ocurrió. Son rara vez utiles dentro del prpoyecto excepto si se quiere excepto si se quiere dejar un registro aqui fue donde quede, simplemente es mas como referencia interna. Entonces lo interesante es mandarlo a internet.

Recordar que siempre se debe hacer **git pull origin main** antes de hacer cualquier cambio, para tener los fuentes del remoto actualizados. Actualiza e indica que todo está bien. Y ahora se va a enviar el tag a Github con el siguiente comando, significa que se va a empujar a Github el tag que fue creado. 

$ git push origin --tags

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin --tags
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 186 bytes | 186.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To github.diegoall:DiegoAll/pro-git-github.git
 * [new tag]         v0.1 -> v0.1
```
Se visualiza en Github y se ve que se tiene algo nuevo:

<img src="/assets/tag_v0.1_1.jpeg" align="center" />

Y si se revisa el código, ahi esta la primera version del blogpost e historia.txt 

<img src="/assets/tag_v0.1_2.jpeg" align="center" />

**¿Pero que pasa si se crea un tag que no nos gusta?**

Se va a crear un tag errado. Se toma un tag cualquiera 82ae293, y se va a crear un tag random llamado dormido, 

$ git tag -a dormido -m "Pohas dfdff sdfdsf" 82ae293

Ahora lo voy a mandar al remoto, traigo lo del remoto nuevamente, no hay nada pero es una buena practica **git pull origin main** y luego se envian:

$ git push origin --tags

Se revisa en Github y en efecto se tiene el tag dormido, y el código asociado a ese hash con el que se creo el tag. El hecho es que se cometio un error, ¿Como se borra el tag dormido?
Se podría borrar desde la interfaz bonida de Github, pero tambien se puede borrar de forma local, es muy sencillo. Se revisan los tags que existen con **git tag** y una vez se tiene claro que este tag existe y lo tengo que matar se utiliza el siguiente comando:

$ git tag -d dormido 

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git tag -d dormido
Deleted tag 'dormido' (was 3276491)
```
Y fue completamente borrado el tag dormido. Al darle **git status** no han cambiado los archivos entonces no hay nada que hacer. Nuevamente se hace **git pull origin main** para traer los cambios ... otra vez se vuelve a hacer push de los tags **git push origin --tags** y al volver al repositorio y recargar aun existe el tag dormido en el remoto: 

```
dormido
Toggle commit message
 18 minutes ago  82ae293  zip  tar.gz
v0.1
Toggle commit message
 20 hours ago  689f66d  zip  tar.gz
```
Ahora en el repositorio local fue borrado el cambio

$ git tag 

La razón por la que no se borra de manera automatica en Github, es por que los tags se puedne utilizar como **Releases** que es la forma como se taggea se categoriza que algo está listo. Entonces aunque se borre internamente (local) tiende a quedar acá arriba (remoto).

Entonces debe borrarse de una manera especial:

$ git push origin :refs/tags/dormido

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin :refs/tags/dormido
To github.diegoall:DiegoAll/pro-git-github.git
 - [deleted]         dormido
```

Esta es una sintaxis interna que borra esa referencia en el origen conectado con nuestra referencia de cuando se borro el tag.

```
v0.1
Toggle commit message
 20 hours ago  689f66d  zip  tar.gz
```

BRUJA

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git tag -d dormido
Deleted tag 'dormido' (was 3276491)
CO0C02GD0T7MD6M:pro-git-github dposada$ git tag
v0.1
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin --tags
Everything up-to-date
CO0C02GD0T7MD6M:pro-git-github dposada$ git tag
dormido
v0.1
```
En el curso funciona.

La caceria de la bruja es la siguiente primero se crea el tag y se envia. Luego se pullea de buena practica para actualizar, git push origin --tags  ... Es como si el pull funcionara como push ...

Se recomienda borrar del remoto y pullear el cambio para eliminarlo.


otro comando
git push origin --delete dormido

solucion

1. borrar local
2. borrar remoto
3. pull and push

```
* 2a9f6c9 Commit al master del blogpost en su version mas reciente
* 689f66d (tag: v0.1) Reemplazo de una version por otra de la historia
* cc19055 Cambio de maestria
* 8ebe2c6 Cambio de vida
```
Como el tag dormido fue borrado no aparece con el comando "ramas"


git config --global alias.NOMBRE_ALIAS 'COMANDO_DEL_ALIAS'


## 24. Manejo de ramas en GitHub

En Github siempre se va a ver la rama principal (master o main) donde esta la ultima version, pero que pasa con las ramas de desarrollo? Normalmente hay una version estable del software y luego se empiezan a crear cambios y no se está seguro si se desean agregar o no a la rama principal. O tambien puede que hayan multiples programadores trabajando en ramas distintas.
Como se esta haciendo un blog se va a hacer el desarrollo de la cabecera en una rama, y el desarrollo del footer en otra rama. Ya se uso la rama cabecera pero para efectos practicos, la rama de cabecera va a ser llamada header, de tal manera que la cabacera que se maneja local quede como una historia. Y en header es donde se manejan los cambios de la parte de arriba, y en footer los cambios de la parte de abajo, como si fueran trabajadores distintos. Primero se va a agregar la historia de las ramas a Github, y luego se van a crear estas 2 ramas nunevas, 

Recordatorio comandos importantes de ramas

- git checkout cabecera
- git branch 
- ramas (muestra la historia de esas ramas)

Un nuevo comando importante para manejar ramas es **git show-branch** que muestra cuales ramas existen y cual ha sido su historia.

$ git shown-branch

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git show-branch
! [cabecera] Modifique la cabecera y el color del texto
 * [main] Novedad version de el blogpost (ancestro)
--
 * [main] Novedad version de el blogpost (ancestro)
 * [main^] Otra version de el blogpost (ancestro)
 * [main~2] Parrafo de prueba (firma desde Github y warning al realizar git pull)
 * [main~3] Una version de el blogpost (ancestro)
 * [main~4] Cambie el titulo del blogpost
+* [cabecera] Modifique la cabecera y el color del texto
```

Tambien esta el comando **git show-branch --all** que entrega un poco mas de información.

$ git show-branch --all

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git show-branch --all
! [cabecera] Modifique la cabecera y el color del texto
 * [main] Novedad version de el blogpost (ancestro)
  ! [origin/HEAD] Novedad version de el blogpost (ancestro)
   ! [origin/main] Novedad version de el blogpost (ancestro)
----
 *++ [main] Novedad version de el blogpost (ancestro)
 *++ [main^] Otra version de el blogpost (ancestro)
 *++ [main~2] Parrafo de prueba (firma desde Github y warning al realizar git pull)
 *++ [main~3] Una version de el blogpost (ancestro)
 *++ [main~4] Cambie el titulo del blogpost
 --- [main~5] Solucione el conflicto de las ramas al fusionar
+*++ [cabecera] Modifique la cabecera y el color del texto
```

Tambien esta el comando gitk , lo que hace es abrir en un software la historia del repo de una forma ultravisual.
Muestra los cambios, las ramas incluso los tags. 

<img src="/assets/gitk.jpeg" align="center" />

Es mucho mas amigable, debe verse mas como una ayuda. Se presentaron primero los comandos porque como desarrollador permite mayor rapidez para trabajar y es mejor.

$ git branch 

Aparecen 2 ramas main y cabecera, aun no ha sido enviada cabecera. 

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch
  cabecera
* main
```
Se va a enviar la rama con el comando:

$ git push origin cabecera

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git pull origin main ; git push origin cabecera
From github.diegoall:DiegoAll/pro-git-github
 * branch            main       -> FETCH_HEAD
Already up to date.
CO0C02GD0T7MD6M:pro-git-github dposada$ git checkout cabecera
M       notes/COMMANDS.md
M       notes/EXTRAS.md
M       notes/NOTES.md
Switched to branch 'cabecera'
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin cabecera
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'cabecera' on GitHub by visiting:
remote:      https://github.com/DiegoAll/pro-git-github/pull/new/cabecera
remote: 
To github.diegoall:DiegoAll/pro-git-github.git
 * [new branch]      cabecera -> cabecera
```

Se visualiza en Github y en efecto aparece la rama cabecera. 2023 se genera un enlace (Pull Request) para fusionar esta rama con main. Tambien aparece la funcionalidad para proteger la rama.

```
Your main branch isn't protected
Protect this branch from force pushing or deletion, or require status checks before merging. Learn more
```
<img src="/assets/push_cabecera.jpeg" align="center" />

Y al darle click a la rama cabecera se ve la historia de cabecera, 

<img src="/assets/cabecera_on_github.jpeg" align="center" />

Se pueden tener ramas que nunca son enviadas al repositorio remoto en Github, se pueden tener ramas que siempre se estan enviando, lo importante es aprender a manejar este proceso de ramas. Ahora que ya se tiene la rama cabecera enviada, se pueden crear un par de ramas mas. Crear las ramas de trabajo header y footer, y olvidemos la rama de cabecera que va a quedar como una rama de referencia.

Se retorna al main con **git checkout main**

**¿Por que se hace desde acá?**

Es importante crear la rama desde la version mas reciente.

$ git branch header  

$ git branch footer

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch header
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch footer
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch
  cabecera
  footer
  header
* main
```

Se van a enviar a internet por si alguien copia de internet estos datos.

$ git push origin header footer

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin header
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'header' on GitHub by visiting:
remote:      https://github.com/DiegoAll/pro-git-github/pull/new/header
remote: 
To github.diegoall:DiegoAll/pro-git-github.git
 * [new branch]      header -> header
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin footer
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'footer' on GitHub by visiting:
remote:      https://github.com/DiegoAll/pro-git-github/pull/new/footer
remote: 
To github.diegoall:DiegoAll/pro-git-github.git
 * [new branch]      footer -> footer
``` 

Ahora lo interesante es ver, **¿Como va a ser el flujo de trabajo?**

Imaginar que hay otro programador completamente distinto, que se va a encargar de hacer el footer, y yo me voy a encargar de haxcer el header. Que pasa cuando ese programador quiere fusionar ese trabajo de footer con mi trabajo de header? Y cuando los dos ya estemos listos para enviarlo a master, esto es lo que va a ser muy interesante y esto esto es basicamente un flujo de trabajo en Git.

En efecto y estan las 4 ramas creadas en el proyecto remoto.


<img src="/assets/footer_header_branch.jpeg" align="center" />


## 25. Configurar múltiples colaboradores en un repositorio de GitHub

Se tiene un nuevo programador adicional con cuenta en Github  **https://github.com/diego-all**. esta persona tiene un e-maile que es dposadallano@hotmail.com. Entonces es importante configurar eso en el entorno local, se puede corroborar que ya fue previamente configurado juntop con su user.name.

```
(base) MBPdeDiego:prueba-dposada-hotmail mac$ git config -l
credential.helper=osxkeychain
user.email=dposadallano@hotmail.com
user.name=Diego All
```

Se crea una carpeta para arrancar su repositorio, hay una diferencia en este escenario, este nuevo usuario no requiere hacer un **git init** solamente requiere traer el repositorio. Se visita el repositorio el cual se quiere clonar y se extrae su URL.

**Cabe aclarar que una cosa es que este nuevo usuario pueda clonar y otra es que pueda enviar.**

$ git clone git@github-diegoall:DiegoAll/pro-git-github.git

```
(base) MBPdeDiego:prueba-dposada-hotmail mac$ git clone git@github.diego-all:DiegoAll/pro-git-github.git
Clonando en 'pro-git-github'...
Warning: Permanently added the ECDSA host key for IP address '140.82.113.3' to the list of known hosts.
ERROR: Repository not found.
fatal: No se pudo leer del repositorio remoto.

Por favor asegúrate de que tengas los permisos de acceso correctos
y que el repositorio exista.
```

Se procede a enviar una invitación, para que el usuario diego-all pueda ser colaborador en el repositorio

<img src="/assets/colaborator_invitation.jpeg" align="center" />

Luego de que se acepta la invitación, se clona el repositorio nuevamente y se logra el cometido.

$ git clone git@github.diego-all:DiegoAll/pro-git-github.git

```
(base) MBPdeDiego:prueba-dposada-hotmail mac$ git clone git@github.diego-all:DiegoAll/pro-git-github.git

Clonando en 'pro-git-github'...
remote: Enumerating objects: 112, done.
remote: Counting objects: 100% (112/112), done.
remote: Compressing objects: 100% (62/62), done.
remote: Total 112 (delta 45), reused 99 (delta 39), pack-reused 0
Recibiendo objetos: 100% (112/112), 835.08 KiB | 1.72 MiB/s, listo.
Resolviendo deltas: 100% (45/45), listo.
```

**Ahora continuando con el curso**

Si el repositorio fuera público no pediria credenciales. Al ser público simplemente estaba ahi, se puede descargar simplemente.
La carpeta clonada se llama exactamente igual a como se llama en Github, realmente se le puede cambiar el nombre solamente que este es el nombre por defecto. 

Ahora el nuevo programador viene al archivo historia.txt, y va a añadir un nuevo aporte. 

y agrega la siguiente linea:

```
Diego Respaldo tiene 32.5 años y nacio en internet.
```

Como el archivo ya esta trackeado (En teoria es decir ya fue commiteado) se puede utilizar el siguiente comando.

$ git commit -am "Primer commit del programador nuevo"

```
(base) MBPdeDiego:pro-git-github mac$ git commit -am "Primer commit del programador nuevo"
[main a882b40] Primer commit del programador nuevo
 1 file changed, 2 insertions(+)
```

Se trae lo quie está en internet.

$ git pull origin main  (Buena práctica)


Como ejercicio interesante, **¿Sera que trajo solamente la rama main o todas las ramas?**

$ git branch 

```
(base) MBPdeDiego:pro-git-github mac$ git branch
* main
```

Esta por ahora la rama main.

Con **git log** se puede ver toda la historia. y si se visualiza **git log --graph** se va a ver toda la historia incluyendo el primer commit del desarrollador nuevo que apunta a  (HEAD -> main) pero no está en (origin/main, origin/header, origin/footer, origin/HEAD) que son las ramas que están en este momento en internet (Github). Y se pueden ver todos los cambios que han realizados los usuarios, por que Git es una base de datos historica de todo lo que ha pasado en el proyecto, 

```
(base) MBPdeDiego:pro-git-github mac$ git log
commit a882b4059f2dba1bb60a777568b344eecd327f68 (HEAD -> main)
Author: Diego All <dposadallano@hotmail.com>
Date:   Fri Jan 6 23:22:19 2023 -0500

    Primer commit del programador nuevo

commit 5c478dce4be1a279f042ee976ac4304879087777 (origin/main, origin/header, origin/footer, origin/HEAD)
Author: Diego All <dposadallano@hotmail.com>
Date:   Wed Jan 4 23:29:28 2023 -0500

    Novedad version de el blogpost (ancestro)
```
Ahora se va a enviar al repositorio remoto el cambio realizado por el nuevo programador. **git push origin main**

```
(base) MBPdeDiego:pro-git-github mac$ git push origin main
Enumerando objetos: 7, listo.
Contando objetos: 100% (7/7), listo.
Compresi'on delta usando hasta 8 hilos
Comprimiendo objetos: 100% (4/4), listo.
Escribiendo objetos: 100% (4/4), 455 bytes | 455.00 KiB/s, listo.
Total 4 (delta 2), reusados 0 (delta 0), pack-reusados 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.diego-all:DiegoAll/pro-git-github.git
   5c478dc..a882b40  main -> main
```

A mi me funciona por que ya habia previamente agregado como colaborador al nuevo programador en el repositorio, en el curso hay que hacer este proceso. Tener en cuenta entrar al repositorio e ir a los settings del mismo y no a los settings del usuario.

Si estas en un ambiente corporativo se sugiere crear la cuenta con el correo corporativo (interno).

~~~~~
Si no aparece el colaborador al momento de agregarlo es por que no tiene una cuenta publica verificada. 
Para hacer eso se debe ir al perfil y crear un email publico, y para eso hay que cambiar la configuracion e indicar que se desea ser visible (Not visible in emails) y todo eso. Como el email publico no es visible, no se puede. En vez de darle el email se pretende realizar con el nombre de usuario diego-all porque se desea que el email se mantenga privado. 
~~~~~

**Configuración diego-all**

<img src="/assets/github_email_diego-all.jpeg" align="center" />


**Configuracion corporativa**

<img src="/assets/github_email_corporativo.jpeg" align="center" />

Se envia la invitación, se acepta y ahora el nuevo programador es colaborador del repositorio y puede empezar a colaborar con el equipo de trabajo.

**Nota:** Si quiere ahondar en el tema revisar access level para los repositorios.

Se revisa en el sistema de diego-all y se valida que por ahora no se tiene acceso a ese repositorio, todo sigue normal  pero si se tiene acceso de push al repositorio de pro-git-github.

<img src="/assets/accepted_invitation_github_diego-all.jpeg" align="center" />

Se logro realizar push a un repositorio remoto con un usuario diferente.

~~~~~
Tema del GAP con las cuentas
Fraude prueba agregar llave ssh a mi cuenta de github. Otro pasquin hace el codigo.
Debe tenerse acceso a la cuenta de Github y agregar una llave ssh a una cuenta para poder realizar cambios en un repositorio.
Considerar los repositorios privados requiere que se agregue como colaborador un nuevo usuario.
Si el repo es publico puede hacer pull pero no push sin estar autorizado y nada mas.
Si desea ahondar mas informacion revisar access level en Github.
Siempre mapea el usuario de Github
Si no tiene usuario de Github mapea el de la configuiracion local o las variables de entorno.
Dado el caso que haga un commit previo sin tener cuenta y despues la cree, toma el username de la cuenta.
~~~~~

[Convertir una organización en un usuario](https://docs.github.com/es/organizations/managing-organization-settings/converting-an-organization-into-a-user)

~~~~~
Convertir una organización en un usuario
No es posible convertir una organización en una cuenta personal, pero puedes crear una nueva cuenta personal y transferirle los repositorios de la organización.
~~~~~

**Flujos de trabajo profesionales**


## 26. Flujo de trabajo profesional: Haciendo merge de ramas de desarrollo a master


DiegoAll se encarga del header y diego-all se encarga del footer, en mi header quiero agregar un logo, se va a crear una nueva carpeta que se llame imagenes y se guarda la imagen del logo con extension *.png.
El problema es que una imagen es un archivo binario no es un archivo de texto plano, las mejores practicas dicen que los archivos binarios no se deberian agregar a repositorios, deberian estar a aparte deberian estar ignorados, en este caso por temas de agilidad sera agregado.

Ahora se hara un cambio de rama para la rama header. En master solo se envia lo que se tiene certeza que esta listo para producción, es una buena practica de trabajo.

$ git checkout header

$ git add imagenes/logo.png

$ git commit -am "Logo del header"

Se revisa en Github y aun no se visualiza la carpeta de imagenes. Se procede a  traer la ultima version de la rama header.

$ git pull origin header

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git pull origin header
From github.diegoall:DiegoAll/pro-git-github
 * branch            header     -> FETCH_HEAD
Already up to date.
```
$ git log

Se puede ver el apuntador que ya esta hacia la rama.

```
commit 5d32301673fe3d3910d6549f56daa5c96fffa6e8 (HEAD -> header)
Author: DiegoAll <dposadallano@gmail.com>
Date:   Sat Jan 7 01:04:09 2023 -0500

    Logo del header
```
Ahora se envia la imagen a Github:
```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin header
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 6 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (8/8), 89.41 KiB | 7.45 MiB/s, done.
Total 8 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.diegoall:DiegoAll/pro-git-github.git
   5c478dc..5d32301  header -> header
```

Se valida en el repositorio y ya aparece la carpeta de imagenes y sale algo nuevo **Compare & pull request** se vera a profundidad mas adelante.


#### CRISIS DE DATA PERDIDA (git checkout header - git commit -am "Logo del header")

~~~~~
INCONVENIENTE 1:

Hubo un error con las ramas al hacer **git commit -am "Logo del header" se sincronizaron con la rama remota header archivos que estaban almacenados en local tenian modificaciones pero no se deseaba subir al remoto. Se recomienda utilizar **git add <fileName>**
ya que estos archivos ya fueron previamente commiteados, el **git commit -am "Logo del header" los lleva a staging, los commitea y posteriormente al pushear son enviados al remoto a la rama header pero no quedan en main por que aun no se ha hecho en push.
~~~~~

**Se va a eliminar la rama header de forma local:**

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch -d header
error: The branch 'header' is not fully merged.
If you are sure you want to delete it, run 'git branch -D header'.

CO0C02GD0T7MD6M:pro-git-github dposada$ git branch -D header
Deleted branch header (was 5d32301).

CO0C02GD0T7MD6M:pro-git-github dposada$ git branch
  cabecera
  footer
* main
```
[-d] Eliminará la branch únicamente si esta ha sido empujada y fusionada con la branch remota. 

[-D] Si desea forzar la eliminación de una branch, incluso si aún esta no ha sido empujada o fusionada aún


**Se va a eliminar la rama header de forma remota:**

$ git push origin --delete header

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git push origin --delete header
To github.diegoall:DiegoAll/pro-git-github.git
 - [deleted]         header
```

Se corrobora que haya sido borrada en el repositorio local:

$ git branch -a

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch -a
  cabecera
  footer
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/cabecera
  remotes/origin/footer
  remotes/origin/main
```

Se corrobora que haya sido borrada en el repositorio remoto:


remote_header_branch_deleted.jpeg  pendiente ajustar foto


~~~~~~
INCONVENIENTE 2: Como estos cambios nunca habian sido commiteados en la rama main (Solo estaban de forma local), al eliminar la rama header (Implica hacer un checkout a main para poder borrar otra rama) **fueron perdidos los cambios que nunca habian sido commiteados** en la rama main y el **git commit -am "mensaje"** los habia llevado a la rama header eliminada. La unica forma de recuperar esta información es recreando esta rama eliminada o restableciendola.
~~~~~

Hay un método, al eliminar esta rama con **git branch -D header** la salida del comando entrega un hash SHA.

CO0C02GD0T7MD6M:pro-git-github dposada$ git branch -D header
Deleted branch header (was 5d32301).

Se intenta RECREAR esa rama, es decir realizar el cambio a esa rama y se le pone el SHA1. Si no se tiene el hash se puede utilizar el comando git reflog.

a882b40 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: checkout: moving from header to main
5d32301 HEAD@{1}: checkout: moving from main to header
a882b40 (HEAD -> main, origin/main, origin/HEAD) HEAD@{2}: checkout: moving from header to main
5d32301 HEAD@{3}: commit: Logo del header

Se utiliza el siguiente comando:

$ git branch header 5d32301  (Recrear la rama header que fue eliminada.)

Ahora con **git branch** se puede ver que se recupero la rama header.

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git branch
  cabecera
  footer
  header
* main
```

#### SOLUCIONES A DATA PERDIDA

1. Restaturar rama
2. Recuperar información.
3. Deben recrearse las ramas ya que fueron creadas a partir de main antes de la perdida.
4. Se puede pushear /notes o convertir a Untracked files. (Se decide por dejarlos untracked mientras se finaliza todo en aras de probar la solución tambien, se tiene copia de las notas.)

Se realizan las correciones pertinentes y se procede a volver a main para borrar las ramas header y footer, y finalmente continuar... 

**Investigar como destrackear esto, ya que asi esten los cambios en main siempre que me pase de rama y vuelva voy a perder lo que tenga en main si no estoy constantemente haciendo commit.
La derecha es nunca haberle hecho commit, pero como ya se le hizo .... tener cuidado con los chekouts que borra la info asi sea del local.**

```
CO0C02GD0T7MD6M:pro-git-github dposada$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   notes/COMMANDS.md
        modified:   notes/EXTRAS.md
        modified:   notes/NEMONICS.md
        modified:   notes/NOTES.md
```

**Es con git restore**

Al parecer Github todo el tiempo esta trackeando los cambios en los archivos, asi no esten en stagging para ser commiteados.
Cuando se hacen cambios de rama se pierden los cambios locales que se habian hecho ya que los archivos estaban siendo trackeados por Git. 






## 27.




## 28.



## 29.




## 30.



## 31.



## 32.



## 33. 





PORTAFOLIO


https://assets.thepragmatic.xyz/#

https://assets.thepragmatic.xyz/resumeDiegoPosada.html  



thepragmatic.xyz@gmail.com

#### Generar llaves para thepragmatic.xyz  N/A

[Convertir una organización en un usuario](https://docs.github.com/es/organizations/managing-organization-settings/converting-an-organization-into-a-user)

~~~~~
Convertir una organización en un usuario
No es posible convertir una organización en una cuenta personal, pero puedes crear una nueva cuenta personal y transferirle los repositorios de la organización.
~~~~~











## 27.




## 28.



## 29.




## 30.



## 31.



## 32.



## 33. 





PORTAFOLIO


https://assets.thepragmatic.xyz/#

https://assets.thepragmatic.xyz/resumeDiegoPosada.html  



thepragmatic.xyz@gmail.com

#### Generar llaves para thepragmatic.xyz  N/A

[Convertir una organización en un usuario](https://docs.github.com/es/organizations/managing-organization-settings/converting-an-organization-into-a-user)

~~~~~
Convertir una organización en un usuario
No es posible convertir una organización en una cuenta personal, pero puedes crear una nueva cuenta personal y transferirle los repositorios de la organización.
~~~~~
