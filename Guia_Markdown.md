 <div align="center"> 
 
 # Guia Basica de MarkDown 
 
 [Mark Down Link Guide](https://www.markdownguide.org/basic-syntax/)

 > (keyboard shortcuts, table of contents, auto preview and more)
 [Mark Down All in One Guide](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)</div>


### **MENÚ**

- [Guia Basica de MarkDown](#guia-basica-de-markdown)
    - [**MENÚ**](#menú)
  - [Crear Títulos](#crear-títulos)
- [h1](#h1)
  - [h2](#h2)
    - [h3](#h3)
      - [h4](#h4)
        - [h5](#h5)
          - [h6](#h6)
  - [Textos](#textos)
    - [Negrita](#negrita)
    - [Cursiva](#cursiva)
    - [Combinado](#combinado)
  - [Listas](#listas)
    - [UL](#ul)
    - [OL](#ol)
    - [Combinacion Listas](#combinacion-listas)
  - [Separadores](#separadores)
  - [Citas](#citas)
  - [Bloques de Codigo](#bloques-de-codigo)
  - [Links](#links)
  - [Imágenes](#imágenes)
  - [Símbolos sin formato](#símbolos-sin-formato)
  - [Combinar con HTML](#combinar-con-html)
  - [Emoji](#emoji)

## Crear Títulos 

'#'

# h1
## h2
### h3
#### h4
##### h5
###### h6

## Textos

### Negrita

'__ __' o '** ** '

__negrita__

**negrita**

Esto **en negrita**, esto no

### Cursiva

'_ _' o '* *'

_cursiva_

*cursiva*

### Combinado

'*** ***'

Esto es ***negrita y cursiva***


## Listas
### UL
' * o - o +'
* Lista
- Lista2
+ Lista3
    + Lista 4

### OL
'Numero y punto ex. '1.''
1. Lista 1
2. Lista 2

### Combinacion Listas
1. Lista 1
    - Lista 1.1
    - Lista 1.2

## Separadores

' ---- o **** '

----
****

## Citas

' > ' y ' >> '
> Esto es una cita
>> y esto es otra cita

## Bloques de Codigo

Usar comillas simple

`print("Hola Mundo")`

usar ~~~  para codigo de mas de una linea
~~~
for chat in text{
    print(char)
}
~~~

## Links

\[\]\(\)

[Mi web](https://moure.dev)

## Imágenes

\!\[\]\(\)

![Mi foto](htttps://link.com)

## Símbolos sin formato 

Anteponer una \ antes del símbolo '\\*'
\* 

## Combinar con HTML

~~~
<table>
    <tr>
        <th>Nombre</th>
        <th>Apellido</th>
        <th>Edad</th>
    </tr>
    <tr>
        <th>Ramon</th>
        <th>Estol</th>
        <th>41</th>
    </tr>
</table>
~~~

<table>
    <tr>
        <th>Nombre</th>
        <th>Apellido</th>
        <th>Edad</th>
    </tr>
    <tr>
        <th>Ramon</th>
        <th>Estol</th>
        <th>41</th>
    </tr>
</table>

## Emoji
 ':nombreemoji:'
 ex.

 `:smile:` :smile:

`:crossed_fingers:`:crossed_fingers:<br>
`:white_check_mark:`:white_check_mark:

`:x:`:x:

## Table of contents
TOC

- Run command "Create Table of Contents" (in the VS Code Command Palette) to insert a new table of contents.

- The TOC is automatically updated on file save by default. To disable, please change the toc.updateOnSave option.

- The indentation type (tab or spaces) of TOC can be configured per file. Find the setting in the right bottom corner of VS Code's status bar.

Note: Be sure to also check the list.indentationSize option.

- To make TOC compatible with GitHub or GitLab, set option slugifyMode accordingly

> Three ways to control which headings are present in the TOC:


>1. Add <!-- omit from toc --> at the end of a heading to ignore it in TOC
(It can also be placed above a heading)

>2. Use toc.levels setting.

>3. You can also use the toc.omittedFromToc setting to omit some headings (and their subheadings) from TOC:

~~~
// In your settings.json
"markdown.extension.toc.omittedFromToc": {
  // Use a path relative to your workspace.
  "README.md": [
      "# Introduction",
      "## Also omitted",
  ],
  // Or an absolute path for standalone files.
  "/home/foo/Documents/todo-list.md": [
    "## Shame list (I'll never do these)",
  ]
}
~~~
Note:

- Setext headings (underlined with === or ---) can also be omitted, just put their # and ## versions in the setting, respectively.
  
- When omitting heading, make sure headings within a document are unique. Duplicate headings may lead to unpredictable behavior.
