# Practica1Softca
Practica de Git / Github control de versiones

## CLONAR VUESTRO REPOSITORIO EN LOCAL

~~~
git clone git@github.com:cdelcastillomaussa/Practica1Softca.git
~~~

## README.md
Creamos en vuestro repositorio local
un documento **README.md**.

~~~
touch README.md 
~~~

## Commit inicial
Realizamos nuestro primer commit inicial 

~~~
git add .
git commit -m "commit inicial"
~~~



## Push inicial
Subimos los cambios al respositorio remoto
~~~
git push origin main
~~~

## Ignorar archivos

creamos un repositorio local un fichero llamado **privado.txt**

~~~
touch privado.txt
~~~

Creamos carpeta llamada **privada**

~~~
mkdir privada
~~~

Realizamos los cambios oportunos para que tanto el archivo como la carpeta sean ignorados por git.

~~~
echo "privado.txt" > .gitignore
echo "/privada" > .gitignore
git add .
git commit -m "añadimos fichero .gitignore"
~~~

## Añadir fichero 1.txt
Añadimos fichero al repositorio local

~~~
touch 1.txt
git add .
git commit -m "añadimos fichero 1.txt"
~~~

## Creacion del Tag v0.1

~~~
git tag v0.1
~~~

## Subimos el tag v0.1

~~~
git push --tag origin main
~~~

## Creamos una rama y nos movemos hacia ella llamada v0.2

~~~
git checkout -b v0.2
~~~

## Añadimos fichero 1.txt estando en la rama llamada v0.2

~~~
touch 2.txt
git add .
git commit -m "añadimos fichero 2.txt"
~~~

## Creamos rama remota v0.2
Subimos los cambios al repositorio remoto en Github

~~~
git push origin v0.2
~~~

## Merge directo (FUSION)
Primero que todo nos posicionamos en la rama **main**

~~~
git checkout main

git merge v0.2 "fusion v0.2 sin conflictos"
~~~

## Merge con conflicto
En la rama PRICNCIPAL **main** ponemos **Hola** en el fichero **1.txt** y hacemos commit

~~~
git checkout main
echo "Hola" >> 1.txt
git add .
git commit -m "hola en 1.txt"
~~~

Ahora nos posicionamos en la rama v0.2 que antes se habia creado y ponemos **Adios** en el fichero **1.txt** y hacemos tambien commit

~~~
git checkout v0.2
echo "Adios" >> 1.txt
git add .
git commit -m "adios en 1.txt"
~~~

IMPORTANTE: Para realizar el **merge** debemos posicionarnos en la rama **main** PRINCIPAL y hacer un merge con la rama **v0.2**

~~~
git checkout main
git merge v0.2
vim 1.txt
git add .
git commit -m "Arreglamos merge en 1.txt con conflictos y solucionamos correctamente"
~~~

## Listado de ramas
Listamos las ramas con merge y las ramas sin merge

~~~
git branch --merged
git branch --no-merge
~~~

## Borrar la rama **v0.2**

Creamos un tag **v0.2**

~~~
git tag v0.2
~~~


Borramos la rama **v0.2**
~~~
git branch -d v0.2
~~~

## Listado de cambios
Listar los distintos commits con sus ramas y sus tags.

~~~
git config --global alias.list 'log --oneline --decorate --graph --all'
git list
~~~





