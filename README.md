# devjumpers
Ejercitacion final GIT-GITHUB, Arbusta.

Empiezo creando mi repositorio en Github y mediante Git lo clono para traerlo a mi maquina local, utilizando los siguientes comandos:
```bash
$ git clone https://github.com/maryjse/devjumpers.git
```
Luego, hago los cambios de mi README.md y hago el primer commit, utilizando los siguientes comandos:
```bash
$ cd devjumpers 
```
(Entro a mi carpeta main, donde se ubica el .git)
```bash
$ git status
```
(Para visualizar el cambio del primer texto que escribí)
```bash
$ git add .
$ git commit -m "Commit inicial"
$ git push 
```
(Acá hice mi primer push)

IGNORAR ARCHIVOS:

El comando .gitignore me permite clasificar los archivos o carpetas los cuales quiero ignorar en mi repositorio.
En el repositorio local creo un archivo .txt y una carpeta de la manera:
```bash
$ touch privado.txt
$ mkdir privada
```
Luego, para visualizar que se crearon correctamente veo la lista de mi carpeta:
```bash
$ ls
```
Para ignorar la carpeta y el archivo creé utilicé el archivo .gitignore, el cual lo creé con el comando:
```bash
$ touch .gitignore
```
Y dentro del archivo ingresé el nombre de los elementos a ignorar.
Luego, lo añadí e hice el push:
```bash
$ git add .
$ git commit -m "Ignorar Archivos"
$ git push
```

AÑADIR FICHERO 1.TXT:

Posicionandome en la rama main, utilicé el comando:
```bash
$ touch 1.txt
```

CREACIÓN DE RAMA v0.2:

Para crear la rama utilicé el comando:
```bash
$ git branch v0.2
```
Luego, en la rama main creé el archivo 2.txt de la manera, además vi si se había añadido la nueva rama correctamente:
```bash
$ touch 2.txt
$ git branch
```
Me posicioné en la rama v0.2 con:
```bash
$ git checkout v0.2
```
y añadí mi archivo txt a la misma, hice el commit y el push al repositorio remoto de la siguiente manera:
```bash
$ git add 2.txt
$ git commit -m "Creacion de fichero 2.txt en rama v0.2"
$ git push --set-upstream origin v0.2
```

MERGE DIRECTO:

Hice el merge de mi archivo 2.txt a la rama main, primero me posicioné en la rama main y después realicé el merge, de la siguiente manera:
```bash
$ git checkout main
$ git merge v0.2
```

MERGE CON CONFLICTO:

En la rama main agregué "Hola" al archivo 1.txt de la manera:
```bash
$ echo "Hola" > 1.txt
$ git add 1.txt
$ git commit -m "Agregando HOLA a 1.txt desde main"
```
Luego, me posicioné en la rama v0.2 y le agregué al archivo 1.txt "Adiós":
```bash
$ git checkout v0.2
$ echo "Adios" > 1.txt
$ git add 1.txt
$ git commit -m "Agregando ADIOS a 1.txt desde v0.2"
```
Volví a la rama main e intenté realizar el merge, pero me encuentro con un conflicto.
```bash
$ git checkout main
$ git merge v0.2
```
Git me arrojó este mensaje:
```bash
Auto-merging 1.txt
CONFLICT (add/add): Merge conflict in 1.txt
Automatic merge failed; fix conflicts and then commit the result.
```

LISTADO DE RAMAS:

La funcion --merged me muestra las ramas que estan ya fusionadas, y --no-merged las que no estan, por lo tanto no puedo eliminarlas. En mi caso tengo la rama main fusionada pero v0.2 no lo esta, y al aplicar el comando me sale de esta manera:
```bash
Usuario@MACHINE-K MINGW64 ~/Desktop/Github/devjumpers (main|MERGING)
$ git branch --merged
* main
```
```bash
Usuario@MACHINE-K MINGW64 ~/Desktop/Github/devjumpers (main|MERGING)
$ git branch --no-merged
  v0.2
```
ARRGLAR CONFLICTO:

Arreglo el conflicto manualmente, ingresando a mi archivo 1.txt y modificando los cambios que quiera arreglar, en mi caso me sale de esta manera:

<<<<<<< HEAD
Hola
=======
Adios
>>>>>>> v0.2

Hago los cambios pertinentes en el archivo 1.txt de mi rama main:
Hola
Adios
Una vez solucionado, ya puedo agregar y realizar mi commit.

BORRAR RAMA:

Yo eliminé la rama de manera forzada, ya que la agregué a mi repositorio, al intentar hacerlo con:
```bash
$ git branch -d v0.2
```
Me salió este mensaje:
```bash
warning: not deleting branch 'v0.2' that is not yet merged to
         'refs/remotes/origin/v0.2', even though it is merged to HEAD.
error: The branch 'v0.2' is not fully merged.
If you are sure you want to delete it, run 'git branch -D v0.2'.
```
Así que la eliminé de la forma:
```bash
$ git branch -D v0.2
```
Y al hacer:
```bash
$ git branch
```
Sólo puedo visualizar la rama main.

LISTA DE CAMBIOS:

Con en comando:
```bash
$ git log --oneline --decorate --all --graph
```
Puedo visualizar todos los commits realizados de manera más detallados, los cuales son:
```bash
* 7d9f66c (HEAD -> main, origin/main, origin/HEAD) Rama v0.2 eliminada
*   5ac9f2f Conflicto Arreglado
|\
| * 7dd7918 Agregando ADIOS a 1.txt desde v0.2
* | a17f7a7 Agregando HOLA a 1.txt desde main
|/
* 2b41d24 (origin/v0.2) Creacion de fichero 2.txt en rama v0.2
* df0f59c Creacion de archivo 1.txt desde main
* 432b0f9 Ignorar Archivos
* 131404d Commit inicial
* cf52fa4 Initial commit
```