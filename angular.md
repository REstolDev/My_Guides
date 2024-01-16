
 <div style="text-align: center"> 
 
 # ***ANGULAR***

 
 ### *MENÚ*</div>



- [***ANGULAR***](#angular)
    - [*MENÚ*](#menú)
- [Resumen de Angular](#resumen-de-angular)
  - [Componentes](#componentes)
  - [Módulos](#módulos)
  - [Servicios](#servicios)
  - [Modelos](#modelos)
  - [Pipes](#pipes)
  - [Rutas](#rutas)
  - [Resumen Angular CLI (Command Line Interface)](#resumen-angular-cli-command-line-interface)
    - [Uso de Angular CLI](#uso-de-angular-cli)
  - [Formularios](#formularios)
    - [Formularios Reactivos](#formularios-reactivos)
    - [Formularios basados en plantillas](#formularios-basados-en-plantillas)
  - [Importaciones Comunes](#importaciones-comunes)
- [**Styles**](#styles)
  - [Great blog that explains CSS encapsulation: \[https://blog.angular.io/the-state-of-css-in-angular-4a52d4bd2700\]](#great-blog-that-explains-css-encapsulation-httpsblogangulariothe-state-of-css-in-angular-4a52d4bd2700)
    - [**The State of CSS in Angular**](#the-state-of-css-in-angular)
    - [Global CSS — The Way You’re Used To](#global-css--the-way-youre-used-to)
    - [Component-Scoped CSS](#component-scoped-css)
    - [Three Modes of Component Encapsulation](#three-modes-of-component-encapsulation)
      - [Deep CSS](#deep-css)
      - [But I want that functionality!](#but-i-want-that-functionality)
        - [Use Custom Properties (AKA CSS Variables) —](#use-custom-properties-aka-css-variables-)
        - [Use globally-scoped styles sheets and emulated encapsulation —](#use-globally-scoped-styles-sheets-and-emulated-encapsulation-)
        - [Use ::ng-deep — If you need this today, use ::ng-deep.](#use-ng-deep--if-you-need-this-today-use-ng-deep)
  - [Official Angular documentation about styling:\[https://angular.io/guide/component-styles\]](#official-angular-documentation-about-stylinghttpsangularioguidecomponent-styles)
- [***Manipulando el DOM***](#manipulando-el-dom)
  - [@HostListener:](#hostlistener)
  - [Renderer2:](#renderer2)
- [***Manipulando el DOM  de forma segura***](#manipulando-el-dom--de-forma-segura)
    - [Angular, el framework multiplataforma](#angular-el-framework-multiplataforma)
  - [Manipulando el DOM con Renderer2, primeros pasos](#manipulando-el-dom-con-renderer2-primeros-pasos)
    - [Añadir o eliminar una clase de un elemento](#añadir-o-eliminar-una-clase-de-un-elemento)
    - [Añadir o eliminar un atributo](#añadir-o-eliminar-un-atributo)
    - [Llamar a un método del elemento](#llamar-a-un-método-del-elemento)
    - [Crear contenido en el DOM](#crear-contenido-en-el-dom)
      - [Crear un texto](#crear-un-texto)
- [***Manipula elementos del DOM (Renderer2) -- EJEMPLO***](#manipula-elementos-del-dom-renderer2----ejemplo)
      - [Ejemplo de lo que aprenderás](#ejemplo-de-lo-que-aprenderás)
    - [Así se resolvería con Vanilla JavaScript](#así-se-resolvería-con-vanilla-javascript)
    - [¿Por qué debo evitar los métodos de document?](#por-qué-debo-evitar-los-métodos-de-document)
    - [Usando Renderer2](#usando-renderer2)
- [**Forms**](#forms)
- [**How to deploy Angular Apps to GitHub Pages (gh-pages)**](#how-to-deploy-angular-apps-to-github-pages-gh-pages)
- [**Lazy Loading**](#lazy-loading)
- [Different Loading Strategies in Angular](#different-loading-strategies-in-angular)
  - [1. Eager Loading](#1-eager-loading)
  - [2. Lazy Loading](#2-lazy-loading)
  - [3. Preloading Strategies](#3-preloading-strategies)
    - [PreloadAllModules Strategy](#preloadallmodules-strategy)
    - [Custom Preloading Strategy](#custom-preloading-strategy)
  - [Understanding Lazy Loading](#understanding-lazy-loading)
    - [Benefits of Lazy Loading](#benefits-of-lazy-loading)
  - [Implementation in Angular](#implementation-in-angular)
    - [Step 1: Setup Routes](#step-1-setup-routes)
    - [Step 2: Create a Lazy Module](#step-2-create-a-lazy-module)
    - [Step 3: Routing within Lazy Module](#step-3-routing-within-lazy-module)
    - [Step 4: Use Lazy Components](#step-4-use-lazy-components)
  - [Best Practices](#best-practices)
  - [Conclusion](#conclusion)
- [**Optimize the Bundle Size**](#optimize-the-bundle-size)
  - [**Optimize the Bundle Size with Bundle Analyzer**](#optimize-the-bundle-size-with-bundle-analyzer)
  - [**Optimize the Bundle Size using Source Map Explorer**](#optimize-the-bundle-size-using-source-map-explorer)
  - [Why?](#why)
  - [Tools](#tools)
  - [What is Source Map Explorer?](#what-is-source-map-explorer)
  - [Why Source Map Explorer?](#why-source-map-explorer)
  - [Prerequisites](#prerequisites)
    - [Generated Files after Build](#generated-files-after-build)
    - [Browserlist](#browserlist)
    - [Installation of Source Map Explorer](#installation-of-source-map-explorer)
  - [Bundle Analysis](#bundle-analysis)
    - [Before Optimization](#before-optimization)
  - [Optimization 1: Browserlist Update](#optimization-1-browserlist-update)
    - [After Optimization 1](#after-optimization-1)
  - [Optimization 2: Removing Unwanted Packages](#optimization-2-removing-unwanted-packages)
    - [After Optimization 2](#after-optimization-2)
  - [Conclusion](#conclusion-1)



# Resumen de Angular

Angular es un framework de desarrollo web desarrollado por Google que se utiliza para construir aplicaciones web y móviles de una sola página (SPA) de manera eficiente y escalable. A continuación, se presentan los conceptos y funcionalidades básicos de Angular:

## Componentes

Los componentes son bloques de construcción fundamentales en Angular. Representan partes de la interfaz de usuario y encapsulan la lógica de la vista y el controlador. Cada componente tiene su propio archivo de plantilla HTML y se pueden anidar para crear interfaces de usuario complejas.

## Módulos

Los módulos son contenedores que agrupan componentes, servicios y otros recursos relacionados en una aplicación Angular. Cada aplicación Angular tiene al menos un módulo raíz, y puede tener varios módulos secundarios.

## Servicios

Los servicios son clases que proporcionan funcionalidades compartidas y lógica de negocio reutilizable en toda la aplicación. Se inyectan en componentes y otros servicios mediante la inyección de dependencias.

## Modelos
En Angular, los modelos son clases TypeScript que representan la estructura de datos utilizada en la aplicación. Estos modelos se utilizan para definir el formato de los datos que se manejan en la aplicación y a menudo se utilizan en combinación con servicios para recuperar y manipular datos. Los modelos son útiles para garantizar un tipado seguro en toda la aplicación y facilitar la comunicación entre componentes y servicios.

Ejemplo de un modelo simple en TypeScript:

```typescript

export class Usuario {
  id: number;
  nombre: string;
  email: string;
}
```

## Pipes

Los pipes son transformadores de datos que se utilizan para formatear y manipular la información que se muestra en la vista. Angular incluye pipes integrados y permite crear pipes personalizados.

## Rutas

Angular tiene un enrutador que permite navegar entre diferentes vistas o componentes de la aplicación sin necesidad de recargar la página. Las rutas se definen en un archivo de configuración y se pueden utilizar para crear aplicaciones de una sola página.

## Resumen Angular CLI (Command Line Interface)

Angular CLI es una herramienta de línea de comandos que simplifica la creación, desarrollo y gestión de proyectos de Angular. Con Angular CLI, puedes generar componentes, módulos, servicios, rutas y mucho más con comandos simples.

### Uso de Angular CLI

Para crear un nuevo proyecto de Angular:

```bash
ng new nombre-del-proyecto
```

Para generar un nuevo componente:

```bash
ng generate component nombre-del-componente
```

Para generar un nuevo módulo:

```bash
ng generate module nombre-del-modulo
```

Para generar un nuevo servicio:

```bash
ng generate service nombre-del-servicio
```

Para generar una nueva ruta:

```bash
ng generate module nombre-del-modulo
```


## Formularios

Angular proporciona un módulo llamado `FormsModule` que simplifica la gestión de formularios en la aplicación. Puedes crear formularios reactivos o basados en plantillas. Los formularios reactivos son más flexibles y poderosos, mientras que los formularios basados en plantillas son más simples y adecuados para casos más simples.

### Formularios Reactivos

Los formularios reactivos se basan en la programación reactiva y utilizan clases TypeScript para definir la estructura y la lógica del formulario. Esto permite una mayor flexibilidad y control sobre la validación y el comportamiento del formulario.

Ejemplo de un formulario reactivo:

```typescript
import { Component } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-mi-formulario',
  templateUrl: './mi-formulario.component.html'
})
export class MiFormularioComponent {
  miFormulario: FormGroup;

  constructor(private fb: FormBuilder) {
    this.miFormulario = this.fb.group({
      nombre: ['', Validators.required],
      email: ['', [Validators.required, Validators.email]]
    });
  }
}
```

### Formularios basados en plantillas

Los formularios basados en plantillas se definen directamente en el HTML utilizando directivas de Angular. Son más simples de configurar y son adecuados para formularios más simples.

Ejemplo de un formulario basado en plantillas:

```html
<form #miFormulario="ngForm" (ngSubmit)="submitForm(miFormulario)">
  <div class="form-group">
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" ngModel required>
  </div>
  <div class="form-group">
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" ngModel required email>
  </div>
  <button type="submit">Enviar</button>
</form>
```

## Importaciones Comunes

Algunas de las importaciones más comunes que se utilizan en Angular incluyen:


1. **NgModule**:

   - **Uso**: `NgModule` es una decoración utilizada para configurar un módulo de Angular. Los módulos son bloques de construcción fundamentales en una aplicación Angular y se utilizan para organizar y configurar componentes, servicios, rutas y otras funcionalidades relacionadas.
   - **Funcionalidades**: 
     - Configuración de rutas.
     - Declaración de componentes, directivas y pipes.
     - Importación de otros módulos.
     - Definición de servicios proporcionados a nivel de módulo.

   Ejemplo de uso:

   ```typescript
   import { NgModule } from '@angular/core';
   import { CommonModule } from '@angular/common';
   import { MiComponente } from './mi-componente.component';

   @NgModule({
     declarations: [MiComponente],
     imports: [CommonModule],
     providers: [MiServicio],
   })
   export class MiModulo { }
   ```

2. **Component**:

   - **Uso**: `Component` es una decoración utilizada para definir una clase como un componente Angular. Los componentes son responsables de gestionar la lógica y la vista de una parte específica de la interfaz de usuario.
   - **Funcionalidades**: 
     - Gestión de la lógica y la vista del componente.
     - Interacción con el ciclo de vida del componente.
     - Recepción de datos de entrada mediante `@Input`.
     - Emisión de eventos mediante `@Output`.

   Ejemplo de uso:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'mi-componente',
     templateUrl: './mi-componente.component.html',
     styleUrls: ['./mi-componente.component.css']
   })
   export class MiComponente {
     // Propiedades y métodos del componente
   }
   ```

3. **HttpClient**:

   - **Uso**: `HttpClient` se utiliza para realizar solicitudes HTTP a servidores desde una aplicación Angular.
   - **Funcionalidades**: 
     - Realización de solicitudes GET, POST, PUT, DELETE, etc.
     - Gestión de encabezados de solicitud y respuesta.
     - Conversión de respuestas JSON en objetos TypeScript.

   Ejemplo de uso para una solicitud GET:

   ```typescript
   import { HttpClient } from '@angular/common/http';

   constructor(private http: HttpClient) { }

   obtenerDatos() {
     return this.http.get('/api/datos');
   }
   ```

4. **RouterModule**:

   - **Uso**: `RouterModule` se utiliza para configurar las rutas de navegación en una aplicación Angular.
   - **Funcionalidades**:
     - Configuración de rutas y rutas anidadas.
     - Definición de rutas parametrizadas.
     - Navegación programática a través de rutas.

   Ejemplo de uso para configurar rutas:

   ```typescript
   import { RouterModule, Routes } from '@angular/router';

   const routes: Routes = [
     { path: 'inicio', component: InicioComponent },
     { path: 'perfil/:id', component: PerfilComponent },
     { path: '', redirectTo: '/inicio', pathMatch: 'full' }
   ];

   @NgModule({
     imports: [RouterModule.forRoot(routes)],
     exports: [RouterModule]
   })
   export class AppRoutingModule { }
   ```

5. **Injectable**:

   - **Uso**: `Injectable` es una decoración utilizada para marcar una clase como un servicio inyectable. Los servicios son clases que proporcionan funcionalidades compartidas en toda la aplicación.
   - **Funcionalidades**:
     - Inyección de dependencias en componentes, otros servicios, o cualquier clase que lo necesite.
     - Gestión de la lógica de negocio y la comunicación con servidores.

   Ejemplo de uso:

   ```typescript
   import { Injectable } from '@angular/core';

   @Injectable({
     providedIn: 'root'
   })
   export class MiServicio {
     // Lógica del servicio
   }
   ```


6. **ViewChild y ViewChildren**:

   - **Uso**: `ViewChild` y `ViewChildren` son decoradores que se utilizan para acceder a elementos del DOM o componentes hijos desde componentes padres en Angular.
   - **Funcionalidades**:
     - `ViewChild` se usa para obtener una referencia a un elemento del DOM o a un componente hijo.
     - `ViewChildren` se usa para obtener una colección de referencias a elementos del DOM o a componentes hijos que coinciden con un selector.
     - Se utilizan para manipular el contenido y el comportamiento de elementos en la vista desde el componente.

   Ejemplo de uso con `ViewChild`:

   ```typescript
   import { Component, ViewChild, ElementRef } from '@angular/core';

   @Component({
     selector: 'app-mi-componente',
     template: '<button #miBoton (click)="hacerAlgo()">Haz clic</button>'
   })
   export class MiComponente {
     @ViewChild('miBoton') miBoton: ElementRef;

     hacerAlgo() {
       // Acceder y manipular el botón
       this.miBoton.nativeElement.innerText = 'Clicado';
     }
   }
   ```

   Ejemplo de uso con `ViewChildren`:

   ```typescript
   import { Component, ViewChildren, QueryList } from '@angular/core';

   @Component({
     selector: 'app-mi-componente',
     template: '<div *ngFor="let item of items" #miItem>{{ item }}</div>'
   })
   export class MiComponente {
     @ViewChildren('miItem') items: QueryList<ElementRef>;

     // Puedes acceder a la lista de elementos y manipularlos
     modificarItems() {
       this.items.forEach(item => {
         item.nativeElement.style.color = 'blue';
       });
     }
   }
   ```

7. **Input y Output**:

   - **Uso**: `Input` y `Output` son decoradores que se utilizan para establecer comunicación entre componentes en Angular.
   - **Funcionalidades**:
     - `Input` se usa para pasar datos desde un componente padre a un componente hijo.
     - `Output` se usa para emitir eventos desde un componente hijo para que un componente padre los escuche.
     - Permiten compartir datos y eventos entre componentes de manera eficaz.

   Ejemplo de uso con `Input`:

   ```typescript
   import { Component, Input } from '@angular/core';

   @Component({
     selector: 'app-hijo',
     template: '<p>{{ mensaje }}</p>'
   })
   export class HijoComponent {
     @Input() mensaje: string;
   }
   ```

   Ejemplo de uso con `Output`:

   ```typescript
   import { Component, Output, EventEmitter } from '@angular/core';

   @Component({
     selector: 'app-hijo',
     template: '<button (click)="enviarMensaje()">Enviar</button>'
   })
   export class HijoComponent {
     @Output() mensajeEnviado = new EventEmitter<string>();

     enviarMensaje() {
       this.mensajeEnviado.emit('Hola desde el hijo');
     }
   }
   ```

8. **ActivatedRoute**:

   - **Uso**: `ActivatedRoute` se utiliza para obtener información sobre la ruta activa en un componente. Esto es especialmente útil cuando se necesitan datos de la URL o parámetros de ruta en un componente.
   - **Funcionalidades**:
     - Acceso a los parámetros de ruta.
     - Acceso a los fragmentos de URL.
     - Observación de cambios en la ruta activa.

   Ejemplo de uso:

   ```typescript
   import { Component } from '@angular/core';
   import { ActivatedRoute } from '@angular/router';

   @Component({
     selector: 'app-detalle',
     template: '<p>Detalle del producto {{ productId }}</p>'
   })
   export class DetalleComponent {
     productId: string;

     constructor(private route: ActivatedRoute) {
       this.productId = this.route.snapshot.paramMap.get('id');
     }
   }
   ```

   9. **Renderer2**:

 El `Renderer2` en Angular es una interfaz que actúa como una capa de abstracción para interactuar con el DOM de manera segura y eficiente. Antes de la introducción de `Renderer2`, se podía interactuar directamente con el DOM utilizando el objeto `Renderer`, pero esto tenía algunas desventajas, como problemas de seguridad y rendimiento en ciertos contextos. `Renderer2` fue introducido en Angular para abordar estos problemas.

 ***Cómo funciona `Renderer2` en Angular***

1. **Creación de instancias de `Renderer2`**: Para utilizar `Renderer2`, primero debes crear una instancia de esta interfaz. Puedes hacerlo mediante el uso de `RendererFactory2`, que Angular proporciona a través de la inyección de dependencias.

   ```typescript
   constructor(private rendererFactory: RendererFactory2) {
     // Crear una instancia de Renderer2
     this.renderer = this.rendererFactory.createRenderer(null, null);
   }
   ```

   - `rendererFactory.createRenderer(null, null)` crea una instancia de `Renderer2`. Los dos argumentos `null` indican que no está asociado a un componente específico.

2. **Manipulación segura del DOM**: Una vez que tienes una instancia de `Renderer2`, puedes utilizar sus métodos para interactuar con el DOM de manera segura. Algunos de los métodos más comunes son:

   - `createElement`: Crea un nuevo elemento HTML.
   - `setAttribute`: Establece un atributo en un elemento.
   - `removeAttribute`: Elimina un atributo de un elemento.
   - `addClass`: Agrega una clase CSS a un elemento.
   - `removeClass`: Elimina una clase CSS de un elemento.
   - `setStyle`: Establece un estilo CSS en un elemento.
   - `appendChild`: Agrega un elemento secundario a un elemento principal.
   - `removeChild`: Elimina un elemento secundario de un elemento principal.
   - Y muchos otros métodos para realizar diversas operaciones en el DOM.

3. **Beneficios de usar `Renderer2`**:

   - **Seguridad**: `Renderer2` realiza automáticamente las comprobaciones necesarias para garantizar que las operaciones en el DOM sean seguras. Esto ayuda a prevenir ataques XSS (cross-site scripting) al asegurarse de que los datos ingresados por el usuario no se interpreten como código malicioso.

   - **Portabilidad**: `Renderer2` es independiente del entorno subyacente. Puedes utilizarlo tanto en aplicaciones web como en aplicaciones nativas (por ejemplo, Angular para aplicaciones móviles) sin modificar tu código.

   - **Optimización de rendimiento**: Angular puede aplicar estrategias de cambio para optimizar la manipulación del DOM, como la agrupación de múltiples cambios en una sola operación de actualización del DOM. Esto mejora el rendimiento de la aplicación.

En resumen, `Renderer2` es una interfaz que ofrece una forma segura y eficiente de interactuar con el DOM en aplicaciones Angular. Facilita la manipulación del DOM sin sacrificar la seguridad y el rendimiento de la aplicación. Al utilizar `Renderer2`, puedes escribir código más limpio y seguro al trabajar con el DOM en tus componentes Angular.

 [****Más Info de como Manipular el DOM****](#manipulando-el-dom)  


# **Styles**

Suggested Documentation

-----------------
Great blog that explains CSS encapsulation: [https://blog.angular.io/the-state-of-css-in-angular-4a52d4bd2700]
-----------------

### **The State of CSS in Angular**
Author: Stephen Fluin


Styling applications is a critical part of delivering great experiences for users. Across the web we have Cascading Style Sheets (CSS) as a powerful standard for developers to define the look of an application separately from its construction.


By default in Angular, when you attach CSS directly to a component, we scope that css exclusively to that component. This scoping isolates it from the rest of your application. This additional capability means that there are two ways to use CSS with Angular.

### Global CSS — The Way You’re Used To
For as long as CSS has existed, styles loaded on a page have applied globally to every matching element on that page. Most developers are working with global styles like this every day, and the community has developed a myriad of different approach for managing and organizing this, ranging from simple prefixes to more involved systems like BEM and OOCS.

Angular components can be styled via global CSS the same as any other element in your application. Simply drop a `<link>` element on your page (typically in index.html) and you’re good to go! However, Angular additional gives developers more options for scoping your styles.

### Component-Scoped CSS
Angular’s component model empowers developers to build in isolation as much as possible. This applies to styles as well, where unexpected side effects from CSS can be undesirable.

We’ve all been in a situation where a seemingly innocuous change, like moving a component to a different location, caused an unexpected cascade of changes. This can happen when insufficiently scoped styles completely throw off a page’s layout. To help avoid experiences like this, Angular will scope a component’s styles such that they only apply within that component’s template.

### Three Modes of Component Encapsulation
Developers who use component-scoped CSS in Angular will default to emulated mode for this encapsulation. In emulated mode, we generate and attach random attributes to each instantiated component, and then create styles that use those generated attributes as selectors.

We also support Native mode, which will use Shadow DOM to create additional contexts and prevent cross-component leakage of styles. This will work in any browsers with support for Shadow DOM v1. Native mode creates a shadow root under each component, which will isolate the component completely, even from styles defined globally (global styles DO pierce components with emulated view encapsulation).

The third and last encapsulation you can choose is None, which means that all of your CSS ends up being globally applied. You can use this if you want to opt-out of Angular’s style encapsulation completely.

Read more about Component-Scoped CSS[https://angular.io/guide/component-styles]

#### Deep CSS
But what if I wanted to combine these two worlds? I want to write component-scoped CSS that affects the component itself as well as any children I put inside of it.

Angular and browsers have historically offered what is commonly known as the deep selector. This is also known by several other names, including >>>, /deep/, or the more official Shadow-Piercing descendant combinator.

The deep selector originated as an effort by the Blink team. It allowed developers to style across shadow roots. It was ultimately deprecated as it failed to meet standardization, performance, and developer experience expectations.

Prior to the release of Angular version 4.3, changes in tools such as SASS and other announcements mean that our existing interpretation of /deep/ was creating conflicts. In order to give developers a temporary reprieve from these externally-driven breaking changes, we created ::ng-deep which achieves the same functionality.

As we want to keep our emulated and native style encapsulations as functionality equivalent as possible (with the hope of future browser standardization), we don’t recommend new adoption of /deep/ or ::ng-deep when you can avoid it.

There’s some good coverage of ::ng-deep and the history of this feature in an article by Dor Moshe.

#### But I want that functionality!
We understand that there are legitimate use cases for component-scoped CSS, where your styles pierce into child components. Here are three ways you can achieve this:

##### Use Custom Properties (AKA CSS Variables) — 
While there isn’t complete browser support for Custom Properties yet, browser implementation of these capabilities will give developers the best combination of isolation and flexibility. Custom Properties, in effect, allow component authors to define an API surface for the styles of their components; they let developers decide what should be styled externally and what needs to stay consistent.
##### Use globally-scoped styles sheets and emulated encapsulation — 
Using traditional CSS you can refer to components by name as part of CSS selectors which will cause styles will be applied as they always have, including piercing down to child components, assuming that you use our emulated (default) view encapsulation on your components.
##### Use ::ng-deep — If you need this today, use ::ng-deep. 
This shouldn’t conflict with any 3rd party tools or new browser development. We are committed to keeping ::ng-deep around until a standards-based approach has achieved industry-wide support.


------------------
Official Angular documentation about styling:[https://angular.io/guide/component-styles]
------------------

# ***Manipulando el DOM***
##Diferencias entre @hostListener y Renderer2

@HostListener y Renderer2 son dos conceptos diferentes en Angular que se utilizan para abordar aspectos diferentes de la manipulación del DOM y la interacción con eventos. Aquí hay una explicación de ambas:

## @HostListener:
@HostListener es un decorador que se utiliza en Angular para escuchar eventos en el host, es decir, el elemento DOM en el que se encuentra el componente. Puedes usarlo para vincular métodos de tu componente a eventos del DOM, como clics, desplazamientos, pulsaciones de teclas, etc. El decorador @HostListener se coloca encima de un método en el componente y le permite reaccionar a eventos específicos.

Ejemplo:
~~~
typescript
Copy code
@Component({
  selector: 'app-my-component',
  template: '<button (click)="handleClick()">Click me</button>'
})
export class MyComponent {
  @HostListener('window:scroll', ['$event'])
  onScroll(event: Event) {
    // Manejar el evento de desplazamiento aquí
  }
  
  handleClick() {
    // Manejar el evento de clic aquí
  }
}
~~~
## Renderer2:

Renderer2 es una clase proporcionada por Angular que se utiliza para manipular el DOM de manera segura y eficiente. A diferencia de acceder directamente al DOM a través de document u otros objetos globales, Renderer2 abstrae la manipulación del DOM y proporciona un enfoque más seguro y compatible con el universo de Angular. Es especialmente útil cuando estás trabajando con aplicaciones que se pueden renderizar en entornos diferentes al navegador, como el renderizado del lado del servidor.

- Ejemplo:
~~~
typescript
Copy code
import { Component, Renderer2, ElementRef } from '@angular/core';

@Component({
  selector: 'app-my-component',
  template: '<button (click)="changeColor()">Change Color</button>'
})
export class MyComponent {
  constructor(private renderer: Renderer2, private el: ElementRef) {}

  changeColor() {
    const element = this.el.nativeElement;
    this.renderer.setStyle(element, 'color', 'blue');
  }
}
~~~

En resumen, @HostListener se utiliza para escuchar y reaccionar a eventos en el host del componente, mientras que Renderer2 se utiliza para manipular el DOM de manera segura y eficiente, evitando el acceso directo a objetos globales como document. Ambos son útiles en diferentes contextos y pueden complementarse en ciertas situaciones.




# ***Manipulando el DOM  de forma segura***

Es muy sencillo manipular directamente elementos del DOM en Angular, solo hay que echar mano de la clase ElementRef. Pero ¡cuidado! Angular lo etiqueta como una mala práctica. La manipulación directa del DOM crea un acoplamiento indeseado entre la capa de renderizado y la de lógica, que impide por ejemplo lanzar tu app en un web worker.

Para sortear este obstáculo tienes la clase Renderer2 de Angular. Renderer2 proporciona una API para acceder de forma segura a elementos nativos, incluso cuando no están soportados por la plataforma (web workers, server-side rendering, etc).

### Angular, el framework multiplataforma
Quizá no lo sabías, pero Angular se define como platform agnostic.
¿Qué quiere decir esto? Pues que Angular está diseñado para abstraerse del renderizado del DOM, y eso le permite funcionar en distintas plataformas, como:

Navegadores web
Servidores (Node.js)
Web Workers
Apps móviles nativas (NativeScript, React Native)
Por eso, es muy importante que cuando desarrolles en Angular, te acostumbres a NO UTILIZAR las variables globales document o window, o a manipular directamente el DOM con ElementRef.

Ninguno de estos elementos estará disponible en un entorno que no sea el navegador, y por tanto no podrás reutilizar tu código para renderizar desde servidor (con Angular Universal), meterlo en una app nativa, o conseguir el máximo rendimiento de tu interfaz ejecutándolo todo en un Web Worker.

Como he introducido antes, la forma correcta de manipular el DOM es a través de Renderer2.

## Manipulando el DOM con Renderer2, primeros pasos
En la documentación de Angular sobre Renderer2 puedes encontrar todos los métodos que te ofrece esta clase. Yo me voy a centrar en algunas de las manipulaciones más habituales.

Supongamos un componente de Angular que tiene un botón. Para poder manipular este elemento, necesito una referencia al mismo y para eso sí que utilizo ElementRef, junto con una template reference variable (myButton) el decorador @ViewChild.

Pero la manipulación no será a través del ElementRef, sino mediante el servicio Renderer2, así que lo primero que tengo que hacer es importarlo e inyectarlo.

~~~
import { Component, Renderer2 } from '@angular/core';

@Component({
  selector: 'app-root',
  template: '<button #myButton></button>'
})
export class AppComponent{
  @ViewChild("myButton") myButton: ElementRef;

  constructor(private renderer: Renderer2) { 
  }

}
~~~

### Añadir o eliminar una clase de un elemento
A partir de aquí, podría alterar las clases del elemento myButton con los métodos de Renderer2:

  addClass(el: any, name: string): void
  removeClass(el: any, name: string): void
Como puedes imaginar, name hace referencia la clase que quieres añadir/quitar. En cuanto a el, hace referencia al elemento nativo del DOM sobre el que quieres actuar (ElementRef.nativeElement).

Te enseño como quedaría, y añado en comentarios como sería el acceso directo (mala práctica) a través de ElementRef.

~~~
import { Component, Renderer2 } from '@angular/core';

@Component({
  selector: 'app-root',
  template: '<button #myButton></button>'
})
export class AppComponent{
  @ViewChild("myButton") myButton: ElementRef;

  constructor(private renderer: Renderer2) { }

  addMyClass(){
    //this.myButton.nativeElement.classList.add("my-class"); //BAD PRACTICE
    this.renderer.addClass(this.myButton.nativeElement, "my-class");
  }

  removeMyClass(){
    //this.myButton.nativeElement.classList.remove("my-class"); //BAD PRACTICE
    this.renderer.removeClass(this.myButton.nativeElement, "my-class");
  }

}
~~~

### Añadir o eliminar un atributo
Pongamos que quiero crear unos métodos para habilitar o deshabilitar mi botón por código. Renderer2 me ofrece los siguientes métodos.

~~~
  setAttribute(el: any, name: string, value: string, namespace?: string|null): void
  removeAttribute(el: any, name: string, namespace?: string|null): void
~~~

De nuevo, te enseño a usarlos y añado también la práctica errónea en comentario de código.

//...some stuff...
~~~
export class AppComponent{
  @ViewChild("myButton") myButton: ElementRef;
  constructor(private renderer: Renderer2) { }

  disable(){
    //this.myButton.nativeElement.setAttribute("disabled", "true"); //BAD PRACTICE
    this.renderer.setAttribute(this.myButton.nativeElement, "disabled", "true");
  }

  enable(){
   //this.myButton.nativeElement.removeAttribute("disabled"); //BAD PRACTICE
   this.renderer.removeAttribute(this.myButton.nativeElement, "disabled");
  }  

}
~~~

### Llamar a un método del elemento
La dinámica anterior es sencilla y muy similar para clases, atributos, propiedades o estilos. Pero cuando quieres llamar a un método del elemento por código (por ejemplo el método click de mi botón), te pueden entrar dudas.


  `selectRootElement(selectorOrNode: string|any): any`

Que te devuelve una versión platform-safe del elemento nativo del DOM.

El código correcto a continuación, y el incorrecto comentado:

~~~
export class AppComponent{
  @ViewChild("myButton") myButton: ElementRef;
  constructor(private renderer: Renderer2) { }

  clickButton(){
    //this.myButton.nativeElement.click(); //BAD PRACTICE
    this.renderer.selectRootElement(this.myButton.nativeElement).click();
  }

}
~~~
Esto y otras muchas buenas prácticas las encontrarás en mi curso Componentes en Angular – nivel PRO


### Crear contenido en el DOM
Siguiendo con el ejemplo, imagina que quiero añadirle un texto al botón. El texto del botón en realidad no es más que una cadena de texto que se encuentra en el nodo hijo del botón, así que para conseguirlo con Renderer2, podría seguir esta estrategia:

#### Crear un texto
Añadir ese texto como hijo del botón

~~~

export class AppComponent{
  @ViewChild("myButton") myButton: ElementRef;
  constructor(private renderer: Renderer2) { }

  addText(){
    let text = this.renderer.createText("my button");
    this.renderer.appendChild(this.myButton.nativeElement, text);
  } 

}
~~~


# ***Manipula elementos del DOM (Renderer2) -- EJEMPLO***
#### Ejemplo de lo que aprenderás

>Cambia de color
>El botón es de color negro

### Así se resolvería con Vanilla JavaScript
Para resolverlo con JavaScript obtendríamos el elemento del DOM con uno de los métodos que ofrece el objeto global document como por ejemplo getElementById('id del elemento').

HTML
~~~
<button (click)="changeColor()" id="myButton">
  <mat-icon>palette</mat-icon> Cambia de color
</button>      
<p id="myText">El botón es de color negro</p>
~~~
TS
~~~

  public changeColor() {
    const buttonElement: HTMLElement = document.getElementById('myButton');
    const textElement: HTMLElement = document.getElementById('myText');
    const currentColor = buttonElement.style.backgroundColor;
    if (currentColor === 'yellow') {
      buttonElement.style.backgroundColor = 'black';
      buttonElement.style.color = 'white';
      textElement.textContent = 'El botón es de color negro';
    } else {
      buttonElement.style.backgroundColor = 'yellow';
      buttonElement.style.color = 'black';
      textElement.textContent = 'El botón es de color amarillo';
    }
  }
 ~~~ 
### ¿Por qué debo evitar los métodos de document?
Usar los métodos facilitados por el objeto global document no es lo recomendable para manipular los elementos del DOM si estás usando Angular porque:

Angular mantiene el Componente y la vista sincronizados usando plantillas, vinculación de datos y detección de cambios, etc. Todos ellos se omiten cuando actualizamos el DOM directamente
La manipulación de DOM solo funciona en el navegador. No podrá usar la aplicación en otras plataformas, como en un service worker, en un servidor (SSR con Angular Universal por ejemplo), en un escritorio, en la aplicación móvil, etc., donde no hay un navegador.
Las API DOM no desinfectan los datos. Por lo tanto, es posible inyectar un script, lo que abre nuestra aplicación como un blanco fácil para el ataque de inyección XSS.
Como recomienda el equipo de Angular
El equipo de Angular recomienda manipular los objetos del DOM con la clase Renderer2👈

### Usando Renderer2

- Asignaremos un alias a cada elemento del HTML al que querramos acceder desde el componente de TypeScript con el símbolo de numeral o hash (#) delante del alias


<button
  color="primary"
  mat-raised-button
  (click)="changeColor()"
  #myButton
>
  <mat-icon>palette</mat-icon> Cambia de color
</button>
<p #myText>El botón es de color negro</p>

~~~
<button
  color="primary"
  mat-raised-button
  (click)="changeColor()"
  #myButton
>
  <mat-icon>palette</mat-icon> Cambia de color
</button>
<p #myText>El botón es de color negro</p>
~~~

- Con el decorador ViewChild cargamos el elementos del DOM con el alias especificado y le asignamos el tipo ElementRef:

ViewChild se referencia desde @angular/core

~~~
  @ViewChild('myButton')myButtonInTS!:ElementRef;
  @ViewChild('myText')myTextInTS!:ElementRef;
 ~~~ 
- Inyectamos en nuestro constructor el Renderer2

`constructor(private renderer2:Renderer2)`

En la función que cambia el color hacemos uso del Renderer2 usando el método setStyle para cambiar los estilos del botón y usamos el método setProperty para modificar el texto del párrafo.

~~~
  public changeColor() {
    const myButton=this.myButtonInTS.nativeElement;
    const myText=this.myTextInTS.nativeElement; 
    
    if (this.isBlack) {
      this.renderer2.setStyle(myButton, 'backgroundColor', 'yellow');
      this.renderer2.setStyle(myButton, 'color', 'black');      
      this.renderer2.setProperty(myText, 'innerHTML', "El botón es de color amarillo"); 
    } else {
      this.renderer2.setStyle(myButton, 'backgroundColor', 'black');
      this.renderer2.setStyle(myButton, 'color', 'white');
      this.renderer2.setProperty(myText, 'innerHTML', "El botón es de color negro"); 
    }
    this.isBlack=!this.isBlack;
  }
 ~~~

- Cambiando la altura relativa de un elemento

~~~
@ViewChild('myDiv')myDivInTS!:ElementRef;
private initialHeight:number;  

constructor(private renderer2:Renderer2){}

ngAfterViewInit(){
  this.initialHeight=this.myDivInTS.nativeElement.offsetHeight;
}

changeHeight(){
  const _myDiv=this.myDivInTS.nativeElement;   
  
  //aumento en 40px la altura inicial del div
  this.renderer2.setStyle(_screen, 'height', String(this.initialHeight+40)+'px');
}     
~~~     
        
>Precaución
> 🚩 Ten en cuenta que la asignación de la relación entre el html y el ts se hace justo antes del ngAfterViewInit, así que no puedes hacer uso de los elementos view child ni en el constructor ni en el ngOnInit.


# **Forms**
En Angular, el módulo ReactiveFormsModule proporciona una variedad de validadores que puedes usar para validar los campos de un formulario. Estos validadores se pueden aplicar tanto en la creación del formulario como en la validación dinámica mientras el usuario interactúa con el formulario. Los validadores se definen usando funciones de fábrica que se importan del módulo @angular/forms.

Aquí tienes una lista de algunos de los validadores más comunes y los valores que devuelven:

Validators.required:
Este validador se utiliza para verificar si un campo está vacío o no.

Valor devuelto:

Si el campo está vacío, el validador devuelve un objeto que indica el error: { required: true }.
Si el campo no está vacío, el validador no devuelve ningún error.
Validators.minLength(min: number):
Verifica que el valor de un campo tenga al menos min caracteres.

Valor devuelto:

Si el valor tiene menos de min caracteres, el validador devuelve un objeto que indica el error: { minlength: { requiredLength: min, actualLength: value.length } }.
Si el valor tiene al menos min caracteres, el validador no devuelve ningún error.
Validators.maxLength(max: number):
Verifica que el valor de un campo no tenga más de max caracteres.

Valor devuelto:

Si el valor tiene más de max caracteres, el validador devuelve un objeto que indica el error: { maxlength: { requiredLength: max, actualLength: value.length } }.
Si el valor tiene como máximo max caracteres, el validador no devuelve ningún error.
Validators.pattern(pattern: string | RegExp):
Verifica si el valor de un campo coincide con un patrón de expresión regular dado.

Valor devuelto:

Si el valor no coincide con el patrón, el validador devuelve un objeto que indica el error: { pattern: { actualValue: value, requiredPattern: pattern } }.
Si el valor coincide con el patrón, el validador no devuelve ningún error.
Validators.email:
Verifica si el valor de un campo es una dirección de correo electrónico válida.

Valor devuelto:

Si el valor no es una dirección de correo electrónico válida, el validador devuelve un objeto que indica el error: { email: true }.
Si el valor es una dirección de correo electrónico válida, el validador no devuelve ningún error.
Estos son solo algunos ejemplos de los validadores disponibles en Angular. Puedes combinar estos validadores para crear reglas de validación más complejas y personalizadas. Cuando el formulario se presenta con errores, Angular agrega clases CSS especiales a los elementos correspondientes, lo que te permite aplicar estilos de acuerdo a los errores de validación.

Recuerda que puedes acceder a los errores de validación específicos usando el método get del FormGroup y verificando las propiedades errors y touched en los controles del formulario.


# **How to deploy Angular Apps to GitHub Pages (gh-pages)**

> Author Sourse [https://medium.com/tech-insights/how-to-deploy-angular-apps-to-github-pages-gh-pages-896c4e10f9b4]

## ***Method 1***
Below is the first method for deploying an Angular App to Github pages.

- Step 1
Create your Github Repository:

The first thing to do if you want to deploy your Angular App on Github pages is to create a repo for your project.

After creating the repo, commit all your changes and push your project files to the repository you have created.

-Step 2
Install Angular CLI gh-pages:

There is a tool at your disposal that you can use to easily deploy your angular app to gh-pages, the angular-cli-pages tool.

The angular-cli-pages tool is used as a command on the angular CLI for the purpose of deployment. To install it, let us run this command on our terminal:

`$ npm i angular-cli-ghpages --save-dev`

> Note: This command will install angular-cli-ghpages globally in your operating system. You don’t have to install it again in case you need to use it in the future.

- Step 4
Deploy to gh-pages:

After building the App, you can now deploy it to Github Pages using the angular-cli-ghpages tool.

Run the command below in your terminal to deploy the App:


`$ ng deploy --base-href=/angular-app/`
> Note: Make sure you put the name of the project in the place of “angular-app” in the command above.

You can find this in the angular.json file under defaultProject which is at the bottom of the file. If the project name is wrong, your App will not work; so if you are seeing any errors, check the angular.json to confirm if you used the correct project name.

-  Step 6
Visit the App Page:

Visit the URL to your App gh-pages, it is the same URL you created earlier on our terminal; https://GithubUserName.github.io/GithubRepoName/

You should see your application running remotely, which means it has successfully been published on gh-pages.



# **Lazy Loading**

# Different Loading Strategies in Angular

In Angular, various strategies exist for loading modules, each with its own benefits and use cases. Let's explore these strategies along with examples:

## 1. Eager Loading

Eager loading is the default method in Angular, where modules are loaded when the main application starts. All code from these modules is included in the main bundle, impacting the initial load time. This is suitable for small or commonly used modules.

```typescript
import { ProductsModule } from './products/products.module';

@NgModule({
  imports: [
    ProductsModule, // Eager loading
    // ...
  ],
  // ...
})
export class AppModule { }
```

## 2. Lazy Loading

Lazy loading loads modules only when needed, typically when a user navigates to a specific route. This reduces the initial load time and improves performance. Lazy-loaded modules are packaged into separate bundles and loaded on-demand.

```typescript
const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'products', loadChildren: () => import('./products/products.module').then(m => m.ProductsModule) },
  // ...
];
```

## 3. Preloading Strategies

Preloading strategies determine how lazy-loaded modules load in the background after the main content loads. Two common preloading strategies are:

### PreloadAllModules Strategy

Preloads all lazy-loaded modules after the main content loads, improving navigation speed.

```typescript
@NgModule({
  imports: [
    RouterModule.forRoot(routes, { preloadingStrategy: PreloadAllModules }),
    // ...
  ],
  // ...
})
export class AppRoutingModule { }
```

### Custom Preloading Strategy

Create a custom preloading strategy to selectively preload specific modules based on your application’s needs.

```typescript
export class SelectivePreloadingStrategy implements PreloadingStrategy {
  preload(route: Route, load: () => Observable<any>): Observable<any> {
    return route.data && route.data.preload ? load() : of(null);
  }
}

@NgModule({
  imports: [
    RouterModule.forRoot(routes, {
      preloadingStrategy: SelectivePreloadingStrategy, // Custom strategy
    }),
    // ...
  ],
  // ...
})
export class AppRoutingModule { }
```

## Understanding Lazy Loading

Lazy loading is a design pattern that defers the loading of non-essential resources until they are needed. It significantly enhances the initial loading time of a web application, improving the overall user experience.

### Benefits of Lazy Loading

1. **Faster Initial Loading:** Reduces the time for users to start interacting with the application.
2. **Reduced Data Usage:** Downloads fewer resources, crucial for mobile users.
3. **Optimized Performance:** Helps avoid rendering bottlenecks for smoother operation.
4. **Improved SEO:** Prioritizes loading essential content for search engine crawlers.

## Implementation in Angular

Angular provides built-in support for lazy loading through its routing module. Follow these steps:

### Step 1: Setup Routes

Define routes in `app-routing.module.ts` and specify the module to load lazily.

```typescript
const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'lazy', loadChildren: () => import('./lazy/lazy.module').then(m => m.LazyModule) },
  { path: '**', component: NotFoundComponent },
];
```

### Step 2: Create a Lazy Module

Create a separate module for the component(s) to load lazily.

### Step 3: Routing within Lazy Module

Inside the lazy module, define its own routing similarly to the main app routing.

```typescript
const routes: Routes = [
  { path: '', component: LazyComponent },
];
```

### Step 4: Use Lazy Components

Use the lazy-loaded components within your application; Angular loads them only when respective routes are accessed.

## Best Practices

To maximize lazy loading benefits, follow these best practices:

1. **Module Organization:** Create separate modules for features intended for lazy loading.
2. **Route Configuration:** Define lazy-loaded modules in the `app-routing.module.ts` file.
3. **Shared Modules:** Be cautious with shared modules in lazy-loaded modules; create feature-specific shared modules if needed.
4. **Preloading:** Implement preloading to load some lazy-loaded modules in the background.
5. **Lazy Loading Guards:** Implement guards for lazy-loaded routes.
6. **Avoid Over-Lazy Loading:** Only lazy load modules that truly need it.
7. **Testing:** Write tests for lazy-loaded components using Angular testing tools.
8. **Monitoring and Performance Analysis:** Use tools like Lighthouse or Chrome DevTools for performance analysis.
9. **Documentation and Collaboration:** Document your lazy loading strategy for team awareness.

## Conclusion

Lazy loading is a powerful technique for optimizing web application performance and user experience. By loading only necessary components when needed, developers can significantly reduce initial loading times, providing a smoother interaction for users. Angular's built-in routing module makes implementing lazy loading straightforward.

Incorporate lazy loading into your Angular projects today to witness tangible benefits in application performance and user satisfaction.

# **Optimize the Bundle Size**

## **Optimize the Bundle Size with Bundle Analyzer**
>For other frameworks (works for Angular as well)
>https://www.npmjs.com/package/webpack-bundle-analyzer


## **Optimize the Bundle Size using Source Map Explorer**

> Recommended for Angular
> src: https://mohammedfahimullah.medium.com/optimize-the-bundle-size-using-source-map-explorer-5e848850e578

## Why?

Modern web applications often rely on various third-party libraries, contributing to larger bundle sizes. This can impact the initial loading time of the application. To enhance performance, it's essential to reduce the bundle size.

## Tools

There are several tools available for analyzing bundle size. In this article, we'll focus on one of them:

1. **Source Map Explorer**

2. Webpack Bundle Analyzer

We'll explore how to analyze bundle size using **Source Map Explorer**.

## What is Source Map Explorer?

Source Map Explorer determines the origin of each byte in your minified code, providing a treemap visualization to help debug code origins.

## Why Source Map Explorer?

- Recommended by the Google Team.
- Widely used with 6 lakh weekly downloads.

## Prerequisites

Before diving into optimization, let's understand some basic concepts.

### Generated Files after Build

After executing the build command (`ng build --configuration=production`), two different bundles are generated:

1. ES5 Bundle
2. ES2015 Bundle

The ES5 bundle supports legacy browsers, while the ES2015 bundle is for modern browsers.

### Browserlist

A configuration file specifying targeted browsers for application support. It excludes browsers without official support and defines the level of global market share. Differential loading generates ES5 and ES2015 bundles based on browser support.

### Installation of Source Map Explorer

```bash
npm i source-map-explorer --save-dev
```

Add custom scripts to `package.json`:

```json
"scripts": {
  "source-map-analyzer": "ng build --configuration=production && npm run source-map-explorer",
  "source-map-explorer": "source-map-explorer dist/*.js"
}
```

Run the command:

```bash
npm run source-map-analyzer
```

## Bundle Analysis

After running the command, a browser will open, displaying a treemap visualization of generated bundles.

### Before Optimization

![Bundle Representation without Optimization](url_to_image_fig5)

Total Bundle Size: 5.59MB

Observation: External plugins occupy nearly 65% of the application.

## Optimization 1: Browserlist Update

All users of the application use the latest versions of Edge or Chrome. Update the `browserslist` file:

```text
"last 2 Chrome versions",
"last 2 Edge versions",
"not dead",
"not IE 9-11"
```

After updating, no separate ES5 bundle is generated.

### After Optimization 1

![Bundle Representation after Optimization 1](url_to_image_fig8)

Bundle Size: 2.38MB (Reduced from 5.59MB)

## Optimization 2: Removing Unwanted Packages

Remove unwanted packages, such as lottie and Moment JS. Consider alternatives for heavy packages.

### After Optimization 2

![Bundle Representation after Optimization 2](url_to_image_fig9)

Bundle Size: 1.94MB (Reduced from 2.68MB)

## Conclusion

1. Update your `browserslist` file according to the targeted user browsers.
2. Libraries contribute significantly to bundle size. Import packages only if necessary.
3. Add devDependency packages to the `devDependencies` section of `package.json`.
4. Remove unwanted packages.
5. If a package is heavy, find alternatives (e.g., Moment JS).
6. If no differential loading is needed, update your `browserslist.src` file.