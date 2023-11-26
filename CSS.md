 <div style="text-align: center"> 
 
 # ***APUNTES CSS***
 
 ### *MENÚ*</div>

 - [Metodología BEM](#metodología-bem)
 - [EM y REM](#em-y-rem)
 - [Breakpoints](#breakpoints)
 - [Media Queries](#media-queries)

Of course, I'll include information about the bugs and essential concepts, along with concise examples of key properties:

## **CSS Flexbox Essentials:**
- **Introduction:** Flexbox simplifies complex layouts and provides flexible alignment and space distribution within a container.

- **Benefits:** Easier alignment and responsive layouts, reordering elements, and creating same-height columns.

- **Main Axis and Cross Axis:** Flex containers have a main axis and cross axis defined by the flex-direction property.

- **Flex Containers and Flex Items:** Set display to flex or inline-flex to create flex containers, with direct children becoming flex items.

### **Key Flex Container Properties:**

- **flex-direction:** Defines the main axis direction (row, column, row-reverse, column-reverse).

   Example: `flex-direction: column;`

- **flex-wrap:** Controls whether items wrap when space is insufficient (wrap, nowrap, wrap-reverse).

   Example: `flex-wrap: wrap;`

- **justify-content:** Aligns items along the main axis (flex-start, flex-end, center, space-between, space-around, space-evenly).

   Example: `justify-content: center;`

- **align-items:** Aligns items along the cross axis (stretch, flex-start, flex-end, center, baseline).

   Example: `align-items: center;`

- **align-content:** Aligns flex lines along the cross axis in a multi-line container.

   Example: `align-content: space-between;`

### **Key Flex Item Properties:**

- **order:** Changes the order of appearance for items based on a numerical value.

   Example: `order: 2;`

- **flex-grow:** Determines how items grow to occupy extra space (a number value).

   Example: `flex-grow: 2;`

- **flex-shrink:** Controls how items shrink when space is insufficient (a number value).

   Example: `flex-shrink: 0;`

- **flex-basis:** Sets the default size of an item (a length value).

   Example: `flex-basis: 50px;`

- **flex:** A shorthand property for flex-grow, flex-shrink, and flex-basis.

   Example: `flex: 2 0 50px;`

**Centering with Flexbox:**
- To center an element, make the parent element a flex container and set `justify-content` and `align-items` to `center`.

**Flexbox Gaps:**
- Use the `gap` property to adjust space between flex items, which can take two values for rows and columns separately.

   Example: `gap: 10px 20px;`

### **CSS Flexbox Bugs:**
- A common example is that some HTML elements cannot act as flex containers. These include the `<button>, <fieldset>, and <summary>`` elements.

>The workaround is to use an element like a div to wrap around the element's children. Then use Flexbox on the wrapper div.

- Workarounds are available, and known bugs can be found in the [Flexbugs repository on GitHub](https://github.com/philipwalton/flexbugs)

>[CSS FLEX extended guide](https://www.freecodecamp.org/news/the-css-flexbox-handbook/#are-there-bugs-in-css-flexbox)


## **Metodología BEM en CSS**

BEM CSS es una metodología de nomenclatura, consiste en nombrar las clases de los nodos de tu HTML para después atacarlos con CSS de manera cómoda.

### **Selectores en CSS sin BEM**

- Lo normal seria usar esto
  
~~~
section.informacion{}
section.informacion article{}
section.informacion article h2{}
section.informacion article p{}
section.informacion article p.inactive{
        display: none;
    }
~~~



### **Selectores en CSS con BEM**
> BEM =>  Bloque, Elemento, Modificador

El nombre debería ser bloque__elemento--Modificador
~~~
.informacion{}
.informacion__article{}
.informacion__h2{}
.informacion__p{}
.informacion__p--inactive{
    display: none;
}
~~~

Así quedaría anidado y con `&`
~~~
.informacion{
  &__article{}
  &__h2{}
  &__p{}
  &__p--inactive{
    display: none;
  }
}
~~~


## **EM y REM**

> <p style="text-align:center; color:red">--- NUNCA USAR PX !!! ---</p>

- Em y REM son medidas relativas
- REM es relativa a la etiqueta `<html>`
- EM es relativa a su `<etiqueta> <contenedora>, <body> y <htmL>`
- Por DEFAULT  el de HTML y BODY es font-size:16px
- Si ponemos 

`html{ font-sizew:100%}` = 16px si el usuario no lo configura

`html{ font-sizew:1em}` = también vale 16px si el usuario no lo configura

EL problema con REM es que si el usuario cambia el `<body>` o en otra etiqueta y no el `<html>` donde usemos REM no cambiara,
por eso es mejor usar EM para a el font-size.

Y para cajas si no quieres complicarte usa REM para padding,margin,border-radius

- !Para el border si que se puede usar PX!

> [Vídeo explicativo](https://www.youtube.com/watch?v=YglSzse9tEo&t=340s)


 #### Truco para no estar calculando el EM y el REM:
  
  Usar la extension PX to REM => introduce en px y  pulsa ALT+Z
  

## **Breakpoints**

Los breakpoints se usan en:
- HTML: en el atributo media=""
- CSS: en la regla @media: las [mediaQueries](#media-queries)
  
### **Breakpoints de resolución**

#### **Breakpoints básicos**

Esto es más o menos los standard:
- Movil : 0 a 480px
- Tablet : 480 a 960px
- Ordenador: 960 a 1328px

#### **Breakpoints completos**

Esto es mas útil para definir móviles muy pequeños o tablets de diferentes tamaños.

A los anteriores hay que añadir breakpoints en 320px, 768px y 1024px, quedaría así:
- Movil mini : 0 a 320px
- Movil : 320 a 480px
- Tablet en vertical: 480 a 768px
- Tablet en horizontal : 768px a 960px
- Ordenador portátil: 960 a 1024px
- Ordenador: 1024 a 1328px

#### **Breakpoints personalizados**

Depende de nuestro propio diseño/maquetación

> Revisa Google Analytics para saber los usuarios finales que usan 

### **Breakpoints de dispositivo**

Son los breakpoints que tienen en cuenta el comportamiento propio del dispositivo:
- Orientación
- Modo OScuro
- Pantalla o Impresión (ya casi no se usa)


## Media Queries

La Media Query es una declaración en CSS (una palabra reservada), que nos permite definir mediante los breakpoints en que px las propiedades de un elemento van a cambiar.

No existe una si no muchas.

**Sintaxis en CSS:**
- Palabra reservada `@media`
- Media type `screen` (antes existían más como `print`,`braile`, pero están obsoletos)
- Operadores `and|or|not`
- Breakpoints `max-width:480px`
  
  `@media screen and (max-width:480px){}`

> - Colocar siempre al final del archivo CSS
 - Deben de tener el mismo selector
 - Pensar bien los Breakpoints
 - Usar alguna metodología como BEM

 **Sintaxis en HTML:**

 Se usa en forma de atributo en etiquetas como:
 - `<link>` ya no se recomienda
 - `<style>` tampoco se recomienda
 - `<picture>`

    ~~~
    <picture>
    <source srset="imagenMovil.jpg" media="screen and (max-width:480px)>
    <img src="imagenPC.jpg"alt="imagen">
    </picture>
    ~~~

- `<meta>` la más importante para que todo funcione, se usa dentro del `<header>`
  ~~~
  < meta name="viewport" content="width=device-width, initial-scale=1.0" />
  ~~~

### ***Orientación***
`@media screen and (orientation:landscape){`

  ` .elemento{ color: gray; `
  
`}`

### ***Dark Mode***

`@media screen and (prefers-color-scheme:dark){`

  ` .elemento{ color: gray; `
  
`}`
  > ### ***Trucos para Responsive***

  > No usar las alturas (solamente min_heigh si es necesario)
  > Usa siempre medidas en porcentajes vw,vh,em
  > Calcular bien los anchos usando calc() o margin
  > Usar flex o grid siempre que sea posible
  > Tener un buen RESET de CSS




