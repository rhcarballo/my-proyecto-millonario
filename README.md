Roberto Hernández Carballo  
1º DAM

# my-proyecto-millonario
Crear un repositorio en vuestro GitHub llamado my-proyecto-millonario.

Clonar vuestro repositio en local.
    - Repositorio clonado

## Commit inicial

Añadir al README.md los comanddos utilizados hasta ahora y hacer un coomit inicial con el mensaje commit inicial.

    ```code
    - git add .
    - git commit -m "commit inicial"
        - salida
        [main 2fe8d1c] commit inicial
        1 file changed, 13 insertions(+), 1 deletion(-)
        - salida
    ```

## Push inicial

Subir los cambios al repositorio remoto.

    ```code
    - git push origin main
        - salida
        Username for 'https://github.com': rhcarballo
        Password for 'https://rhcarballo@github.com': 
        Enumerando objetos: 5, listo.
        Contando objetos: 100% (5/5), listo.
        Compresión delta usando hasta 4 hilos
        Comprimiendo objetos: 100% (2/2), listo.
        Escribiendo objetos: 100% (3/3), 446 bytes | 446.00 KiB/s, listo.
        Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0
        To https://github.com/rhcarballo/my-proyecto-millonario
        b3671c7..2fe8d1c  main -> main
        - salida
    ```
### Pregunta

Si has clonado el repostorio es necesirio que parte del comando anterior puedo omitir.Justifica tu respuesta en el fichero. 

Al haber clonado el repositorio, podemos omitir algunos pasos, por ejemplo el caso de la creación del README.md. Si creas el fichero junto al repositorio directamente en la plataforma de github, podemos omitir el código necesario para crear el README desde la terminal. 

## Ignorar archivos

Crear en el repositorio local un fichero llamado privado.txt.

    ```code
    - touch privado.txt
    ```
Crear en el repositorio local una carpeta llamada privada.

    ```code
    - mkdir privada
    ```

Realizar los cambios oportunos para que tanto el archivo como la carpeta sean ignorados por git.

    ```code
    - echo "privado.txt" >> .gitignore
    - echo "/privada" >> .gitignore
    - git add .
    - git commit -m "añadido fichero .gitignore"
        - salida
        [main 0986155] añadido fichero .gitignore
        2 files changed, 33 insertions(+), 1 deletion(-)
        create mode 100644 .gitignore
        - salida
    ```

### Pregunta

el fichero y el directorio privado debe de subir al repositorio si se encuentra añadido al fichero .gitingnore. [Si/No]. Justifica tu respuesta en el fichero.

La respuesta es no. Este tipo de archivos no deben subirse al repositorio, ya que de por sí, Git ignorará todos los archivos que tienen .gitignore. 

## Añadir fichero 1.txt

1. Añadir fichero 1.txt

    ```code
    - touch 1.txt
    - git add .
    - git commit -m "añadido 1.txt"
        - salida
        [main 08af7d8] añadido 1.txt
        2 files changed, 33 insertions(+)
        create mode 100644 1.txt
        - salida
    ```
### Pregunta

Si ejecutado las acciones add y commit, que realiza cada una sobre el/los ficheros. Justifica tu respuesta en el fichero

La acción add, guarda los archivos con las últimas modificaciones realizadas, puede hacerse con archivos específicos (git add nombre-archivo), o de todos los archivos del repositorio (git add .), para posterioirmente subirlos al repositorio.

La acción commit tiene la función de añadir un comentario cada vez que vayamos a guardar o subir cambios de los archivos modificados. 

## Crear el tag v0.1

1. Crear un tag v0.1.

    ```code
    - git tag v0.1
    ```

___(Hasta este punto, se han realizado las acciones en Linux, ahora trajaré en un windows)___

## Subir el tag v0.1

1. Subir los cambios al repositorio remoto.

    ```code
    - git push --tag origin master
        - salida
        error: src refspec master does not match any
        error: failed to push some refs to 'https://github.com/rhcarballo/my-proyecto-millonario'
        - salida
    ```
- __Tras haber dado este error, lo he vuelto a intentar pero en vez de escribir master, he probado con main. Esto es lo que se ha documentado:__

    ```code
    - git push --tag origin main
        - salida 
        Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
        To https://github.com/rhcarballo/my-proyecto-millonario
        * [new tag]         v0.1 -> v0.1
        - salida
    ```
__Ahora que hemos visto que el error se ha solucionado, podemos continuar.__

### Pregunta

¿Qué es un tag sobre un repositorio git, en nuestro caso Github?. Justifica tu respuesta.

En un repositorio Git, ___tag___ es una herramienta a la que se le puede denominar como "etiqueta", ya que se usa para marcar un punto en el historial de ese repositorio, pudiendo hacer y guardar distintas versiones de lo que estamos trabajando.

## Crear una rama v0.2

1. Crear una rama v0.2.

    ```code
    - git branch v0.2
    ```
2. Posiciona tu trabajo en esta rama

    ```code
    - git checkout v0.2
        - salida
        Switched to branch 'v0.2'
        M       README.md
        - salida
    ```

## Añadir fichero 2.txt

1. Añadir un fichero 2.txt en la rama v0.2.

En este caso hay que buscar un equivalente a touch para windows, por lo que en vez de usar touch usaremos "echo . > 2.txt"

    ```code
    - echo . > 2.txt
    - git add .
    - git commit -m "añadido 2.txt"
        - salida
        [v0.2 d270f72] añadido  2.txt
        2 files changed, 3 insertions(+), 1 deletion(-)
        create mode 100644 2.txt
        - salida
    ```
### Pregunta

Cuando estamos trabajando con ramas, cual es su fin, y sentido en organizaciones pequeñas/medianas/grandes. Justifica tu respuesta.

Las ramas permiten que al trabajar en una organización cada trabajador vaya progresando en su parte del trabajo, para luego unir todas las ramas en una sola, lo que sería la rama principal. 

## Creamos rama remota

1. Subir los cambios al repositorio remoto. 

    ```code
    - git push origin v0.2
        - salida
        Enumerating objects: 9, done.
        Counting objects: 100% (9/9), done.
        Delta compression using up to 8 threads
        Compressing objects: 100% (6/6), done.
        Writing objects: 100% (7/7), 1.48 KiB | 1.48 MiB/s, done.
        Total 7 (delta 3), reused 0 (delta 0), pack-reused 0
        remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
        remote:
        remote: Create a pull request for 'v0.2' on GitHub by visiting:
        remote:      https://github.com/rhcarballo/my-proyecto-millonario/pull/new/v0.2
        remote:
        To https://github.com/rhcarballo/my-proyecto-millonario
        * [new branch]      v0.2 -> v0.2
        - salida
    ```

## Merge directo

1. Posicionarse en la rama master/main según sea tu rama principal.

    ```code
    - git checkout main
        - salida
        error: Your local changes to the following files would be overwritten by checkout:
        README.md
        Please commit your changes or stash them before you switch branches.
        Aborting.
        - salida
    ```

- Tras este error, haremos lo que se nos indica en el aviso y procederemos a seguir con la tarea

    ```code
    - git add .
    - git commit -m "Terminamos el apartado Crear rama remota"
        - salida
        [v0.2 0909369] Terminamos el apartado Crear rama remota
        1 file changed, 52 insertions(+), 1 deletion(-)
        - salida
    
    - git checkout main
        - salida
        Switched to branch 'main'
        Your branch is up to date with 'origin/main'.
        - salida
    ```
2. Hacer un merge de la rama v0.2 en la rama master/main.

    ```code
    - git merge v0.2 -m "merge v0.2 sin conflictos"
        - salida
        Updating 3286df7..4f0ecf3
        Fast-forward (no commit created; -m option ignored)
            2.txt     | Bin 0 -> 8 bytes
        README.md | 128 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
        2 files changed, 127 insertions(+), 1 deletion(-)
        create mode 100644 2.txt
        - salida
    ```

### Pregunta

Se tendrían que producir conflictos en esta acción. [Si/No] Justifica tu respuesta en el fichero

La respuesta es sí y no, todo depende de un factor. Tenemos que tener en cuenta que en estos casos un conflicto se produce cuando un archivo o fichero se ha modificado de forma diferente en dos ramas distintas. Por lo que en caso de que se haya producido esto, la respueta es sí. Pero en caso de que el archivo se haya modificado desde una sola rama, no tendrían que surgir conflictos. 

## Merge con conflicto

1. En la rama master/main poner Hola en el fichero 1 y hacer commit.

    ```code
    - git checkout main
        - salida
        Already on 'main'                    
        M       README.md
        Your branch is ahead of 'origin/main' by 4 commits.
        (use "git push" to publish your local commits)
        - salida
    - echo "Hola" >> 1.txt
        - salida
        En línea: 1 Carácter: 16
        + echo >> "Hola" >> 1.txt
        +                ~~~~~~~~
        El flujo de salida de este comando ya está redirigido.
        + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
        + FullyQualifiedErrorId : StreamAlreadyRedirected
        - salida
    
    - git add .
    - git commit -m "hola en 1.txt"
        - salida
        [main a914c8a] hola en 1.txt
        1 file changed, 49 insertions(+), 1 deletion(-)
        - salida
    ```

2. Posicionarse en la rama v0.2 y poner Adiós en el fichero "1.txt" y hacer commit.

nota: Se ha tenido que instalar el editor de texto Vim para que el comando funcione de manera correcta.

    ```code
    - git checkout v0.2
    - echo "Adios" >> 1.txt
    - git add .
    - git commit -m "adios en 1.txt"
        - salida 
        [v0.2 bd0a9ee] adios en 1.txt
         1 file changed, 0 insertions(+), 0 deletions(-)
        PS C:\Users\rober\OneDrive\Escritorio\rhcarballo\my-proyecto-millonario> vim 1.txt
        - salida
    ```

3. Posicionarse de nuevo en la rama master/main y hacer un merge con la rama v0.2

    ```code
    - git checkout master
        - salida
        Switched to branch 'main'
        Your branch is ahead of 'origin/main' by 6 commits.
        (use "git push" to publish your local commits)
        - salida
    
    - git merge v0.2
        - salida
        Merge made by the 'ort' strategy.
        1.txt | Bin 0 -> 16 bytes
        1 file changed, 0 insertions(+), 0 deletions(-)
        - salida

    - vim 1.txt
        - se entró al editor de texto, para salir de este hay que escribir :wq
    - git add .
    - git commit -m "arreglado merge en 1.txt
        - salida
        [main 379f8ca] arreglado merge en 1.txt
        2 files changed, 0 insertions(+), 0 deletions(-)
         create mode 100644 .1.txt.un~
        create mode 100644 1.txt~
        - salida
    ```

## Listado de ramas

1. Listar las ramas con merge y las ramas sin merge.

    ```code
    - git branch --merged
        - salida
        * main
        v0.2
        - salida
    
    - git branch --no-merged 
    ```

## Arreglar conflicto

1. Arreglar conflicto anterior y hacer un commit.

    ```code
    - vim 1.txt
    - git add .
    - git commit -m "arreglado merge en 1.txt"
        - salida
        [main e089156] arreglado merge en 1.txt
        2 files changed, 61 insertions(+), 1 deletion(-)
        - salida
    ```
## Borrar rama

1. Crear un tag v0.2.

    ```code
    - git tag v0.2
    ```

2. Borrar la rama v0.2.

    ```code
    - git branch -d v0.2
        - salida
        Deleted branch v0.2 (was bd0a9ee).
        - salida
    ```
## Listado de cambios

1. Listar los distintos commits con sus ramas y sus tags.

    ```code 
    - git config --global alias.list 'log --oneline -- decorate --graph --all'
    - git list
        - salida
        * e089156 (HEAD -> main, tag: v0.2) arreglado merge en 1.txt
        * 379f8ca arreglado merge en 1.txt
        *   ab36c11 Merge branch 'v0.2'
        |\
        | * bd0a9ee adios en 1.txt
        * | d262289 hola en 1.txt 2ºintento
        * | a914c8a hola en 1.txt
        |/
        * 4f0ecf3 Terminamos el apartado Crear rama remoto pero este es otro intento del checkout
        * 0909369 Terminamos el apartado Crear rama remota
        * d270f72 (origin/v0.2) añadido  2.txt
        * 0895567 Seguimos con el trabajo pero hay que probar código equivalente a touch
        - salida
    ```

#### Fin de documentación.