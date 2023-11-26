<div align="center">

    # APUNTES SASS

</div>

### MENÚ

- [MENÚ](#menú)
- [COMPILADO](#compilado)
- [VARIABLES](#variables)
- [MIXIN](#mixin)
  - [TIPOS DE MIXIN](#tipos-de-mixin)
  - [Mixin sin argumentos](#mixin-sin-argumentos)
  - [Mixin con argumentos](#mixin-con-argumentos)
  - [Mixin con la regla @content](#mixin-con-la-regla-content)
  - [**Los nombres de los archivos y/o carpetas que usaríamos son:**](#los-nombres-de-los-archivos-yo-carpetas-que-usaríamos-son)


### COMPILADO

  SASS es un lenguaje que se compila a CSS, pero necesitas herramientas para compilar SASS

Puedes usar:

    - Consola con NODEJS
    - Sistemas de Bundling como Webpack
    - Sistemas de Task Runner como Grunt
    - APP como Prepros
    - Extensiones de VSC como Live Sass Compiler

### VARIABLES

> Es mejor usar snake-case 

Se definen con $ ,  ej 
~~~
$negro: black;
a{
    color:$negro;
}
p{
    background-color: $negro;
}
~~~

Si tenemos muchas variables es mejor usar un array,
para eso usaremos map-get(), ej
~~~
$colores:{
    "negro": black,
    "blanco": white,
};

$fuentes :{
    "normal":Verdana,
    "titulo":Helvetica
};

header{
    color: map-get($colores,"negro" );
    font-fanily: map-get($fuentes , "normal");
}

h1{
    color: map-get($colores,"blanco" );
    font-fanily: map-get($fuentes , "Helvetica");}
~~~

### MIXIN

Mixin es una función que nos ahorrar lineas de código y pueden usar:

- Argumentos
- @content
  
Diferencias entre SASS y SCSS:
- En SASS no se usa ni ; ni {}, se usan tabuladores
- En SCSS se usa igual ; y {} que en CSS

#### TIPOS DE MIXIN

- Mixin sin argumentos
- Mixin con argumentos:
  - 1 argumento
  - más de un argumento
  - argumento con valor por defecto
- Mixin con la regla @content
- Mixin para flex
- Mixin para grid
- Mixin para Responsive DEsign
- Mixin propio


#### Mixin sin argumentos

 - Creamos con @mixin
 - Lo usamos con @include
 - Si no usamos argumentos(variables) podemos no poner los ()
~~~

//Creamos
@mixin nombreMixin(){
    background: black;
}
//Usamos
header{
    @include nombreMixin(); //Usamos el Mixin con paréntesis
}

//Sin paréntesis tendría que ser así

@mixin nombreMixin{
    background: black;
}
//Usamos
header{
    @include nombreMixin; //Usamos el Mixin con paréntesis
}
~~~

#### Mixin con argumentos


- Siempre necesitamos los paréntesis 
- Los argumentos son como las variables

~~~
//Con un argumetno

@mixin nombreMixin($argumento1){
    background: $argumento1;
}

//Usamos
header{
    @include nombreMixin(black); 
}

//Otra forma es así

@mixin nombreMixin($argumento1 : red){ //Por defecto sera red
    background: $argumento1;
}

//Usamos
header{
    @include nombreMixin(); //usaría el valor del argumento por defecto en este caso 'red'

    @include nombreMixin(black); //usaría el valor que introducimos 'black'
}

~~~

~~~
//Con más de un argumento

@mixin nombreMixin($argumento1, argumento2 , argumento3){
    font-weight: $argumento1;
    color: $argumento2;
    Font-size: $argumento3;
}

//Usamos
header{
    @include nombreMixin(bold, white, 2em); 
}
~~~

#### Mixin con la regla @content

- Nos deja introducir multiples propiedades CSS dentro de un Mixin
- Muy usado para Responsive Design
  
  ~~~
  @mixin movil(){
    @media screen and (max-width:480px){
        @content;
    }
  }

  p{
    font-size: 4em;
    @include movil(){
        font-size: 2em;
    }
  }

#### Mixin Muy Útiles

##### **FLEX**

~~~
@mixin flexible($dis,$direction,$corte,$just,$align){
    display: $dis; 
    flex-flow: $direction $corte;
    justify-content: $just;
    align-items: $align;
}

main {
    @include flexible(flex, row, nowrap, center, center);
}
section {
    @include flexible(flex, column, nowrap, flex-start, flex-start);
}
~~~

#### **GRID**

~~~
@mixin grid( $columnas, $espacio){
    display: grid; 
    grid-template-column: repeat( $columnas, 1fr);
    gap: $espacio;

    @media screen and (max-width:480px){
        grid-template-column: 1fr;
        gap: 0em;
    }
}

main {
    @include grid(4, 1em);
}
section {
    @include grid(3, 2em);
}
~~~

#### **RESPONSIVE DESIGN**

~~~
@mixin mediaMovil($medida: 480px){
     @media screen and (max-width:medida){
        @content;
     }
}

article{
    width:25%;
    @include mediaMovil(768px){width:50%}
    @include mediaMovil(){width:100%}
}
~~~
#### Mixin Propios

~~~
@mixin neoformismo($radius, $eje){
    border-redius:$radius;
    background: #e0e0e0;
    box-shadow: $eje $eje ($eje*2) #bebebe, (-$eje)(-$eje)($eje*2) #ffffff;
}

article{
    @include neo(50px , 21px);
}

section{
    @include neo(20px,10px);
}
~~~

### Nesting (Anidación)

- En CSS haríamos esto
    ~~~
    header{
        color: black;
    }
    header h1{
        color: red;
    }
    header nav{
        @include flex();
    }
    ~~~
- En SCSS lo haríamos así
    ~~~
    header{
        color: black;
        h1{
            color: red;
        }
        nav{
            @include flex();
        }
    }
    ~~~

Además en SCSS tenemos el uso del `&`, que añade al selector padre

- En CSS:
    ~~~
    a{
        color:black;
    }
    a:hover{
        color:red;
    }
    a:active{
        color:aquA;
    }
    a:visited{
        color:pink;
    }
    ~~~
- Como funciona `&` en  SCSS
    ~~~
    a{
        color:black;

        &:hover{color:red}
        &:active{color:aquA;}
        &:visited{color:pink;}
    }

Aquí es donde toma más sentido la metodología BEM para poner nombre a las clases.

    ~~~
    header{
        color: black;
        &__h1{
            color: red;
        }
        &__nav{
            @include flex();
        }
    }
    ~~~

### **Metodología BEM en CSS**

BEM CSS es una metodología de nomenclatura, consiste en nombrar las clases de los nodos de tu HTML para después atacarlos con CSS de manera cómoda.

#### **Selectores en CSS sin BEM**

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

#### **Selectores en CSS con BEM**
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

> USAR BEM HELPER extensión que te crea directamente desde el HTML un archivo scss con todos los selectores

#### **Arquitectura OCSS**

Los principios son:

##### ***1. Estructura y piel separadas:***
   
Casi todos los elementos en una página web con estilo tienen diferentes características visuales que se repiten en diferentes contextos y (los colores, degradados o los bordes visibles). Por otro lado, también se repiten otras características generalmente invisibles (es decir, “estructura”).

Cuando estas características diferentes se abstraen en módulos basados ​​en clases, se vuelven reutilizables y se pueden aplicar a cualquier elemento y tienen el mismo resultado básico.

Antes de aplicar los principios de OOCSS, puede tener CSS que se ve así:

~~~
#button {
  width: 200px;
  height: 50px;
  padding: 10px;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#box {
  width: 400px;
  overflow: hidden;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
~~~

Los tres elementos anteriores tienen estilos que son únicos para cada uno y se aplican con el selector de ID no reutilizable para definir los estilos. Pero también tienen varios estilos en común. Los estilos comunes pueden existir para fines de marca o consistencia de diseño.

Con un poco de planificación y previsión, podemos abstraer los estilos comunes para que el CSS termine así:

~~~
.button {
  width: 200px;
  height: 50px;
}

.box {
  width: 400px;
  overflow: hidden;
}

.widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
}

.skin {
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
~~~
Ahora todos los elementos están usando clases, los estilos comunes se combinan en una “máscara” reutilizable y nada se repite innecesariamente. Solo tenemos que aplicar la clase “skin” a todos los elementos y el resultado será el mismo que el que produciría el primer ejemplo, excepto con menos código y una posibilidad de reutilización adicional . separar la estructura de la piel y separar el contenedor del contenido.

2. Contenedor separado y contenido
El segundo principio descrito en la página wiki OOCSS GitHub es la separación de los contenedores de su contenido. Para ilustrar por qué esto es importante, tome el siguiente CSS:
~~~
#sidebar h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: .8em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}
~~~
Estos estilos se aplicarán a cualquier encabezado de tercer nivel que sea hijo del #sidebarelemento. Pero, ¿qué sucede si queremos aplicar exactamente los mismos estilos a los títulos de tercer nivel que aparecen en el pie de página, con la excepción de un tamaño de fuente diferente y una sombra de texto modificada?

Entonces tendríamos que hacer algo como esto:
~~~
#sidebar h3, #footer h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 2em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

#footer h3 {
  font-size: 1.5em;
  text-shadow: rgba(0, 0, 0, .3) 2px 2px 4px;
}
~~~
O podríamos terminar con algo peor:
~~~
#sidebar h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 2em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

/* other styles here.... */

#footer h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 2px 2px 4px;
}
~~~

Ahora estamos duplicando estilos innecesariamente , y es posible que no nos demos cuenta (o simplemente no nos importe). Con OOCSS, se nos recomienda que prestemos más atención a lo que es común entre los diferentes elementos, luego separemos esas características comunes en módulos u objetos, que se pueden reutilizar en cualquier lugar.

Los estilos que se declaran utilizando el selector descendente en los ejemplos anteriores no son reutilizables , ya que dependen de un contenedor particular (en este caso, la barra lateral o el pie de página).

Cuando usamos la construcción de módulos basados ​​en clases de OOCSS, nos aseguramos de que nuestros estilos no dependan de ningún elemento contenedor. Esto significa que pueden reutilizarse en cualquier parte del documento, independientemente del contexto estructural.

En OCSS se puede organizar solamente con múltiples archivos de etilo o usando diferentes carpetas que contienen los nombres de las clases.

- - - - 

#### **Los nombres de los archivos y/o carpetas que usaríamos son:**
- styles: donde importamos todos los archivos de estilo
- _base: con el reset de CSS
- _layout: Grid,Flex,wrappers..(~mixin)
- _modules: estilos de los objetos o módulo(~bloques/contenedora)
- _shame: donde ponemos los arreglos de CSS que necesitamos hacer(~!important)

