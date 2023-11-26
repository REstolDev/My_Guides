### Guía Rápida de Git y GitHub

- [Guía Rápida de Git y GitHub](#guía-rápida-de-git-y-github)
  - [1. Configuración Inicial](#1-configuración-inicial)
  - [2. Iniciar un Repositorio](#2-iniciar-un-repositorio)
  - [3. Clonar un Repositorio](#3-clonar-un-repositorio)
  - [4. Trabajar con Ramas](#4-trabajar-con-ramas)
  - [5. Realizar Cambios](#5-realizar-cambios)
  - [6. Fusionar Ramas](#6-fusionar-ramas)
  - [7. Resolución de Conflictos](#7-resolución-de-conflictos)
  - [8. Subir Cambios a GitHub](#8-subir-cambios-a-github)
  - [9. Descargar Cambios desde GitHub](#9-descargar-cambios-desde-github)
  - [10. Git Flow (Extensiones de Git)](#10-git-flow-extensiones-de-git)
  - [11. Convención de Commits (Conventional Commits)](#11-convención-de-commits-conventional-commits)
  - [12. GitIgnore](#12-gitignore)
  - [13. Borrar un Repositorio Local](#13-borrar-un-repositorio-local)
  - [14. Borrar un Repositorio Remoto en GitHub](#14-borrar-un-repositorio-remoto-en-github)
  - [15. Configurar un Repositorio Remoto](#15-configurar-un-repositorio-remoto)
- [GitHub Actions: Automatización de Procesos en GitHub](#github-actions-automatización-de-procesos-en-github)
- [GitHub Issues y Pull Requests: Seguimiento y Revisión](#github-issues-y-pull-requests-seguimiento-y-revisión)

#### 1. Configuración Inicial

Configurar tu nombre de usuario y correo electrónico:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

#### 2. Iniciar un Repositorio

Crear un nuevo repositorio local:

```bash
git init
```

#### 3. Clonar un Repositorio

Clonar un repositorio existente desde GitHub:

```bash
git clone URL_del_Repositorio
```

#### 4. Trabajar con Ramas

Crear una nueva rama:

```bash
git branch nombre_de_la_rama
```

Cambiar a una rama existente:

```bash
git checkout nombre_de_la_rama
```

Crear y cambiar a una nueva rama:

```bash
git checkout -b nombre_de_la_rama
```

#### 5. Realizar Cambios

Verificar el estado de los archivos:

```bash
git status
```

Agregar archivos al área de preparación (staging):

```bash
git add nombre_del_archivo
```

Hacer un commit:

```bash
git commit -m "Mensaje descriptivo del commit"
```

#### 6. Fusionar Ramas

Cambiar a la rama destino:

```bash
git checkout rama_destino
```

Realizar la fusión:

```bash
git merge rama_origen
```

#### 7. Resolución de Conflictos

Si hay conflictos durante la fusión, resolverlos en los archivos afectados y luego:

```bash
git add nombre_del_archivo
git merge --continue
```

#### 8. Subir Cambios a GitHub

Subir cambios a la rama actual:

```bash
git push origin nombre_de_la_rama
```

#### 9. Descargar Cambios desde GitHub

Actualizar tu repositorio local con los cambios remotos:

```bash
git pull origin nombre_de_la_rama
```

#### 10. Git Flow (Extensiones de Git)

Instalar Git Flow:

```bash
apt-get install git-flow (Linux)
brew install git-flow (macOS)
```

Iniciar un nuevo proyecto Git Flow:

```bash
git flow init
```

#### 11. Convención de Commits (Conventional Commits)

Seguir la convención para mensajes de commit semánticos:

- **`feat`:** nueva funcionalidad
- **`fix`:** corrección de errores
- **`docs`:** cambios en la documentación
- **`chore`:** tareas de mantenimiento

#### 12. GitIgnore

- **`.gitignore`:** Crear un archivo `.gitignore` para ignorar archivos/directorios en Git.

#### 13. Borrar un Repositorio Local

Eliminar un repositorio local (asegúrate de estar en el directorio correcto):

```bash
rm -rf nombre_del_repositorio
```

#### 14. Borrar un Repositorio Remoto en GitHub

1. Ve a la página del repositorio en GitHub.
2. En la pestaña "Settings", desplázate hacia abajo hasta la sección "Danger Zone".
3. Haz clic en "Delete this repository".
4. Sigue las instrucciones para confirmar la eliminación.

#### 15. Configurar un Repositorio Remoto

Agregar un repositorio remoto:

```bash
git remote add nombre_remoto URL_del_Remoto
```

Eliminar un repositorio remoto:

```bash
git remote remove nombre_remoto
```

Ver la lista de remotos configurados:

```bash
git remote -v
```

Cambiar la URL de un remoto existente:

```bash
git remote set-url nombre_remoto nueva_URL
```

> Recuerda tener precaución al borrar repositorios, ya que esta acción no se puede deshacer y eliminará todos los datos asociados al repositorio.

### GitHub Actions: Automatización de Procesos en GitHub

GitHub Actions es una poderosa herramienta de automatización que permite a los desarrolladores definir flujos de trabajo personalizados directamente en su repositorio de GitHub. Estos flujos de trabajo consisten en acciones, unidades de trabajo predefinidas o personalizadas que realizan tareas específicas. Aquí hay algunos aspectos clave para entender y aprovechar GitHub Actions:

1. **Flujos de Trabajo (Workflows):** Los flujos de trabajo son secuencias de acciones que se ejecutan automáticamente en respuesta a eventos específicos, como la creación de una solicitud de extracción o el envío de un nuevo commit. Estos flujos de trabajo pueden ser personalizados para adaptarse a las necesidades del proyecto.

2. **Acciones (Actions):** Son los componentes fundamentales de GitHub Actions. Una acción puede ser cualquier tarea automatizada, desde compilar y probar el código hasta implementar en un entorno de producción. GitHub Actions proporciona una amplia variedad de acciones predefinidas, y los usuarios también pueden crear sus propias acciones personalizadas.

3. **Eventos:** Los flujos de trabajo se desencadenan por eventos específicos, como push (envío de cambios al repositorio), pull_request (creación o actualización de una solicitud de extracción), entre otros. La automatización basada en eventos ayuda a mantener la coherencia en el proceso de desarrollo.

4. **Matrices (Matrices):** Permite ejecutar un flujo de trabajo en varias configuraciones al mismo tiempo. Esto es útil para probar el código en diferentes versiones de lenguajes, entornos o sistemas operativos.

5. **Secretos (Secrets):** GitHub Actions proporciona una forma segura de almacenar y utilizar información sensible, como claves de API o tokens de acceso, mediante el uso de secretos. Estos secretos se pueden acceder dentro de los flujos de trabajo sin exponer la información confidencial.

6. **Integración Continua (CI) y Entrega Continua (CD):** GitHub Actions es comúnmente utilizado para implementar prácticas de CI/CD, lo que significa que los desarrolladores pueden integrar y probar cambios automáticamente, y luego implementarlos en entornos de producción de manera eficiente.

### GitHub Issues y Pull Requests: Seguimiento y Revisión

GitHub Issues y Pull Requests son herramientas esenciales para gestionar y colaborar en proyectos de desarrollo de software. Estas funciones permiten un seguimiento efectivo de problemas, la planificación de tareas y la revisión de código colaborativa:

1. **Issues (Problemas):** Los problemas se utilizan para realizar un seguimiento de tareas, mejoras, errores y otras unidades de trabajo. Pueden etiquetarse, asignarse a miembros del equipo y clasificarse según su estado (abierto, cerrado, en progreso, etc.). Los problemas proporcionan un medio para la comunicación y colaboración entre los miembros del equipo.

2. **Milestones (Hitos):** Los hitos agrupan problemas y pull requests relacionados para un

 lanzamiento específico o un conjunto de funcionalidades. Facilitan la planificación y el seguimiento del progreso a lo largo del tiempo.

3. **Pull Requests (Solicitudes de Extracción):** Las solicitudes de extracción son propuestas de cambios que los colaboradores envían al proyecto. Permiten la revisión del código, comentarios y la integración de nuevas características o correcciones. Las discusiones en las solicitudes de extracción facilitan la colaboración y garantizan la calidad del código.

4. **Revisión de Código:** GitHub proporciona herramientas para revisar cambios en las solicitudes de extracción. Los revisores pueden comentar líneas específicas de código, aprobar o solicitar modificaciones antes de la fusión. La revisión de código es esencial para mantener altos estándares de calidad y consistencia en el código base.

5. **Integración con Flujos de Trabajo:** GitHub Actions se puede integrar directamente en las solicitudes de extracción para ejecutar pruebas automatizadas, análisis estático de código y otras tareas relevantes antes de la fusión.

En conjunto, GitHub Actions y las funciones de seguimiento y revisión en GitHub proporcionan un entorno colaborativo y automatizado que mejora la eficiencia y calidad en el desarrollo de software. Estas herramientas son esenciales para equipos que buscan optimizar sus flujos de trabajo y garantizar la entrega de software de alta calidad.