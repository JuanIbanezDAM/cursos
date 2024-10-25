# Comandos Git Bash

Iniciar un nuevo repositorio vacío  
$ ```git init```

Establecer nombre de usuario  
$ ```git config --global user.name "John Doe"```

Establecer email  
$ ```git config --global user.email johndoe@example.com```

Cambiar la rama que se crea por defecto a main  
$ ```git config --global init.defaultBranch main```

Ver usuarios y configuración de Git  
$ ```git config --list```

Configurar VS Code por defecto para Git  
$ ```git config --global core.editor "code --wait"```

## Las 3 áreas de Git  
Un archivo puede estar en cualquiera de las tres áreas; cada una de las áreas representa un estado distinto de ese archivo en nuestro repositorio.  
  Desde el archivo original hasta el repositorio:  
   - Directorio de trabajo (Working directory): La carpeta del proyecto que contiene los archivos y el directorio .git del repositorio.
   - Área de preparación (Staging area): Conjunto de archivos y cambios que serán incluidos en el próximo commit.
   - Repositorio: Directorio que contiene todas las versiones del proyecto. Es la parte
            directorio .git: Es la parte del repositorio que se copia cuando clonas un repositorio. ¡La parte más importante de Git!

## Los 3 estados de los archivos.
Según en el área que se encuentren:

   - Modificada (Modified): - Directorio de trabajo M
   - Preparada (Staged): - Área de preparación A
   - Confirmada (Committed): - Repositorio

## Cómo subir un archivo al repositorio

Añadir el archivo al área de preparación  
$ ```git add nombre_de_archivo.txt```  
$ ```git add .```

Comprobar el estado del Directorio de trabajo y el Área de preparación  
$ ```git status```

Eliminar un archivo del área de preparación  
$ ```git rm --cached nombre_de_archivo.txt```

## ¿Qué es un commit?  
Es un registro o "foto" del estado de un proyecto en un momento específico (modificaciones de un archivo, un nuevo archivo, un nuevo directorio, etc.).  
Los commits van acompañados de un mensaje que tiene que representar los cambios realizados.  
Git le asigna a cada commit un identificador único llamado SHA o HASH.  
   - Cambios realizados
   - Dónde se realizaron los cambios
   - Quién realizó los cambios: fecha-usuario-email

## Convenciones del commit.  
Conjunto de reglas para crear los mensajes del commit.  
  Tipo: describen el propósito del commit:  
       - feat: Nueva funcionalidad
       - fix: Corregir un error
       - docs: Cambios en la documentación
       - test: Agregar pruebas o correcciones a las ya existentes
       - refactor: Refactorización de código

Crear un commit  
$ ```git commit -m "tipo(ámbito): descripción"```
Ejemplo:  
$ ```git commit -m "docs: Agregar archivo de documentación sobre Git"```

Ver historial de commits  
$ ```git log```

Deshacer el último commit  
$ ```git reset --soft HEAD~1```

## Ramas
Representan un estado o "copia" del proyecto. La rama principal es main, la cual contiene toda la estructura final del proyecto.  
Podemos cambiar entre ramas para acceder a diferentes versiones del proyecto y fusionarlas para añadir todos los cambios finales.  
  Por convención, los nombres de las ramas son:  
   - main: Rama principal del proyecto (producción)
   - develop: Rama dedicada al desarrollo creada a partir de main
   - release: Rama dedicada a la fase de prueba
   - feature: Rama que crearemos para trabajar en nuevas funcionalidades. Siempre en minúsculas y con guiones en medio y número de versión, ej. feature/footer-001
   - fix: Rama que crearemos para corregir errores.

Crear una rama  
Recuerda que la rama que crees será una copia de la rama en la que te encuentres.  
$ ```git branch mi-rama```
Ejemplo:  
$ ```git branch feature/footer-001```

Cambiar de ramas  
$ ```git switch mi-rama```
$ ```git checkout mi-rama```

Crear una rama y posicionarse en ella  
$ ```git switch -c mi-rama```
$ ```git checkout -b mi-rama```

Listar ramas creadas.  
$ ```git branch```

Renombrar una rama  
$ ```git branch -m nuevo-nombre-mi-rama```
Debes estar directamente en la rama que quieres renombrar.  
$ ```git branch -m mi-rama nuevo-nombre-mi-rama```

Eliminar una rama 
Aplica solo a las ramas del repositorio local.  
$ ```git branch -d mi-rama```


## Fusionar ramas (Merge)
Nos sirve para agregar las distintas funcionalidades que se han desarrollado a la rama final.  
Debes estar en la rama final a la hora de fusionarlas.  

Fusionar ramas  
$ ```git merge mi-rama```

Conflicto al fusionar ramas  
$ ```git merge --continue```

## Clonar un repositorio
Crea una copia local de un repositorio remoto, incluyendo sus versiones e historial de commits.
Origin es el nombre que normalmente le asignamos al repositorio remoto que clonamos. Es un estandar y es el nombre que le vamos a asignar en git, en nuestra copia local del repositorio.

Clonar un respositorio
$ ```git clone```
