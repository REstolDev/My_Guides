<div align="center">

    # APUNTES JS

</div>

## MENÚ

- [MENÚ](#menú)
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