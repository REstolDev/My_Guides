 <div style="text-align: center">

# **_Programación en PHP_**

### _MENÚ_</div>

- [**_Programación en PHP_**](#programación-en-php)
    - [_MENÚ_](#menú)
  - [**Introducción**](#introducción)
    - [_Imprimir por pantalla_](#imprimir-por-pantalla)
      - [**ECHO** para imprimir en pantalla](#echo-para-imprimir-en-pantalla)
  - [**Comentarios de código**](#comentarios-de-código)
  - [**Variables**](#variables)
    - [**Tipos de Datos**](#tipos-de-datos)
    - [**Otras curiosidades las variables**](#otras-curiosidades-las-variables)
      - [_Para la terminal_](#para-la-terminal)
  - [**Constantes**](#constantes)
    - [**Constantes predefinidas**](#constantes-predefinidas)
  - [**Operadores**](#operadores)
    - [_Aritméticos_](#aritméticos)
    - [_Incremento y decremento_](#incremento-y-decremento)
    - [_Asignación_](#asignación)
  - [**Variables globales**](#variables-globales)
    - [_Variables de servidor_](#variables-de-servidor)
    - [_Variable GET_](#variable-get)
    - [_Variable POST_](#variable-post)
  - [**Estructuras de Control**](#estructuras-de-control)
    - [_Condicionales_](#condicionales)
      - [_Operadores de comparación_](#operadores-de-comparación)
      - [_Operadores lógicos_](#operadores-lógicos)
      - [_Operador GOTO_](#operador-goto)
    - [**Bucles**](#bucles)
  - [**Funciones**](#funciones)
    - [_Funciones con Argumentos/Parametros_](#funciones-con-argumentosparametros)
    - [_Funciones con Parametros Opcionales_](#funciones-con-parametros-opcionales)
    - [_Funciones variables_](#funciones-variables)
    - [_Funciones predefinidas_](#funciones-predefinidas)
    - [_RETURN_ /Buenas prácticas](#return-buenas-prácticas)
  - [**Variables**](#variables-1)
    - [_Globales_](#globales)
    - [_Locales_](#locales)
  - [**Includes**](#includes)
    - [*include\_once*](#include_once)
    - [_require_ o *require\_once*](#require-o-require_once)

## **Introducción**

Encapsulamos nuestro codigo en las etiquetas
`<?php  'Codigo' ?>`
No hay límite de cantidad de etiquetas dentro del archivo.

### _Imprimir por pantalla_

#### **ECHO** para imprimir en pantalla

_Concatenación_
Usamos el `.` para concatenar

```
 <?php
   echo '<h3>Listado de videojuegos:</h3>';
   echo'<ul>'
       .'<li>GTA</li>'
       .'<li>Fifa</li>'
       .'<li>Mario Bros</li>'
       .'</ul>';

   echo '<p>Esta es toda'.' - '.'lista de juegos</p>';

   ?>
```

> _TIP_ - Usar comillas simples en la medida que sea posible para utilizar menos recursos.
> _Sintaxis abreviada_ - `<?='Sintaxis abreviada de echo'?>`

## **Comentarios de código**

`//Esto es un comentario en php`

```
/* Esto es un comentarios de
varias líneas*/
```

## **Variables**

Una variable es un contenedor de información donde puedo guardar cualquier dato dentro de ella.

```
$variable_titulo = 'Mi titulo string';
$numero = 44;
$verdadero = true;
```

Signo `$` para identificar que es una variable
`=` para asignar el valor

```
<?php

    $mi_primera_variable = 'Hola Mundo desde una variable';
    echo '<h3>VARIABLES:</h3>';
    echo '<h1>'.$mi_primera_variable.'</h1>';
        //Usamos '.' para concatenar

    echo $mi_primera_variable;
    echo 'Sin concatenar';

    echo '<p>Esta es toda'.' - '.'lista de juegos</p>';

    ?>
```

> Se puede volver a reasignar un valor a las variables

```
<?php
$numero =15;

$numero = 77;
echo $numero ; //imprimirá 77

$numero = 120;
echo $numero ; //imprimirá 120

?>
```

### **Tipos de Datos**

- Entero (int/integer) = 99
- Coma flotante (float/double) = 3.45
- Cadenas de caracteres (string) = 'Esto es una string'
- Booleano (bool) = 1 0 true false
- null
- Array
- Objetos

> Para saber el tipo de dato que tiene una variable se puede usar la función gettype()

`$numero = 100; echo gettype($numero);`

### **Otras curiosidades las variables**

- No se puede empezar una variable con un número
- No se pueden usar tildes ni ñ
- No usar símbolos
- Se pueden usar números en otra posición que no sea la primera

> var_dump() usar esta función para debugear una variable
> `var_dump($numero)`

> se puede usar las comillas dobles `"` para concatenar por ejemplo `$texto="Soy un texto con una variable $numero"`

> usar la barra`\` para mostrar " o '
> `$texto="Soy un texto con comillas \" \'`

#### _Para la terminal_

> Saltos de línea `\n` `$texto="Soy un salto \n de línea`

> Retorno de carro `\r` `$texto="Soy un retorno de carro \r`

## **Constantes**

Un contenedor de información que no puede variar

`define('nombre','Ramon Estol);`

para imprimirla usamos el nombre sin el $
`echo nombre;`
`echo '<h1>'.nombre.'</h1>'`

### **Constantes predefinidas**

Usamos `__nombrefuncion__`

## **Operadores**

### _Aritméticos_

```
<?php
$num1 = 55;
    $num2 = 33;

    echo 'Suma: '.($num1+$num2).'<br>';
    echo 'Resta: '.($num1-$num2).'<br>';
    echo 'Producto: '.($num1*$num2).'<br>';
    echo 'División: '.($num1/$num2).'<br>';
    echo 'Resto :'.($num1%$num2).'<br>';
  ?>
```

### _Incremento y decremento_

```
$year =2019;

    echo 'Year: '.($year).'<br>';

    $year ++;
    echo 'Year++ Incremento: '.($year).'<br>';
    $year --;
    echo 'Year-- Decremento: '.($year).'<br>';
     ++$year;
    echo 'Pre-Incremento ++year: '.($year).'<br>';
    --$year;
    echo 'Pre-Decremento --year: '.($year).'<br>';
```

### _Asignación_

```<?php

    $edad = 42;
    echo 'Edad: '.($edad).'<br>';
    echo 'Edad +=: '.($edad+=5).'<br>';
    echo 'Edad -=: '.($edad-=5).'<br>';
    echo 'Edad /=: '.($edad/=5).'<br>';

    ?>
```

## **Variables globales**

### _Variables de servidor_

Para obtener información del servidor tanto nuestro como del cliente.

```
 <?php
    echo '<h4>$_SERVER'.$_SERVER['SERVER_ADDR'].'</h4>';
    echo '<h4>$_SERVER'.$_SERVER['SERVER_NAME'].'</h4>';
    echo '<h4>$_SERVER'.$_SERVER['SERVER_SOFTWARE'].'</h4>';
    echo '<h4>$_SERVER'.$_SERVER['HTTP_USER_AGENT'].'</h4>';
    echo '<h4>$_SERVER'.$_SERVER['REMOTE_ADDR'].'</h4>';

    ?>
```

### _Variable GET_

Usamos name para asignar el nombre al que accederemos con php y `$_GET['nombreidentificador]` para acceder

```
//form.html

<h2>Formulario en PHP</h2>
<form method="get" action="recibir.php">
<label for="nombre">Nombre:</label>
<input name="nombre" type="text">
<label for="apellidos">Apellidos:</label>
<input name="apellidos" type="text">
<input type="submit" value="Enviar">
</form>

```

````
//recibir.php

<?php
echo  '<h1>'.$_GET['nombre'].'</h1>';
echo  '<h1>'.$_GET['apellidos'].'</h1>';
echo  '<h1>'.var_dump($_GET).'</h1>';
?>```
````

### _Variable POST_

Usamos name para asignar el nombre al que accederemos con php y `$_POST['nombreidentificador]` para acceder

```
<form method="post" action="index.php">
        <label for="nombrePost">Nombre:</label>
        <input name="nombrePost" type="text">
        <label for="apellidosPost">Apellidos:</label>
        <input name="apellidosPost" type="text">
        <input type="submit" value="Enviar">
    </form>

    <?php
    echo '<h1>' . $_POST['nombrePost'] . '</h1>';
    echo '<h1>' . $_POST['apellidosPost'] . '</h1>';
    echo '<h1>' . var_dump($_POST) . '</h1>';
    ?>
```

## **Estructuras de Control**

### _Condicionales_

- IF y ELSE:

  ```
  <?php
  $color ='rojo';

  if($color == 'rojo') echo '<h3>El color es ' . $color . '</h3>';
  else echo '<h3>El color no es ROJO es' . $color . '</h3>';
  ?>

  ```

- ELSE IF:

  ```
   <?php
  $color ='negro';

  if($color == 'rojo')  echo '<h3>El color es rojo </h3>';
  else if($color == 'verde') echo '<h3>El color es verde </h3>';
  else if($color == 'azul') echo '<h3>El color es azul </h3>';
  else echo'<h3> No es ni rojo , ni verde, ni azul. EL color es: '.$color.'</h3>';
  ?>
  ```

- SWITCH

  ```
  <?php
    $color ='negro';

    switch($color){
     case 'rojo': echo '<h3>El color es rojo </h3>';
     case 'verde': echo '<h3>El color es verde </h3>';
     case 'azul': echo '<h3>El color es azul </h3>';
    default: echo'<h3> No es ni rojo , ni verde, ni azul. EL color es: '.$color.'</h3>';
    }
    ?>
  ```

#### _Operadores de comparación_

- == igual
- === idéntico
- !== no idéntico
- != diferente
- <> diferente
- < menor que
- \> mayor que
- <= menor o igual que
- \>= mayor o igual que

#### _Operadores lógicos_

- && and
- || or
- ! not

#### _Operador GOTO_

Para hacer un saltoalguna parte de la pagina

```
<?php
        if ($color ==='rojo') goto marca;

        echo '<h3>linea1 </h3>';
        echo '<h3>linea2 </h3>';
        echo '<h3>linea3 </h3>';

        marca:
        echo 'Me he saltado hasta la marca'

    ?>
```

### **Bucles**

Es una estrucutra de control que itera la ejecución de una serie de instrucciones tantas veces como sea necesario hasta que se cumple una condición o varias

- WHILE:

  ```
  <?php
   $numero = 0;

   while($numero <= 10){
       echo $numero.' - ';
       $numero++;
   }
   ?>

   echo '<br>';
   // usamos la funcion ISSET para comprobar si existe la variable, devuelve true o null
   if(isset($_GET['num'])) $num = (int)$_GET['num'];
   //usamos (int) para convertir o castear 'casting' o 'cast' a entero
   else $num =1;

   $cont =0 ;
   echo "<h1>Tabla de multiplicar del numero $num pasado por GET </h1> ";
   while($cont <= 10){
       echo "$num * $cont = ". ($num*$cont) . '<br>';
       $cont++;
   }

  ```

- DO WHILE:

```
<?php
    $numero = 0;

    do{
        echo $numero;
        if ($numero != 10) echo ' - ';
        $numero++;
    }while($numero <= 10)

    ?>
```

- FOR:

  ```
   <?php
    $num = 10;

    for($i=0 ; $i<=$num ; $i++){
        echo $i;
        if ($i != 10) echo ' - ';

    }
    ?>
  ```

- BREAK:

  Para salir de la ejecución de un bucle `break;`

## **Funciones**

Conjunto de instrucciones agruopadasbajo un nombre en concreto para que puedan ser reutilizadas invocandolas a través de su nombre `mifuncion()`

```
<?php
    function mostrarNombres(){
        echo 'juan <br>';
        echo 'jose <br> ';
        echo'pepe <br>';
    }

    mostrarNombres();
    ?>
```

### _Funciones con Argumentos/Parametros_

```
<?php
    function calculadora($num1,$num2){
        echo 'sumar : '. ($num1+$num2) . '<br>';
        echo 'restar : '. ($num1-$num2). '<br>';
        echo 'muiltiplicar : '. ($num1*$num2). '<br>';
    }

    calculadora(5,2);
    ?>
```

### _Funciones con Parametros Opcionales_

```
<?php
    function calculadora2($num1,$num2, $bold = false){
        if($bold) echo '<b>';
        echo 'sumar : '. ($num1+$num2) . '<br>';
        echo 'restar : '. ($num1-$num2). '<br>';
        echo 'muiltiplicar : '. ($num1*$num2). '<br><br>';
        if($bold) echo '</b>';
    }

    calculadora2(5,2); //puedo pasarle el parametro o no
    calculadora2(5,2, true);
    calculadora2(5,2, false);


    ?>
```

### _Funciones variables_
```
<?php 
    function buenasDias(){ return 'Hola! Buenos dias';}

    function buenasTardes(){ return "Hola! Buenas tardes";}

    function buenasNoches(){ return "Hola! Hora de dormir";}

    $horario = "buenasNoches";

    echo $horario();


    ?>
```

### _Funciones predefinidas_
Listado de funciones predefinidas [aquí](https://www.php.net/manual/es/indexes.functions.php)

```
 <?php 
    
    echo 'fechas: '. date('d-m-Y') . '<br>';
    echo 'tiempo: '. time(). '<br>';

    echo 'raiz cuadrada de 10: '. sqrt(10). '<br>';
    echo 'numero aleatorio entre 10 y 40: '. rand(10,40). '<br>';
    echo 'numero pi: '. pi(). '<br>';
    echo 'redondear 4.324: '. round(4.324). '<br>';


    echo 'que tipo es "hola": '. gettype('hola'). '<br>';
    echo 'es entero 10: '; if(is_int(10))echo 'true'. '<br>';
    echo 'es entero 10.3: '; if(!is_int(10.3))echo 'false'. '<br>';

    echo 'eliminar espacios por delante y detras con trim " hola ": '. trim(' hola '). '<br>';

    //eliminar variables con unset($nombredelavariable)
    ?>
```
### _RETURN_ /Buenas prácticas

> La buena practica siempre debería ser que una funcion no mostrara nada en pantalla solamente debería devolver un valor.

```
<?php
    function calculadora3($num1,$num2, $bold = false){
        $str= '';
        if($bold) $str.= '<b>';
        $str.= 'sumar : '. ($num1+$num2) . '<br>';
        $str.= 'restar : '. ($num1-$num2). '<br>';
        $str.= 'muiltiplicar : '. ($num1*$num2). '<br><br>';
        if($bold) $str.= '</b>';

        return $str;
    }

    echo calculadora3(5,2); //puedo pasarle el parametro o no
    echo calculadora3(5,2, true);
    echo calculadora3(5,2, false);


    ?>
```

## **Variables**

### _Globales_

Son las que se declaran fuera de una función y se pueden usar dentro y fuera de las funciones

### _Locales_

Son las que se declaran fuera de una función y se pueden usar dentro y fuera de las funciones

## **Includes**

Para usar código almacenados en otros archivos
```
//archivo index.php
 <?php 
        include 'includes/cabecera.php';
        include 'includes/footer.php';
    ?>
```
```
//archivo include/cabecera.php
<h2>Esto es la cabecera desde el archivo cabecera.php</h2>
```

```
//archivo include/footer.php
<h2>Esto es el pie desde el archivo footer.php</h2>
```

### *include_once*

No permite incluir mas de una vez un include

### _require_ o *require_once*

Con require no me permite ejecutar la pagina si hay algun error.
Con `require_once`  lo mismo pero solo permite incluirlo una vez

