 <div style="text-align: center"> 

# ***Visión general del CLI y referencia de comandos***


> FUENTE [https://docs.angular.lat/cli]

El CLI de Angular es una herramienta de línea de comandos que se utiliza para inicializar, desarrollar, estructurar y mantener aplicaciones de Angular directamente desde la terminal.
Instalando el CLI de Angular

Las últimas versiones del CLI de Angular pueden ser instaladas siguiendo los mismos lineamientos de la última versión de Angular respaldada. Versiones menores pueden ser instaladas por separado.

 ### *MENÚ*</div>

- [***Visión general del CLI y referencia de comandos***](#visión-general-del-cli-y-referencia-de-comandos)
    - [*MENÚ*](#menú)
  - [**Instalar el CLI usando el gestor de paquetes npm**](#instalar-el-cli-usando-el-gestor-de-paquetes-npm)
  - [**Flujo de trabajo básico**](#flujo-de-trabajo-básico)
    - [Referencia rápida comandos CLI](#referencia-rápida-comandos-cli)
    - [*Ayuda*](#ayuda)
  - [*Crear, construir y servir nuevo proyecto*](#crear-construir-y-servir-nuevo-proyecto)
    - [Crear](#crear)
    - [Abrir](#abrir)
    - [Cambiar de directorio](#cambiar-de-directorio)
    - [Crear más aplicaciones dentro de una area de trabajo](#crear-más-aplicaciones-dentro-de-una-area-de-trabajo)
    - [Estructura de una aplicación](#estructura-de-una-aplicación)
    - [Agregar nuevos archivos](#agregar-nuevos-archivos)
    - [Establecer y recuperar valores de configuración](#establecer-y-recuperar-valores-de-configuración)
  - [**La sintaxis del lenguaje de comando del CLI**](#la-sintaxis-del-lenguaje-de-comando-del-cli)
    - [Booleanos y opciones enumeradas](#booleanos-y-opciones-enumeradas)
  - [**Command Overview**](#command-overview)
 

## **Instalar el CLI usando el gestor de paquetes npm**
     
`npm install -g @angular/cli`

    
## **Flujo de trabajo básico**

Ejecute la herramienta en la línea de comandos a través del ejecutable ng.

### Referencia rápida comandos CLI
Listado de algunos comandos básicos del CLI de Angular:

| Comando                                      | Descripción                                          |
| ------------------------------------------- | ---------------------------------------------------- |
| `ng new nombreProyecto`                     | Crea un nuevo proyecto Angular.                     |
| `ng serve`                                  | Inicia un servidor de desarrollo para la aplicación. |
| `ng generate component nombreComponente`   | Genera un nuevo componente.                         |
| `ng generate service nombreServicio`       | Genera un nuevo servicio.                           |
| `ng generate module nombreModulo`           | Genera un nuevo módulo.                             |
| `ng generate directive nombreDirectiva`     | Genera una nueva directiva.                         |
| `ng generate pipe nombrePipe`               | Genera una nueva tubería (pipe).                    |
| `ng build`                                 | Compila la aplicación para producción.              |
| `ng test`                                  | Ejecuta pruebas unitarias.                          |
| `ng e2e`                                   | Ejecuta pruebas end-to-end.                         |
| `ng lint`                                  | Analiza el código en busca de problemas.            |
| `ng help`                                  | Muestra la ayuda para los comandos de Angular CLI. |

Estos son algunos de los comandos más comunes que se utilizan con Angular CLI para crear, desarrollar, compilar y probar aplicaciones Angular. 
 
### *Ayuda*
La ayuda se encuentra disponible en la línea de comandos. Ingrese lo siguiente para listar comandos u opciones para un comando dado (Ejemplo: generate) con una breve descripción.
      
`ng help`
`ng generate --help`

## *Crear, construir y servir nuevo proyecto*

### Crear
Para crear, construir y servir un nuevo proyecto de Angular básico en el servidor de desarrollo, ve al directorio padre de tu nueva área de trabajo, usa los siguientes comandos:

~~~    
ng new my-first-project
cd my-first-project
ng serve
~~~
    
### Abrir
En tu navegador, abre [http://localhost:4200/] para ver como se esta ejecutando la nueva aplicación. Cuando usas el comando ng serve para construir una aplicación y servirla localmente, el servidor automáticamente reconstruye la aplicación y recarga la página cuando tu cambias cualquiera de los archivos base.

>Cuando tu ejecutas ng new my-first-project se creará una nueva carpeta, llamada my-first-project, en tu actual directorio de trabajo. Cuando tu quieres crear archivos dentro de una carpeta, asegurate que tienes los permisos necesarios en tu actual directorio de trabajo antes de ejecutar el comando.


### Cambiar de directorio
Si tu actual directorio de trabajo no es el lugar adecuado para tu proyecto, lo puedes cambiar a un directorio más apropiado ejecutando primero cd `<path-to-other-directory>`.
Área de trabajo y archivos del proyecto


### Crear más aplicaciones dentro de una area de trabajo
El comando `ng new` crea un área de trabajo de Angular en la carpeta y genera una nueva estructura de la aplicación. El área trabajo puede tener múltiples aplicaciones y librerías. La aplicación inicial creada por el comando ng new está en el nivel superior del área de trabajo. Cuando generas una aplicación adicional o librería en tu área de trabajo, esta irá dentro una subcarpeta llamada projects/.

### Estructura de una aplicación
Una aplicación recientemente generada consiste en archivos base para un módulo raíz, con un componente raíz y una plantilla. Cada aplicación tiene una carpeta src que contiene la lógica, datos y recursos.


### Agregar nuevos archivos
Puedes editar los archivos generados directamente, o agregarlos y modificarlos usando los comandos del CLI. Usar el comando `ng generate` para agregar nuevos archivos para componentes adicionales y servicios, y código para nuevos pipes, directivas, etc. Comandos como son `add y generate`, los que crean y operan en aplicaciones y librerías, deben ser ejecutadas dentro del área de trabajo o carpeta del proyecto.

    Para ver más acerca de la estructura del archivo del área de trabajo .

Configuración del área de trabajo y proyecto.

Se crea un único archivo de configuración de área de trabajo, angular.json, en el nivel superior del área de trabajo. Aquí es donde estableces los valores predeterminados por proyecto para las opciones de los comandos CLI y especificar configuraciones que se usan cuando el CLI construye un proyecto para diferentes targets.

### Establecer y recuperar valores de configuración

El comando `ng config` te permite establecer y recuperar valores de configuración desde la línea de comandos, o puedes editar directamente el archivo angular.json. Tenga en cuenta que los nombres opcionales en el archivo de configuración debe usar camelCase, mientras que los nombres opcionales que se suministra a los comandos pueden ser tanto camelCase o dash-case.

    Para más información configuración de área de trabajo.
    Vea el schema completo para angular.json.

## **La sintaxis del lenguaje de comando del CLI**

La sintaxis del comando se muestra de la siguiente manera:

`ng commandNameOrAlias requiredArg [optionalArg] [options]`

    La mayoría de los comandos, y algunas opciones, tienen alias. Los alias son mostrados en la declaración de sintaxis para cada comando.

    Nombres opcionales llevan como prefijo el doble guión (--). La opción alias lleva como prefijo un guión (-). Los argumentos no llevan prefijo. Por ejemplo:

          
          
    `ng build my-app -c production`

        

    Típicamente, el nombre de un artefacto generado puede ser dado como un argumento para el comando o ser especificado con --nombre opcional.

    Argumento y nombres opcionales pueden ser dados en cualquiera camelCase o dash-case. --myOptionName es equivalente a --my-option-name.

`ng build my-app -c production`


    Típicamente, el nombre de un artefacto generado puede ser dado como un argumento para el comando o ser especificado con --nombre opcional.

    Argumento y nombres opcionales pueden ser dados en cualquiera camelCase o dash-case. 

`--myOptionName` es equivalente a `--my-option-name.`

### Booleanos y opciones enumeradas

Opciones booleanas tienen dos formas: 
`--thisOption`establece la bandera, `--noThisOption` la borra. Si no se proporciona ninguna de las opciones, la bandera permanece en su estado predeterminado, como se indica en la documentación de referencia.

Los valores permitidos son dados con cada descripción de opción enumerada, con el valor predeterminado en negrita.
Rutas relativas

Las opciones que especifican archivos pueden ser dadas por rutas absolutas, o rutas relativas al directorio actual de trabajo, que generalmente es el espacio de trabajo o proyecto raíz.
Esquemas

Los comandos `ng generate` y `ng add` toman como argumento el artefacto o la librería para ser generado o agregado al proyecto actual. Además de las opciones generales, cada artefacto o librería define sus propias opciones en un esquema. Las opciones de esquema se proporcionan al comando en el mismo formato que las opciones de comando inmediatas.

## **Command Overview**
<table>
  <thead>
    <tr>
      <th>Command</th>
      <th>Alias</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>

  <tr>
    <td><a href="https://docs.angular.lat/cli/add">add</a></td>
    <td></td>
    <td><p>Adds support for an external library to your project.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/analytics">analytics</a></td>
    <td></td>
    <td><p>Configures the gathering of Angular CLI usage metrics. See <a href="https://angular.io/https://docs.angular.lat/cli/usage-analytics-gathering">https://angular.io/https://docs.angular.lat/cli/usage-analytics-gathering</a>.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/build">build</a></td>
    <td>b </td>
    <td><p>Compiles an Angular app into an output directory named dist/ at the given output path. Must be executed from within a workspace directory.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/config">config</a></td>
    <td></td>
    <td><p>Retrieves or sets Angular configuration values in the angular.json file for the workspace.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/deploy">deploy</a></td>
    <td></td>
    <td><p>Invokes the deploy builder for a specified project or for the default project in the workspace.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/doc">doc</a></td>
    <td>d </td>
    <td><p>Opens the official Angular documentation (angular.io) in a browser, and searches for a given keyword.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/e2e">e2e</a></td>
    <td>e </td>
    <td><p>Builds and serves an Angular app, then runs end-to-end tests using Protractor.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/generate">generate</a></td>
    <td>g </td>
    <td><p>Generates and/or modifies files based on a schematic.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/help">help</a></td>
    <td></td>
    <td><p>Lists available commands and their short descriptions.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/lint">lint</a></td>
    <td>l </td>
    <td><p>Runs linting tools on Angular app code in a given project folder.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/new">new</a></td>
    <td>n </td>
    <td><p>Creates a new workspace and an initial Angular app.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/run">run</a></td>
    <td></td>
    <td><p>Runs an Architect target with an optional custom builder configuration defined in your project.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/serve">serve</a></td>
    <td>s </td>
    <td><p>Builds and serves your app, rebuilding on file changes.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/test">test</a></td>
    <td>t </td>
    <td><p>Runs unit tests in a project.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/update">update</a></td>
    <td></td>
    <td><p>Updates your application and its dependencies. See <a href="https://update.angular.io/">https://update.angular.io/</a></p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/version">version</a></td>
    <td>v </td>
    <td><p>Outputs Angular CLI version.</p>
</td>
  </tr>

  <tr>
    <td><a href="https://docs.angular.lat/cli/xi18n">xi18n</a></td>
    <td>i18n-extract </td>
    <td><p>Extracts i18n messages from source code.</p>
</td>
  </tr>

</tbody>
</table>