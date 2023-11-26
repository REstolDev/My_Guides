<div align="center">

    # APUNTES JS

</div>

## MENÚ

- [MENÚ](#menú)
- [Objetos en JavaScript](#objetos-en-javascript)
  - [Características Principales:](#características-principales)
  - [Operadores Adicionales:](#operadores-adicionales)
  - [**Funciones en Objetos:**](#funciones-en-objetos)
    - [**Métodos:**](#métodos)
  - [**Operadores de Propagación (Spread) y Desestructuración:**](#operadores-de-propagación-spread-y-desestructuración)
  - [**Propiedades Computadas y Símbolos:**](#propiedades-computadas-y-símbolos)
  - [Otros Tipos de Objetos en JavaScript:](#otros-tipos-de-objetos-en-javascript)
- [call](#call)
- [Apply](#apply)
- [bind](#bind)
- [Operador Spread (`...`)](#operador-spread-)
- [Operador Rest (`...`)](#operador-rest-)
  - [`find`](#find)
  - [`map`](#map)
  - [`filter`](#filter)
- [CALLBACK](#callback)
- [PROMISES - Promesas en JavaScript](#promises---promesas-en-javascript)
  - [Creando una promesa](#creando-una-promesa)
  - [Ejemplo de Promesa](#ejemplo-de-promesa)
- [Clases en JavaScript](#clases-en-javascript)
  - [Definición de una clase](#definición-de-una-clase)
  - [Ejemplo de una clase](#ejemplo-de-una-clase)
- [Clases en JavaScript](#clases-en-javascript-1)
  - [Definición de una clase](#definición-de-una-clase-1)
  - [Ejemplo de una clase](#ejemplo-de-una-clase-1)
- [Herencia en ECMAScript 6 (ES6)](#herencia-en-ecmascript-6-es6)
  - [Definición de una Clase (Superclase)](#definición-de-una-clase-superclase)
  - [Creación de una Subclase (Clase Hija)](#creación-de-una-subclase-clase-hija)
  - [Uso de la Herencia](#uso-de-la-herencia)
  - [Conclusión](#conclusión)
- [Modulos de Node.js](#modulos-de-nodejs)
- [Readline - entradas por teclado terminal](#readline---entradas-por-teclado-terminal)
- [Require - cargar modulos de node.js](#require---cargar-modulos-de-nodejs)

## Objetos en JavaScript

Los objetos en JavaScript son arreglos asociativos que permiten almacenar propiedades en pares clave-valor. Aquí hay un resumen de las características y operaciones más importantes relacionadas con los objetos:

### Características Principales:

- **Propiedades:**
  - Almacenan pares clave-valor.
  - Las claves deben ser cadenas o símbolos.
  - Los valores pueden ser de cualquier tipo.

- **Acceso a Propiedades:**
  - Notación de punto: `obj.property`.
  - Notación de corchetes: `obj["property"]`. Útil cuando la clave es dinámica (`obj[varWithKey]`).

### Operadores Adicionales:

- **Eliminación de Propiedad:**
  - `delete obj.prop`: Elimina la propiedad `prop` del objeto.

- **Comprobación de Existencia:**
  - `"key" in obj`: Verifica si existe una propiedad con la clave proporcionada.

- **Bucle sobre Propiedades:**
  - `for (let key in obj)`: Permite recorrer las propiedades del objeto en un bucle.
  
### **Funciones en Objetos:**

#### **Métodos:**
  - En JavaScript, las funciones pueden ser propiedades de un objeto.
  - Cuando una función es propiedad de un objeto, se llama "método".
  - Ejemplo:
    ```javascript
    let myObject = {
      greeting: "Hola",
      sayHello: function() {
        console.log(this.greeting);
      }
    };

    myObject.sayHello(); // Salida: Hola
    ```

### **Operadores de Propagación (Spread) y Desestructuración:**

- **Operador Spread (`...`):**
  - Permite copiar propiedades de un objeto a otro de una manera más concisa.
  - Ejemplo:
    ```javascript
    let obj1 = { a: 1, b: 2 };
    let obj2 = { ...obj1, c: 3 };
    // Resultado: obj2 es { a: 1, b: 2, c: 3 }
    ```

- **Desestructuración:**
  - Permite extraer propiedades de un objeto y asignarlas a variables.
  - Ejemplo:
    ```javascript
    let { a, b } = obj1;
    // Resultado: a es 1, b es 2
    ```

### **Propiedades Computadas y Símbolos:**

- **Propiedades Computadas:**
  - Las claves de propiedad pueden ser expresiones o variables.
  - Ejemplo:
    ```javascript
    let key = "myKey";
    let obj = { [key]: "valor" };
    // Resultado: obj es { myKey: "valor" }
    ```

- **Símbolos:**
  - Tipo de dato único e inmutable que se puede usar como clave de propiedad.
  - Ayuda a prevenir colisiones de nombres de propiedades.
  - Ejemplo:
    ```javascript
    const mySymbol = Symbol("descripcion");
    let obj = { [mySymbol]: "valor" };
    ```

Estas son algunas adiciones a las características básicas de los objetos en JavaScript. Las funciones, el operador spread, la desestructuración, las propiedades computadas y los símbolos ofrecen más flexibilidad y poder al trabajar con objetos en el lenguaje.

### Otros Tipos de Objetos en JavaScript:

- **Array:**
  - Almacena colecciones de datos ordenados.
  - Ejemplo: `let myArray = [1, 2, 3];`

- **Date:**
  - Almacena información sobre fecha y hora.
  - Ejemplo: `let currentDate = new Date();`

- **Error:**
  - Almacena información sobre un error.
  - Ejemplo: `let customError = new Error('Mensaje de error');`

Y hay muchos otros tipos de objetos en JavaScript, cada uno con sus propias características y utilidades.

## call
En JavaScript, la función `call` es un método que pertenece a todas las funciones y se utiliza para llamar a una función con un valor específico para el objeto al que pertenece. En otras palabras, te permite cambiar el contexto en el que una función es ejecutada.

La sintaxis básica de `call` es la siguiente:

```javascript
funcion.call(thisArg, arg1, arg2, ...)
```

- `funcion`: La función a ser llamada.
- `thisArg`: El valor que se utilizará como `this` dentro de la función `funcion`.
- `arg1, arg2, ...`: Los argumentos que se pasarán a la función `funcion`.

Aquí hay un ejemplo simple:

```javascript
function saludar() {
  console.log(`Hola, ${this.nombre}!`);
}

const persona = {
  nombre: 'Juan'
};

// Llamando a la función saludar con el contexto de la persona usando call
saludar.call(persona); // Imprimirá: Hola, Juan!
```

En este caso, `call` se utiliza para ejecutar la función `saludar`, pero se especifica que dentro de la función, la palabra clave `this` debe hacer referencia al objeto `persona`. Esto permite acceder a la propiedad `nombre` del objeto `persona` dentro de la función `saludar`.

## Apply
`apply` es otro método similar a `call` en JavaScript que se utiliza para invocar una función, pero en lugar de pasar los argumentos individualmente, toma un array de argumentos. La sintaxis básica de `apply` es la siguiente:

```javascript
funcion.apply(thisArg, [arg1, arg2, ...])
```

- `funcion`: La función a ser llamada.
- `thisArg`: El valor que se utilizará como `this` dentro de la función `funcion`.
- `[arg1, arg2, ...]`: Un array de argumentos que se pasarán a la función `funcion`.

Aquí hay un ejemplo:

```javascript
function saludar(mensaje) {
  console.log(`${mensaje}, ${this.nombre}!`);
}

const persona = {
  nombre: 'Juan'
};

// Llamando a la función saludar con el contexto de la persona y argumentos usando apply
saludar.apply(persona, ['Hola']); // Imprimirá: Hola, Juan!
```

En este ejemplo, la función `saludar` se llama con el contexto de `persona` y se le pasa el array `['Hola']` como argumento. La palabra clave `this` dentro de la función hace referencia al objeto `persona`, y el argumento 'Hola' se utiliza dentro de la cadena de salida.

## bind
`bind` es otro método en JavaScript que se utiliza para crear una nueva función con un valor específico para la palabra clave `this`, y opcionalmente, predefinir algunos de los argumentos. A diferencia de `call` y `apply`, `bind` no ejecuta la función de inmediato, sino que devuelve una nueva función que puedes llamar más tarde. La sintaxis básica de `bind` es la siguiente:

```javascript
nuevaFuncion = funcion.bind(thisArg, arg1, arg2, ...)
```

- `funcion`: La función original que se va a vincular.
- `thisArg`: El valor que se utilizará como `this` dentro de la función `funcion`.
- `arg1, arg2, ...`: Argumentos opcionales que se pueden predefinir en la nueva función.

Aquí hay un ejemplo:

```javascript
function saludar(mensaje) {
  console.log(`${mensaje}, ${this.nombre}!`);
}

const persona = {
  nombre: 'Juan'
};

// Creando una nueva función saludar con el contexto de la persona
const saludarAJuan = saludar.bind(persona, 'Hola');

// Llamando a la nueva función
saludarAJuan(); // Imprimirá: Hola, Juan!
```

En este ejemplo, `bind` se utiliza para crear una nueva función llamada `saludarAJuan`. Esta nueva función siempre tendrá el objeto `persona` como contexto (`this`) y el mensaje 'Hola' predefinido como argumento. Luego, se llama a la nueva función y se imprime el mensaje resultante. Es útil cuando se quiere fijar ciertos valores y usarlos más tarde, por ejemplo, en manejo de eventos o devolución de llamada.


## Operador Spread (`...`)

El operador spread se utiliza para descomponer o "esparcir" elementos de una estructura, como un array o un objeto, en lugares donde se esperan cero o más elementos. En otras palabras, se utiliza para copiar los elementos de una estructura en otra. La sintaxis básica es:

- **Arrays:**
  ```javascript
  const array1 = [1, 2, 3];
  const array2 = [...array1, 4, 5, 6];
  console.log(array2); // Imprimirá: [1, 2, 3, 4, 5, 6]
  ```

- **Objetos:**
  ```javascript
  const obj1 = { a: 1, b: 2 };
  const obj2 = { ...obj1, c: 3, d: 4 };
  console.log(obj2); // Imprimirá: { a: 1, b: 2, c: 3, d: 4 }
  ```

## Operador Rest (`...`)

El operador rest se utiliza para recoger los elementos restantes de una estructura, como un array, en una variable. Se coloca en la declaración de la función o en la desestructuración de un array. La sintaxis básica es:

- **Funciones:**
  ```javascript
  function sumar(...numeros) {
    return numeros.reduce((total, numero) => total + numero, 0);
  }

  console.log(sumar(1, 2, 3, 4)); // Imprimirá: 10
  ```

- **Desestructuración de arrays:**
  ```javascript
  const [primerElemento, segundoElemento, ...resto] = [1, 2, 3, 4, 5];
  console.log(primerElemento); // Imprimirá: 1
  console.log(segundoElemento); // Imprimirá: 2
  console.log(resto); // Imprimirá: [3, 4, 5]
  ```

En resumen, el operador spread se utiliza para descomponer elementos, mientras que el operador rest se utiliza para recoger elementos restantes. Ambos operadores son denotados por tres puntos (`...`), pero su comportamiento depende del contexto en el que se utilizan.
En JavaScript, `find`, `map`, y `filter` son métodos de array que proporcionan funcionalidades específicas para trabajar con elementos de arrays de manera más concisa y funcional.

### `find`

El método `find` se utiliza para encontrar el primer elemento en un array que cumple con una condición especificada. Retorna el valor del primer elemento que cumple la condición, o `undefined` si no se encuentra ningún elemento.

```javascript
const numeros = [1, 2, 3, 4, 5];

const numeroEncontrado = numeros.find(numero => numero > 2);
console.log(numeroEncontrado); // Imprimirá: 3
```

### `map`

El método `map` se utiliza para crear un nuevo array aplicando una función a cada elemento del array original. Retorna un nuevo array con los resultados de aplicar la función a cada elemento.

```javascript
const numeros = [1, 2, 3, 4, 5];

const cuadrados = numeros.map(numero => numero * numero);
console.log(cuadrados); // Imprimirá: [1, 4, 9, 16, 25]
```

### `filter`

El método `filter` se utiliza para crear un nuevo array con todos los elementos que cumplan una condición especificada. Retorna un nuevo array con los elementos que pasaron la condición.

```javascript
const numeros = [1, 2, 3, 4, 5];

const numerosPares = numeros.filter(numero => numero % 2 === 0);
console.log(numerosPares); // Imprimirá: [2, 4]
```

Estos métodos son especialmente útiles en programación funcional y son parte de las funciones de orden superior en JavaScript. Pueden simplificar el código y hacerlo más legible al eliminar la necesidad de bucles explícitos.

Es importante tener en cuenta que estos métodos no modifican el array original, sino que retornan un nuevo array o valor basado en el array original.

El método `reduce` en JavaScript se utiliza para reducir un array a un solo valor aplicando una función acumuladora a cada elemento del array. La función acumuladora toma dos argumentos: el acumulador y el valor actual. El acumulador es el resultado parcial de las operaciones anteriores, y el valor actual es el elemento actual del array.

La sintaxis básica de `reduce` es la siguiente:

```javascript
array.reduce(function(acumulador, elementoActual, indice, array) {
  // Lógica para combinar el acumulador con el elemento actual
  return nuevoAcumulador;
}, valorInicial);
```

- `acumulador`: El resultado acumulado de las operaciones anteriores.
- `elementoActual`: El valor del elemento actual del array.
- `indice`: (Opcional) El índice del elemento actual en el array.
- `array`: (Opcional) El array original que está siendo procesado.
- `valorInicial`: (Opcional) El valor inicial del acumulador en la primera llamada a la función acumuladora.

Aquí hay un ejemplo simple de cómo usar `reduce` para sumar todos los elementos de un array:

```javascript
const numeros = [1, 2, 3, 4, 5];

const suma = numeros.reduce(function(acumulador, numero) {
  return acumulador + numero;
}, 0);

console.log(suma); // Imprimirá: 15
```

En este ejemplo:

- El acumulador comienza en 0 (se proporciona como segundo argumento a `reduce`).
- La función acumuladora se ejecuta para cada elemento del array.
- En cada iteración, el acumulador se actualiza sumándole el valor del elemento actual.
- Al final, `reduce` devuelve el valor final del acumulador.

Es importante destacar que `reduce` puede ser utilizado para realizar una amplia variedad de operaciones de reducción en arrays, desde sumas y productos hasta concatenación y generación de objetos más complejos. La clave está en cómo defines y utiliza la función acumuladora.

## CALLBACK

Un callback es una función que se pasa como argumento a otra función y se ejecuta después de que ocurra algún evento o se complete una tarea. En el caso del códigodel ejemplo, el callback se utiliza en la función `customConfirm` para manejar la respuesta del usuario (confirmación o cancelación) después de que se muestre el cuadro de confirmación personalizado.

Aquí está el código de `customConfirm`:

```javascript
function customConfirm(message, callback) {
  // Muestra el cuadro de confirmación personalizado con el mensaje dado
  // y botones para confirmar o cancelar.
  // Luego, llama al callback con true si se confirma o false si se cancela.
  // ...

  // Cuando el usuario confirma:
  if (confirmado) {
    // Llama al callback con true para indicar que se confirmó la acción.
    callback(true);
  } else {
    // Cuando el usuario cancela:
    // Llama al callback con false para indicar que se canceló la acción.
    callback(false);
  }
}
```

Ahora, observemos cómo se utiliza `customConfirm` en la función `clear`:

```javascript
function clear() {
  customConfirm("Do you want to delete all the projects from your Local Storage?", (isConfirmed) => {
    if (isConfirmed) {
      localStorage.clear();
      showCustomAlert("Project Deleted");
    }
  });
}
```

1. Cuando se llama a `clear`, primero se muestra el cuadro de confirmación personalizado utilizando `customConfirm`. Se pasa el mensaje "Do you want to delete all the projects from your Local Storage?" como primer argumento.

2. El segundo argumento que se pasa a `customConfirm` es una función de flecha `(isConfirmed) => { ... }`. Esta función de flecha es el callback que se ejecutará después de que el usuario confirme o cancele la acción.

3. Cuando el usuario interactúa con el cuadro de confirmación personalizado y toma una decisión (confirmar o cancelar), `customConfirm` llamará al callback con un argumento. Si el usuario confirma, se llama al callback con `true`; si el usuario cancela, se llama al callback con `false`.

4. En la función de callback `(isConfirmed) => { ... }`, verificamos el valor de `isConfirmed`. Si es `true`, significa que el usuario confirmó la acción. En este caso, ejecutamos el código dentro del `if`:

   - `localStorage.clear();` borra todos los proyectos del almacenamiento local.
   - `showCustomAlert("Project Deleted");` muestra una alerta personalizada indicando que se eliminaron los proyectos.

En resumen, el callback permite que la función `clear` maneje la respuesta del usuario después de que se muestre el cuadro de confirmación personalizado. Si el usuario confirma, se realizan las acciones correspondientes para borrar los proyectos y mostrar una alerta personalizada. Si el usuario cancela, no se realiza ninguna acción. Esto hace que el código sea más flexible y reutilizable, ya que puedes usar la misma función `customConfirm` para manejar otras confirmaciones en tu aplicación.


## PROMISES - Promesas en JavaScript

Las promesas son objetos que representan un valor que puede estar disponible ahora, en el futuro o nunca. Se utilizan para manejar operaciones asincrónicas de manera más ordenada. Una promesa tiene tres estados posibles: pendiente (pending), resuelta (fulfilled), o rechazada (rejected).

### Creando una promesa

Puedes crear una promesa usando la siguiente sintaxis:

```javascript
const miPromesa = new Promise((resolve, reject) => {
  // Código asincrónico aquí
  // Si la operación tiene éxito, llama a 'resolve' con el resultado.
  // Si ocurre un error, llama a 'reject' con el motivo del error.
});
```

### Ejemplo de Promesa

A continuación, se presenta un ejemplo de cómo usar promesas para cargar datos de un servidor de forma asincrónica y manejar tanto el éxito como los errores.

```javascript
// Crear una función que devuelve una promesa
function cargarDatos() {
  return new Promise((resolve, reject) => {
    // Simular una solicitud asincrónica (por ejemplo, una solicitud AJAX)
    setTimeout(() => {
      const exito = true; // Cambiar a 'false' para simular un error

      if (exito) {
        const datos = "Datos cargados con éxito";
        resolve(datos);
      } else {
        const error = "Error al cargar los datos";
        reject(error);
      }
    }, 2000); // Simula una demora de 2 segundos
  });
}

// Usar la promesa
cargarDatos()
  .then((resultado) => {
    console.log("Éxito:", resultado);
  })
  .catch((error) => {
    console.error("Error:", error);
  });
```

En este ejemplo:

1. Creamos una función `cargarDatos` que devuelve una promesa.
2. Dentro de la promesa, simulamos una solicitud asincrónica.
3. Dependiendo de si la solicitud se realiza con éxito o no, llamamos a `resolve` o `reject` para manejar el resultado.
4. Usamos `.then` para manejar el caso de éxito y `.catch` para manejar el caso de error.

Esta es la estructura básica de cómo trabajar con promesas en JavaScript para manejar operaciones asincrónicas de manera más clara y eficiente. Las promesas permiten encadenar múltiples operaciones asincrónicas y manejar los errores de manera más efectiva.

¡Claro! Te explicaré cómo definir y usar clases en JavaScript usando Markdown, junto con un ejemplo paso a paso.

## Clases en JavaScript

Las clases son una forma de definir objetos y sus comportamientos en JavaScript. Aportan un enfoque más orientado a objetos para la programación en JavaScript y se introdujeron en ECMAScript 6 (ES6).

### Definición de una clase

Para definir una clase en JavaScript, puedes utilizar la siguiente sintaxis:

```javascript
class NombreDeLaClase {
  constructor(parametros) {
    // Constructor: inicializa la clase con los parámetros proporcionados
  }

  metodo1() {
    // Definición del primer método
  }

  metodo2() {
    // Definición del segundo método
  }
}
```

### Ejemplo de una clase

A continuación, se presenta un ejemplo de cómo definir y utilizar una clase en JavaScript:

```javascript
// Definición de una clase llamada 'Persona'
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre} y tengo ${this.edad} años.`);
  }
}

// Creación de objetos basados en la clase 'Persona'
const persona1 = new Persona("Juan", 30);
const persona2 = new Persona("Ana", 25);

// Uso de métodos de la clase
persona1.saludar(); // Salida: Hola, soy Juan y tengo 30 años.
persona2.saludar(); // Salida: Hola, soy Ana y tengo 25 años.
```

En este ejemplo:

1. Definimos una clase llamada `Persona` con un constructor que inicializa las propiedades `nombre` y `edad`.
2. La clase `Persona` también tiene un método `saludar` que muestra un saludo en la consola con los valores de `nombre` y `edad`.
3. Luego, creamos dos objetos, `persona1` y `persona2`, basados en la clase `Persona`.
4. Utilizamos el método `saludar` en cada uno de los objetos para mostrar un saludo personalizado.

Las clases en JavaScript permiten una forma más estructurada y orientada a objetos de organizar el código, facilitando la creación y manipulación de objetos con propiedades y métodos.

¡Claro! Te explicaré cómo definir y usar clases en JavaScript usando Markdown, junto con un ejemplo paso a paso.

## Clases en JavaScript

Las clases son una forma de definir objetos y sus comportamientos en JavaScript. Aportan un enfoque más orientado a objetos para la programación en JavaScript y se introdujeron en ECMAScript 6 (ES6).

### Definición de una clase

Para definir una clase en JavaScript, puedes utilizar la siguiente sintaxis:

```javascript
class NombreDeLaClase {
  constructor(parametros) {
    // Constructor: inicializa la clase con los parámetros proporcionados
  }

  metodo1() {
    // Definición del primer método
  }

  metodo2() {
    // Definición del segundo método
  }
}
```

### Ejemplo de una clase

A continuación, se presenta un ejemplo de cómo definir y utilizar una clase en JavaScript:

```javascript
// Definición de una clase llamada 'Persona'
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre} y tengo ${this.edad} años.`);
  }
}

// Creación de objetos basados en la clase 'Persona'
const persona1 = new Persona("Juan", 30);
const persona2 = new Persona("Ana", 25);

// Uso de métodos de la clase
persona1.saludar(); // Salida: Hola, soy Juan y tengo 30 años.
persona2.saludar(); // Salida: Hola, soy Ana y tengo 25 años.
```

En este ejemplo:

1. Definimos una clase llamada `Persona` con un constructor que inicializa las propiedades `nombre` y `edad`.
2. La clase `Persona` también tiene un método `saludar` que muestra un saludo en la consola con los valores de `nombre` y `edad`.
3. Luego, creamos dos objetos, `persona1` y `persona2`, basados en la clase `Persona`.
4. Utilizamos el método `saludar` en cada uno de los objetos para mostrar un saludo personalizado.


## Herencia en ECMAScript 6 (ES6)

En ECMAScript 6 (también conocido como ES6 y posteriores), se introdujo una sintaxis más clara y sencilla para definir clases y heredar propiedades y métodos. A continuación, te proporcionaré una explicación de la herencia en ES6 y un ejemplo paso a paso.

### Definición de una Clase (Superclase)

Para definir una superclase en ES6, utilizamos la palabra clave `class`. Dentro de la clase, podemos definir propiedades y métodos.

```javascript
class Animal {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}.`);
  }
}
```

### Creación de una Subclase (Clase Hija)

Para crear una subclase que herede de la superclase, también usamos la palabra clave `class`. Utilizamos `extends` para indicar la superclase de la que queremos heredar propiedades y métodos.

```javascript
class Perro extends Animal {
  constructor(nombre, raza) {
    super(nombre); // Llama al constructor de la superclase
    this.raza = raza;
  }
}
```

### Uso de la Herencia

Ahora, puedes crear instancias de la subclase `Perro` y heredar propiedades y métodos de la superclase `Animal`.

```javascript
const miPerro = new Perro("Fido", "Labrador");
miPerro.saludar(); // Salida: Hola, soy Fido.
console.log(`Raza: ${miPerro.raza}`); // Salida: Raza: Labrador
```

En este ejemplo, `miPerro` es una instancia de `Perro` que hereda la propiedad `nombre` y el método `saludar` de la superclase `Animal`. Además, `miPerro` tiene su propia propiedad `raza`.

### Conclusión

En ECMAScript 6 (ES6) y posteriores, la herencia se simplificó utilizando la sintaxis de clases. Esto hace que la creación y el uso de clases y herencia sean más sencillos y similares a otros lenguajes de programación orientados a objetos.

## Modulos de Node.js

## Readline - entradas por teclado terminal

`readline` es un módulo en Node.js que proporciona una interfaz para leer datos desde un flujo de entrada (como la entrada estándar, como la terminal). Es particularmente útil para interactuar con el usuario a través de la consola.

Aquí hay una explicación básica de cómo funciona `readline`:

1. **Importar el módulo:**
   Para usar `readline`, primero debes importar el módulo en tu script de Node.js.

   ```javascript
   const readline = require('readline');
   ```

2. **Crear una interfaz readline:**
   Luego, creas una interfaz readline. Esto generalmente implica especificar los flujos de entrada (`process.stdin`) y salida (`process.stdout`).

   ```javascript
   const rl = readline.createInterface({
     input: process.stdin,
     output: process.stdout
   });
   ```

3. **Utilizar la interfaz readline para leer datos:**
   Con la interfaz readline configurada, puedes usar sus métodos para leer datos del usuario. Uno de los métodos más comunes es `question`.

   ```javascript
   rl.question('¿Cómo te llamas? ', (respuesta) => {
     console.log(`Hola, ${respuesta}!`);
     rl.close();
   });
   ```

   En este ejemplo, `rl.question` muestra el mensaje proporcionado y espera a que el usuario escriba una respuesta. La respuesta se pasa a la función de devolución de llamada proporcionada, donde puedes procesarla.

4. **Cerrar la interfaz readline:**
   Es importante cerrar la interfaz readline cuando hayas terminado de usarla. Esto se hace llamando al método `close`.

   ```javascript
   rl.close();
   ```

   El cierre es crucial para liberar los recursos asociados con la interfaz readline.

El módulo `readline` es muy versátil y también proporciona otros métodos útiles, como `rl.prompt()` para mostrar un indicador de entrada, `rl.clearLine()` para borrar una línea en la salida, entre otros.

Aquí tienes un ejemplo completo utilizando `readline`:

```javascript
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

rl.question('¿Cómo te llamas? ', (respuesta) => {
  console.log(`Hola, ${respuesta}!`);
  rl.close();
});

// Cerrar la interfaz readline al finalizar
rl.on('close', () => {
  console.log('¡Hasta luego!');
  process.exit(0);
});
```

Este script le preguntará al usuario su nombre, imprimirá un saludo y luego se cerrará.


## Require - cargar modulos de node.js
`require` es una función en Node.js que se utiliza para cargar módulos en tu aplicación. La declaración `const nombre = require('nombre_del_modulo');` se utiliza para importar un módulo específico en Node.js.

La función `require` tiene algunas funciones clave:

1. **Importar Módulos:**
   - Se utiliza para cargar módulos en tu aplicación Node.js. Puedes importar módulos internos de Node.js, módulos de terceros o incluso tus propios módulos.

   ```javascript
   const fs = require('fs');  // Ejemplo de importación del módulo 'fs' para manipulación de archivos
   ```

2. **Caché de Módulos:**
   - `require` almacena en caché los módulos cargados. Esto significa que si importas un módulo varias veces en tu aplicación, la segunda y subsiguientes veces, Node.js usará la versión almacenada en caché en lugar de volver a cargarla. Esto ayuda a mejorar la eficiencia y el rendimiento.

3. **Exportar Funcionalidades (en combinación con `module.exports`):**
   - Puedes exportar funciones, variables o cualquier objeto desde un módulo para que estén disponibles para otros archivos que utilicen `require`. Esto se hace asignando valores al objeto `module.exports`.

   ```javascript
   // En un módulo llamado 'miModulo'
   module.exports = {
     saludar: function() {
       console.log('Hola desde mi módulo');
     },
     otraFuncion: function() {
       // ...
     }
   };
   ```

   ```javascript
   // En otro archivo que importa 'miModulo'
   const miModulo = require('./miModulo');  // Ruta relativa al archivo actual
   miModulo.saludar();  // Llama a la función exportada
   ```

4. **Manejo de Módulos de Terceros:**
   - Puedes usar `require` para instalar y cargar módulos de terceros que hayas instalado mediante npm (Node Package Manager). Por ejemplo:

   ```javascript
   const express = require('express');  // Importa el módulo 'express' para construir aplicaciones web
   ```

En resumen, `require` en Node.js es una función esencial para importar módulos y organizar la estructura de tu aplicación. También es importante entender cómo exportar funcionalidades desde un módulo para que otros archivos puedan acceder a ellas.