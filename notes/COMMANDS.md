# Commands

## Git

git grep [palabra]: busca esa
palabra en nuestros archivos
en la rama en la cual nos
encontremos.

git grep -n [palabra]:nos da la
línea específica en donde se
encuentra esa palabra.

git grep -c [palabra]: nos
muestra el número de veces
que se utiliza esa palabra en
nuestros distintos archivos.

git log -S “palabra”: busca
palabras usadas en commits.


terminal


ver diapositivas en ingles

sumar a tpgmtc linux fundamentals

cd .
./...
virgulilla
history
!32


Si por algún motivo te equivocaste en el nombre o email que configuraste al principio, lo puedes modificar de la siguiente manera:

git config --global --replace-all user.name “Aquí va tu nombre modificado”

O si lo deseas eliminar y añadir uno nuevo

git config --global --unset-all user.name :Elimina el nombre del usuario

git config --global --add user.name “Aquí va tu nombre”


Solo Haz los cambios que faltaban, luego los añades al staging area (sí, con git add) y usas git commit pero con los flags --amend y --no-edit para aplicar los nuevos cambios al último commit y dejando que el mensaje del commit sea el mismo de antes.


git commit --amend --no-edit  (Sin mensaje, toma el anterior, cambios de stagging son commiteados)





git switch -

Es super sencillo miguel, al hacer

git checkout tag - de un id . Es como visitar el pasado , para regresar al presente solo ejecutas el comando, la terminal te lo va a recomendar tambien
git switch - || comando recomendado por la terminal para regresar



También se agrega un paso adicional, al momento de crear un repositorio desde la línea de comandos. Como vemos en las imágenes ahora debemos hacer:

git branch -M main

Sabemos que git branch nos ayuda a crear una nueva rama dentro de nuestro repositorio y -M nos ayudará a mover todo el historial que tengamos (en caso de que los haya) en master a la nueva rama que estamos creando que se llama main




git fsck realiza una comprobación de integridad del sistema de archivos git e identifica cualquier objeto corrupto


git fsck


Tengamos en cuenta momentos en donde queremos hacer git add en todos los archivos menos en uno, no nos pondríamos a hacer git add y el nombre de cada archivo obviando el que no queremos eso no es nada eficiente, en cambio lo mejor es hacer git add . y después usar un git reset HEAD de ese archivo en particular y así podemos hacer commit en todos menos en ese, y nos ahorramos mucho tiempo


Hola compañeros.
Dejo este aporte por si alguien (como yo jaja) no le gusta escribir tanto.

$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
$ git config --global alias.ust ‘reset HEAD --’

se puede acortar los comando.

Ejemplo:
–Normal
$ git commit -m “Nuevo cambio al repo”
–Con alias
$ git ci -m “Nuevo cambio al repo”



comandos utiles al hacer un merge

Arranca una herramienta visual en consola que permite resolver conflictos.

git mergetool

Comando para abortar la fusion en progreso actual,en caso de no poder resolver los conflictos en ese momento. 
git merge --abort

Si hemos realizado un merge con una rama con la que no queriamos
git reset --merge HEAD


git checkout –b // creará una nueva rama y saltará a ella de forma inmediata

git branch --list // listará las ramas existentes

git branch --delete [nombreRama] // borrará la rama que se indique

git branch –D [nombreRama] // fuerza la eliminación de ramas que aún no han sido fusionadas

git branch –v // muestra el último commit de cada rama

git branch --merged // lista las ramas que se fusionaron con la rama actual

git branch --no-merged // lista las ramas que no se han fusionado con la rama actual

git merge --abort // anula el merge y devuelve todo a como estaba antes


todos los nuevos repositorios sean por default main y no estar haciendo git branch -M main 

git config --global init.defaultBranch main



## VSCode

¿No te funciona el comando code en tu terminal?

Abre Visual Studio Code
Presiona cmd + shift + p ó si estás en windows ctrl + shift + p
Busca una opción que diga lo siguiente: Shell Command: Install 'code' command in $PATH



git graph



Para borrar tags.. 

git push origin :refs/tags/dormido   seran iguales git push origin --delete beta


Para eliminarlo localmente:

git tag --delete nombreDeltag
Para eliminarlo del servidor:

git push --delete origin nombreDeltag

https://es.stackoverflow.com/questions/74187/c%C3%B3mo-eliminar-una-etiqueta-tag-en-git  (BRUJA)


git config --global alias.NOMBRE_ALIAS 'COMANDO_DEL_ALIAS'


