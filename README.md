# Guía de Estudio: Gestión de la Documentación - Control de Versiones

## Conceptos mínimos que tenemos que saber sobre el control de versiones

### Definir brevemente en qué consiste el control de versiones
- El control de versiones consiste en un sistema que registra todos los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo.
- Permite a los equipos colaborar, rastrear el historial de modificaciones y revertir a versiones anteriores.

### Explicación de conceptos clave
- **Repositorio local:** Versiones guardadas en el ordenador de un usuario.
- **Copia local:** Archivos en el sistema de archivos del usuario que representan el contenido del repositorio.
- **Stage (Index):** Área intermedia donde se preparan los cambios antes de confirmarlos.
- **Repositorio remoto:** Servidor donde se almacena una copia del repositorio local, accesible para otros colaboradores.
- **Log:** Historial de cambios y versiones.
- **Conflicto:** Situación que ocurre cuando dos versiones tienen cambios incompatibles.

### Estados de un fichero
- **Sin seguimiento:** Archivo que no está incluido en el control de versiones.
- **Confirmado:** Archivo cuya última versión está registrada en el repositorio.
- **Modificado:** Archivo que ha sido cambiado desde su última versión.
- **Preparado:** Archivo que se encuentra en el Stage.
- **Ignorado:** Archivo que se encuentra en el archivo `.gitignore`.

### Operaciones principales en Git
- **Clone:** Copia un repositorio remoto en la máquina del usuario.
- **Add:** Añade las modificaciones en el Stage para ser confirmadas.
- **Commit:** Confirma los cambios guardados en el Stage y crea una nueva versión.
- **Merge:** Combina los cambios de varias ramas en una sola.
- **Rebase:** Reorganiza la historia de confirmaciones de una rama sobre otra.
- **Push:** Introduce los commits realizados en el repositorio local en el repositorio remoto.
- **Pull:** Descarga los commits del repositorio remoto y después hace un Merge con la rama local.
- **Fork:** Crea una copia independiente en un repositorio remoto.
- **Pull Request:** Solicita la integración de los cambios de una rama o repositorio en un repositorio remoto ajeno.

### Traducción de términos clave (Inglés - Español)
- **Staged:** Preparado.
- **Log:** Historial.
- **Clone:** Clonar.
- **Add:** Añadir.
- **Commit:** Confirmación.
- **Merge:** Fusión.
- **Rebase:** Rebasar.
- **Push:** Subir.
- **Pull:** Bajar (descargar).
- **Fork:** Bifurcación.
- **Pull Request:** Solicitud de fusión.

### Servicios de repositorio remoto
- GitHub
- GitLab

---

## Qué tenemos que saber hacer con Git (y GitHub)

### En el intérprete de comandos de git-bash

```bash
# Mostrar en qué directorio estamos
pwd

# Crear un directorio
mkdir <nombre>

# Cambiar de directorio
cd <ruta>

# Mostrar la lista de ficheros de un directorio
ls

# Borrar un fichero
rm <nombre_fichero>

# Cambiar (mover) un fichero de directorio
mv <nombre_fichero> <lugar_de_destino>
```

### En local

```bash
# Crear un repositorio local en nuestra máquina desde cero (sin remoto)
git init

# Ignorar ficheros
# Crear un archivo llamado .gitignore y especificar los patrones.

# Preparar ficheros para ser confirmados
git add <fichero>

# Confirmar cambios en un repositorio local
git commit -m "<comentario de la versión>"

# Deshacer la operación de preparar
git reset <fichero>

# Deshacer la operación de confirmar, distinguiendo entre niveles
# soft, mixed, hard
git reset <commit> --soft/mixed/hard

# Identificar el estado de un fichero o ficheros en un repositorio local
git status

# Descartar los cambios de un fichero de trabajo
git restore <archivo>

# Crear una rama en un repositorio local
git branch <rama> | git checkout -b <rama>

# Cambiar de rama
git checkout <rama>

# Fundir los cambios de una rama en otra
git merge <rama_origen>

# Injertar una rama en otra
git rebase <rama_origen>
```

### En remoto (con GitHub)

```bash
# Configurar git para que trabaje tras un proxy
git config --global http.proxy <url_proxy>

# Replicar un repositorio remoto localmente
git clone <url_repositorio>

# Replicar un repositorio local en un servidor remoto
git remote add origin <url_remoto>
git push -u origin main

# Traer los cambios de un repositorio remoto a uno local
git pull

# Resolver conflictos tras un pull o merge
git status
# Editar los archivos con conflictos y luego:
git add <archivo_resuelto>
git commit

# Enviar los cambios de un repositorio local a uno remoto
git push

# Enviar una rama local al repositorio remoto con tracking
git push -u origin <branch>

# Incorporar cambios del repositorio remoto a una rama local
git pull origin <branch>

# Crear un repositorio remoto vacío
# Se crea desde la interfaz de GitHub.

# Invitar a colaboradores
# Se realiza en la página de GitHub, en configuración del repositorio.

# Realizar un pull request entre dos ramas
git push origin <rama>
# Luego, usar la interfaz de GitHub para solicitar la fusión.

# Realizar un pull request entre repositorios tras un Fork
# Proponer cambios desde tu repositorio hacia el original.
```

---
