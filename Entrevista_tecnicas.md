# **Entrevistas técnicas**
- [**Entrevistas técnicas**](#entrevistas-técnicas)
- [Preguntas entrevista técnica de Angular](#preguntas-entrevista-técnica-de-angular)
  - [¿Qué es Angular?](#qué-es-angular)
  - [¿Qué ventajas me da un framework como Angular respecto a hacer la misma aplicación web en Vanilla JavaScript?](#qué-ventajas-me-da-un-framework-como-angular-respecto-a-hacer-la-misma-aplicación-web-en-vanilla-javascript)
  - [¿Qué es una inyección de dependencias en Angular?](#qué-es-una-inyección-de-dependencias-en-angular)
  - [¿Qué es un componente en Angular?](#qué-es-un-componente-en-angular)
  - [¿Qué es Angular CLI?](#qué-es-angular-cli)
  - [¿Qué es una pipe en Angular? ¿Podrías poner un ejemplo?](#qué-es-una-pipe-en-angular-podrías-poner-un-ejemplo)
  - [¿Qué es una directiva en Angular? Pon algunos ejemplos](#qué-es-una-directiva-en-angular-pon-algunos-ejemplos)
  - [¿Qué es Lazy Load en Angular?](#qué-es-lazy-load-en-angular)
  - [Pon un ejemplo de cómo mostrarías el valor de una variable del componente TS en el HTML de un componente de Angular.](#pon-un-ejemplo-de-cómo-mostrarías-el-valor-de-una-variable-del-componente-ts-en-el-html-de-un-componente-de-angular)
  - [¿Para qué sirve ngOnInit? Pon un ejemplo](#para-qué-sirve-ngoninit-pon-un-ejemplo)


# Preguntas entrevista técnica de Angular

## ¿Qué es Angular?
Angular es un framework mantenido por Google que nos permite hacer Single Page Applications (SPA) en frontend, es decir, aplicaciones web en entorno cliente. La principal característica de una SPA es que el usuario no observa recargas de la página web, de forma que obtiene una mejor experiencia de usuario y puede acceder a la información de forma más rápida.

## ¿Qué ventajas me da un framework como Angular respecto a hacer la misma aplicación web en Vanilla JavaScript?
Para empezar, Angular usa TypeScript, lo que otorga más robustez a mi aplicación web al tener yo un mejor control de los datos gracias al tipado que me ofrece TypeScript. Por otro lado, al ser Angular un framework, puedo utilizar sus funcionalidades para ahorrarme escribir código (por ejemplo, puedo validar campos de un formulario de forma muy sencilla con una línea de código, mientras que con Vanilla JavaScript escribiría este código de forma manual, consumiendo más tiempo y líneas de código)-lo cual ayuda a que el código sea más mantenible y limpio. Para finalizar, una de las grandes ventajas que yo aprecio de Angular es su estructura: al obligarme a programar con la estructura estándar del framework, yo ya sé qué me puede ofrecer un servicio, qué me puede ofrecer un módulo… de modo que obtengo código más eficiente, limpio y mantenible que programando la misma aplicación web en Vanilla JavaScript.


## ¿Qué es una inyección de dependencias en Angular?
Mediante una inyección de dependencias yo puedo inyectar a mi componente una dependencia para utilizar una funcionalidad en el mismo, de un servicio, por ejemplo. Imaginemos que tenemos un servicio que llama a una API que me ofrece información meteorológica. Yo tendré la llamada a la API en el servicio, ahí recojo los datos, y en mi componente tengo el HTML y el archivo de TS dónde voy a manejar la lógica de dicho componente. Digamos que dicho componente simplemente va a mostrar los datos que reciba de la API. Al inyectar la dependencia del servicio tendré acceso a sus métodos, de forma que en el componente de TS puedo llamar al método, guardar la información recibida de la API en una variable y mostrarla en el HTML de la forma que considere más conveniente.

## ¿Qué es un componente en Angular?
Una aplicación de Angular es como un puzzle, dónde yo integraré los distintos componentes de mi aplicación, que serían las piezas de dicho puzzle. Por ejemplo, un componente puede ser el menú de mi aplicación web, y en ella tendré como mínimo un fichero de HTML (la vista de mi componente) y un fichero de TypeScript (dónde ejecuto la lógica de mi componente). También es muy normal tener un fichero de estilos (con CSS, por ejemplo) y otro fichero de testing unitario, dónde compruebo que este componente funciona efectivamente como yo lo he programado para que funcione. Según como tenga estructurada mi aplicación web, en dicho componente puedo tener también otro tipo de ficheros, pero digamos que estos son los ficheros más básicos que van a conformar un componente de Angular.


## ¿Qué es Angular CLI?
Es una interfaz de línea de comando que yo puedo utilizar para crear mis proyectos de Angular de forma rápida y sencilla, con el siguiente comando: ng new nombreProyecto. Al crear el proyecto me solicitará distintas configuraciones, como si quiero tipado estricto, si utilizaré para los estilos CSS/SASS…

## ¿Qué es una pipe en Angular? ¿Podrías poner un ejemplo?
Una pipe en Angular es una herramienta que nos permite modificar de forma visual la información que mostramos al usuario. Es importante resaltar que no modifica el valor que tiene una determinada variable, sino simplemente cómo se le presenta al usuario. Supongamos que tenemos información recogida de un usuario mediante un formulario, y dicho usuario se llama “pedro gómez ramírez”. El usuario, en un descuido, ha puesto toda su información en minúscula. Pero yo quiero que la persona que tiene que consultar esta información, la consulte cómo debería de mostrarse, es decir, con la primera letra del nombre y del apellido en mayúscula. Para ello puedo utilizar un pipe, en este caso sería el pipe “TitleCase”. Con este pipe, aunque en mi programa el nombre de dicho usuario seguiría mal escrito, al mostrárselo a otro usuario que consulte los nombres, leerá “Pedro Gómez Ramírez” porque el pipe ha puesto la primera letra de cada palabra en mayúscula y el resto en minúsculas, mejorando la experiencia de usuario.

## ¿Qué es una directiva en Angular? Pon algunos ejemplos
Las directivas de Angular me permiten modificar el HTML de forma muy sencilla. Existen directivas, las llamadas Directivas de Atributo, que simplemente me permiten modificar el estilo de un elemento del DOM (por ejemplo, cuando uso Angular Material y añado mat-button como atributo al botón de mi HTML, realmente lo que estoy es aplicándole una directiva, que me aplicará los estilos de Angular Material correspondientes). Existen otras directivas que me permiten modificar la estructura del DOM y por ello se llaman Directivas Estructurales. Por ejemplo, con un *ngIf aplico renderizado condicional sobre un elemento del DOM, que se mostrará en función de la condición que hayamos aplicado a la directiva.


## ¿Qué es Lazy Load en Angular?
Lazy Load es un patrón de diseño que me permite que sólo cargue en un determinado momento lo que el usuario necesita en dicho momento, optimizando por tanto el rendimiento de mi aplicación web. A día de hoy es un estándar a la hora de desarrollar aplicaciones web de entorno cliente con Angular.

## Pon un ejemplo de cómo mostrarías el valor de una variable del componente TS en el HTML de un componente de Angular.
Por ejemplo, yo puedo tener en mi código una variable que sea name y el valor de dicha variable sea Pedro. Puedo mostrarla en mi HTML mediante interpolación, pongamos que la quiero mostrar con un H1, de la siguiente forma: <h1> {{name}}</h1>. Mediante la interpolación, muestro de forma dinámica el valor de una variable de mi fichero TypeScript de mi componente de Angular en mi fichero HTML y, por tanto, ofrezco esa información al usuario gracias a la interfaz gráfica que proporciona el HTML.

## ¿Para qué sirve ngOnInit? Pon un ejemplo
Es un hook o función que forma parte del ciclo de vida de los componentes de Angular, y se ejecuta una vez que el componente está creado. Todo el código que hayamos escrito dentro del ngOnInit se ejecutará
