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
## Añadir fichero 1.txt

1. Añadir fichero 1.txt

        ```code
        - touch 1.txt
        - git add .
        - git commit -m "añadido 1.txt"



