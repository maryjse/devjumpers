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