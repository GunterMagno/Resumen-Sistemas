# Resumen-Sistemas
¡Perfecto! Ahora que tengo todos los archivos, incluyendo el último sobre **Gestión de Procesos**, procederé a actualizar el resumen completo y la "chuleta" con los comandos y conceptos más importantes para que puedas estudiar de manera eficiente para tu examen.

---

### **Resumen Completo de Comandos y Conceptos de Linux**

#### **1. Gestión de Archivos y Directorios**
- **`pwd`**: Muestra la ruta absoluta del directorio actual.
- **`mkdir`**: Crea directorios. Opción `-p` para crear directorios intermedios.
  - Ejemplo: `mkdir -p dir1/dir2`
- **`tree`**: Muestra la estructura de directorios en forma de árbol.
  - Opciones: `-a` (muestra archivos ocultos), `-d` (solo directorios), `-f` (rutas completas).
- **`cd`**: Cambia de directorio.
  - Ejemplos: `cd ..` (sube un nivel), `cd ~` (va al directorio home).
- **`ls`**: Lista archivos y directorios.
  - Opciones: `-l` (lista detallada), `-a` (muestra archivos ocultos), `-R` (recursivo).
  - Ejemplo: `ls -la /home`
- **`cp`**: Copia archivos y directorios.
  - Opciones: `-r` (recursivo para directorios), `-i` (pregunta antes de sobrescribir).
  - Ejemplo: `cp -r dir1 dir2`
- **`mv`**: Mueve o renombra archivos y directorios.
  - Ejemplo: `mv archivo1 archivo2` (renombra), `mv archivo1 dir/` (mueve).
- **`rm`**: Elimina archivos y directorios.
  - Opciones: `-r` (recursivo), `-f` (fuerza la eliminación).
  - Ejemplo: `rm -rf dir/`
- **`rmdir`**: Elimina directorios vacíos.
  - Ejemplo: `rmdir dir/`

#### **2. Visualización de Archivos**
- **`cat`**: Muestra el contenido de un archivo.
  - Ejemplo: `cat archivo.txt`
- **`more`**: Muestra archivos paginados.
  - Ejemplo: `more archivo.txt`
- **`less`**: Similar a `more`, pero permite navegar hacia atrás.
  - Opciones: `-N` (muestra números de línea), `/palabra` (busca una palabra).
  - Ejemplo: `less -N archivo.txt`
- **`touch`**: Crea archivos vacíos o actualiza la fecha de modificación.
  - Ejemplo: `touch archivo.txt`

#### **3. Enlaces**
- **`ln`**: Crea enlaces duros o simbólicos.
  - Enlace duro: `ln archivo1 archivo2`
  - Enlace simbólico: `ln -s archivo1 enlace`
  - Los enlaces duros apuntan al mismo inodo, mientras que los simbólicos son accesos directos.

#### **4. Permisos**
- **`chmod`**: Cambia los permisos de archivos y directorios.
  - Formato simbólico: `chmod u=rwx,g=rx,o=r archivo.txt`
  - Formato octal: `chmod 755 archivo.txt`
- **`chown`**: Cambia el propietario de un archivo o directorio.
  - Ejemplo: `chown usuario:grupo archivo.txt`
- **`chgrp`**: Cambia el grupo propietario de un archivo o directorio.
  - Ejemplo: `chgrp grupo archivo.txt`
- **`umask`**: Establece los permisos por defecto para nuevos archivos y directorios.
  - Ejemplo: `umask 022`

#### **5. Redireccionamientos y Tuberías**
- **`>`**: Redirecciona la salida a un archivo (sobrescribe).
  - Ejemplo: `ls > archivo.txt`
- **`>>`**: Redirecciona la salida a un archivo (añade al final).
  - Ejemplo: `ls >> archivo.txt`
- **`2>`**: Redirecciona los errores a un archivo.
  - Ejemplo: `comando 2> errores.txt`
- **`|`**: Conecta la salida de un comando con la entrada de otro.
  - Ejemplo: `ls | grep txt`

#### **6. Filtros**
- **`grep`**: Busca patrones en archivos o salidas.
  - Ejemplo: `grep "palabra" archivo.txt`
- **`cut`**: Extrae columnas o campos de un archivo.
  - Ejemplo: `cut -d: -f1 /etc/passwd`
- **`head`**: Muestra las primeras líneas de un archivo.
  - Ejemplo: `head -n 10 archivo.txt`
- **`tail`**: Muestra las últimas líneas de un archivo.
  - Ejemplo: `tail -n 10 archivo.txt`
- **`sort`**: Ordena líneas de texto.
  - Ejemplo: `sort archivo.txt`
- **`wc`**: Cuenta líneas, palabras y caracteres.
  - Ejemplo: `wc -l archivo.txt`

#### **7. Comando `find`**
- **`find`**: Busca archivos y directorios.
  - Ejemplo: `find /home -name "*.txt"`
  - Opciones: `-type` (tipo de archivo), `-name` (nombre), `-exec` (ejecuta un comando).
  - Ejemplo avanzado: `find /home -type f -name "*.txt" -exec rm {} \;`

#### **8. Delimitación de Profundidad en `find`**
- **`-maxdepth`**: Limita la profundidad de búsqueda.
  - Ejemplo: `find /home -maxdepth 2 -name "*.txt"`
- **`-mindepth`**: Define el nivel mínimo de profundidad para la búsqueda.
  - Ejemplo: `find /home -mindepth 2 -name "*.txt"`

#### **9. Gestión de Procesos**
- **`ps`**: Muestra los procesos en ejecución.
  - Opciones: `-e` (todos los procesos), `-f` (formato completo), `-u` (procesos de un usuario).
  - Ejemplo: `ps -ef`
- **`pstree`**: Muestra los procesos en forma de árbol.
  - Ejemplo: `pstree`
- **`top`**: Muestra los procesos en tiempo real.
  - Ejemplo: `top`
- **`kill`**: Envía señales a procesos.
  - Señales comunes: `SIGKILL (9)`, `SIGTERM (15)`.
  - Ejemplo: `kill -9 PID`
- **`jobs`**: Muestra los trabajos en segundo plano.
  - Ejemplo: `jobs`
- **`bg`**: Reanuda un proceso en segundo plano.
  - Ejemplo: `bg %1`
- **`fg`**: Trae un proceso al primer plano.
  - Ejemplo: `fg %1`
- **`nohup`**: Ejecuta un proceso que no se detiene al cerrar la terminal.
  - Ejemplo: `nohup comando &`
- **`time`**: Mide el tiempo de ejecución de un comando.
  - Ejemplo: `time sleep 5`
- **`nice`**: Cambia la prioridad de un proceso.
  - Ejemplo: `nice -n 10 comando`
- **`renice`**: Cambia la prioridad de un proceso en ejecución.
  - Ejemplo: `renice 10 -p PID`

---

### **Chuleta de Comandos**

| **Comando** | **Descripción** | **Ejemplo** |
|-------------|-----------------|-------------|
| `pwd`       | Muestra el directorio actual | `pwd` |
| `mkdir`     | Crea directorios | `mkdir dir1` |
| `tree`      | Muestra estructura de directorios | `tree -a` |
| `cd`        | Cambia de directorio | `cd /home` |
| `ls`        | Lista archivos | `ls -la` |
| `cp`        | Copia archivos | `cp archivo1 archivo2` |
| `mv`        | Mueve o renombra | `mv archivo1 dir/` |
| `rm`        | Elimina archivos | `rm -rf dir/` |
| `cat`       | Muestra contenido | `cat archivo.txt` |
| `more`      | Muestra paginado | `more archivo.txt` |
| `less`      | Muestra con navegación | `less archivo.txt` |
| `touch`     | Crea archivos vacíos | `touch archivo.txt` |
| `ln`        | Crea enlaces | `ln -s archivo1 enlace` |
| `chmod`     | Cambia permisos | `chmod 755 archivo.txt` |
| `chown`     | Cambia propietario | `chown usuario:grupo archivo.txt` |
| `chgrp`     | Cambia grupo | `chgrp grupo archivo.txt` |
| `umask`     | Establece permisos por defecto | `umask 022` |
| `>`         | Redirecciona salida | `ls > archivo.txt` |
| `>>`        | Añade a archivo | `ls >> archivo.txt` |
| `2>`        | Redirecciona errores | `comando 2> errores.txt` |
| `|`         | Conecta comandos | `ls | grep txt` |
| `grep`      | Busca patrones | `grep "palabra" archivo.txt` |
| `cut`       | Extrae columnas | `cut -d: -f1 /etc/passwd` |
| `head`      | Muestra primeras líneas | `head -n 10 archivo.txt` |
| `tail`      | Muestra últimas líneas | `tail -n 10 archivo.txt` |
| `sort`      | Ordena líneas | `sort archivo.txt` |
| `wc`        | Cuenta líneas, palabras, caracteres | `wc -l archivo.txt` |
| `find`      | Busca archivos | `find /home -name "*.txt"` |
| `-maxdepth` | Limita profundidad en `find` | `find /home -maxdepth 2 -name "*.txt"` |
| `-mindepth` | Define nivel mínimo en `find` | `find /home -mindepth 2 -name "*.txt"` |
| `ps`        | Muestra procesos | `ps -ef` |
| `pstree`    | Muestra procesos en árbol | `pstree` |
| `top`       | Muestra procesos en tiempo real | `top` |
| `kill`      | Envía señales a procesos | `kill -9 PID` |
| `jobs`      | Muestra trabajos en segundo plano | `jobs` |
| `bg`        | Reanuda proceso en segundo plano | `bg %1` |
| `fg`        | Trae proceso al primer plano | `fg %1` |
| `nohup`     | Ejecuta proceso sin detenerse | `nohup comando &` |
| `time`      | Mide tiempo de ejecución | `time sleep 5` |
| `nice`      | Cambia prioridad de proceso | `nice -n 10 comando` |
| `renice`    | Cambia prioridad de proceso en ejecución | `renice 10 -p PID` |

---

### **Conceptos Importantes**
- **Rutas**:
  - **Absoluta**: Comienza desde la raíz (`/`). Ejemplo: `/home/usuario/archivo.txt`.
  - **Relativa**: Depende del directorio actual. Ejemplo: `../archivo.txt`.
  - **Personal**: Usa `~` para referirse al directorio home. Ejemplo: `~/archivo.txt`.

- **Permisos**:
  - Lectura (`r`), Escritura (`w`), Ejecución (`x`).
  - Se aplican a: Propietario, Grupo, Otros.
  - Ejemplo: `-rwxr-xr--` (propietario tiene todos los permisos, grupo tiene lectura y ejecución, otros solo lectura).

- **Metacaracteres**:
  - `*`: Cualquier cadena de caracteres.
  - `?`: Un solo carácter.
  - `[abc]`: Cualquier carácter dentro de los corchetes.
  - Ejemplo: `ls *.txt` (lista todos los archivos `.txt`).

- **Procesos**:
  - **PID**: Identificador único de un proceso.
  - **PPID**: Identificador del proceso padre.
  - **Foreground**: Procesos que se ejecutan en primer plano.
  - **Background**: Procesos que se ejecutan en segundo plano.
  - **Señales**: Comandos como `kill` envían señales a procesos (ej: `SIGKILL`, `SIGTERM`).

---

Este resumen y la chuleta deberían ayudarte a repasar los comandos y conceptos clave de Linux de manera rápida y efectiva. ¡Buena suerte en tu examen! 😊

