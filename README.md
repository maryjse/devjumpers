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