<div align="center">

    # APUNTES JS

</div>

## MENÚ

- [MENÚ](#menú)
- [**call**](#call)
- [**Apply**](#apply)
- [**bind**](#bind)
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


## **call**
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

## **Apply**
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

## **bind**
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

## Conclusión

En ECMAScript 6 (ES6) y posteriores, la herencia se simplificó utilizando la sintaxis de clases. Esto hace que la creación y el uso de clases y herencia sean más sencillos y similares a otros lenguajes de programación orientados a objetos.