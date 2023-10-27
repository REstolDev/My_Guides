# Guía Rápida de React

[documentación oficial de React](https://reactjs.org/).

- [Guía Rápida de React](#guía-rápida-de-react)
  - [Comandos Básicos en NPM](#comandos-básicos-en-npm)
    - [Instalación de React](#instalación-de-react)
    - [Iniciar la Aplicación](#iniciar-la-aplicación)
  - [Uso de Variables](#uso-de-variables)
    - [Declaración de Variables](#declaración-de-variables)
    - [Uso de Variables en JSX](#uso-de-variables-en-jsx)
  - [Características del Lenguaje JSX](#características-del-lenguaje-jsx)
    - [Componentes](#componentes)
    - [Renderizado Condicionado](#renderizado-condicionado)
  - [Uso de Bucles](#uso-de-bucles)
  - [Condicionales](#condicionales)
    - [Operador Ternario](#operador-ternario)
    - [`if` en Funciones](#if-en-funciones)
  - [Eventos](#eventos)
  - [Props](#props)
  - [Valores Predeterminados (Default Props)](#valores-predeterminados-default-props)
  - [**PropTypes**](#proptypes)
  - [Hooks](#hooks)
    - [`useState`](#usestate)
    - [`useEffect`](#useeffect)


## Comandos Básicos en NPM

### Instalación de React

Para crear una nueva aplicación de React, primero debes asegurarte de tener Node.js y npm instalados en tu sistema. Luego, puedes utilizar el siguiente comando para crear una nueva aplicación de React:

```bash
npx create-react-app mi-aplicacion
```

Esto creará una nueva aplicación de React llamada "mi-aplicacion" en un directorio con el mismo nombre.

### Iniciar la Aplicación

Para ejecutar tu aplicación de React, ve al directorio de tu proyecto y utiliza el siguiente comando:

```bash
cd mi-aplicacion
npm start
```

Esto iniciará un servidor de desarrollo y abrirá tu aplicación en tu navegador por defecto.

## Uso de Variables

### Declaración de Variables

En React, puedes declarar variables utilizando la palabra clave `const` o `let`. Por ejemplo:

```javascript
const nombre = "Juan";
let edad = 30;
```

### Uso de Variables en JSX

Puedes utilizar variables en tus componentes de React dentro de JSX usando llaves `{}`. Por ejemplo:

```javascript
function Saludo() {
  const nombre = "Juan";
  return <h1>Hola, {nombre}</h1>;
}
```

## Características del Lenguaje JSX

### Componentes

Los componentes son la unidad básica de una aplicación de React. Puedes crear componentes personalizados utilizando funciones o clases. Aquí hay un ejemplo de un componente funcional:

```javascript
function MiComponente() {
  return <p>Este es un componente de React</p>;
}
```

### Renderizado Condicionado

Puedes utilizar expresiones condicionales para renderizar contenido de manera condicional. Por ejemplo:

```javascript
function Saludo(props) {
  if (props.usuario) {
    return <h1>Hola, {props.usuario}.</h1>;
  }
  return <h1>Hola, Invitado.</h1>;
}
```

## Uso de Bucles

Puedes utilizar bucles para renderizar listas de elementos en React. Aquí hay un ejemplo de cómo hacerlo con un bucle `map`:

```javascript
function ListaDeNombres(props) {
  const nombres = props.nombres;
  return (
    <ul>
      {nombres.map((nombre, index) => (
        <li key={index}>{nombre}</li>
      ))}
    </ul>
  );
}
```

Asegúrate de proporcionar una clave única a cada elemento cuando renderices listas.

Claro, aquí tienes una guía más extendida de React que cubre condicionales, hooks, iteraciones, eventos y observables:


## Condicionales

### Operador Ternario

Puedes utilizar el operador ternario para realizar renderizado condicional en JSX. Por ejemplo:

```javascript
function Saludo(props) {
  return (
    <div>
      {props.usuario ? <h1>Hola, {props.usuario}.</h1> : <h1>Hola, Invitado.</h1>}
    </div>
  );
}
```

### `if` en Funciones

También puedes usar condicionales `if` dentro de funciones antes de devolver elementos JSX:

```javascript
function Saludo(props) {
  if (props.usuario) {
    return <h1>Hola, {props.usuario}.</h1>;
  } else {
    return <h1>Hola, Invitado.</h1>;
  }
}
```

## Eventos

Puedes manejar eventos como clics de botones, cambios de entrada, etc., en React utilizando atributos especiales en los elementos JSX. Por ejemplo:

```javascript
function BotonContador() {
  const [contador, setContador] = useState(0);

  const manejarClick = () => {
    setContador(contador + 1);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={manejarClick}>Incrementar</button>
    </div>
  );
}
```


## Props

En React, puedes pasar datos de un componente padre a un componente hijo utilizando `props`. Las `props` son simplemente objetos que contienen datos que un componente recibe y utiliza para renderizar. Aquí hay un ejemplo:

```javascript
function Saludo(props) {
  return <h1>Hola, {props.nombre}.</h1>;
}

// Uso del componente Saludo con propiedades
<Saludo nombre="Juan" />
```

En el ejemplo anterior, hemos pasado la propiedad `nombre` al componente `Saludo`. Dentro de `Saludo`, podemos acceder a esta propiedad a través del objeto `props` para mostrar el nombre.

## Valores Predeterminados (Default Props)

A veces es útil establecer valores predeterminados para las `props` en caso de que no se proporcionen. Puedes hacerlo de la siguiente manera:

```javascript
function Saludo(props) {
  const nombre = props.nombre || "Invitado";
  return <h1>Hola, {nombre}.</h1>;
}

Saludo.defaultProps = {
  nombre: "Invitado",
};
```

En el ejemplo anterior, hemos utilizado una expresión lógica para verificar si se proporciona una `props` `nombre`. Si no se proporciona, utilizamos "Invitado" como valor predeterminado. Además, hemos definido un valor predeterminado utilizando `defaultProps` en el componente `Saludo` para asegurarnos de que siempre haya un valor predeterminado disponible.

También puedes utilizar valores predeterminados al definir componentes funcionales con el operador de asignación destructiva (destructuring) y el operador de asignación condicional:

```javascript
function Saludo({ nombre = "Invitado" }) {
  return <h1>Hola, {nombre}.</h1>;
}
```

En este ejemplo, estamos utilizando asignación destructiva para extraer la propiedad `nombre` de `props`, y estamos proporcionando un valor predeterminado directamente en la asignación `nombre = "Invitado"`.

El uso de `props` y la definición de valores predeterminados son prácticas comunes en React para pasar datos entre componentes y proporcionar valores seguros por defecto.

## **PropTypes**

En React, PropTypes es una biblioteca que se utiliza para definir y validar los tipos de propiedades (props) que se pasan a los componentes. Proporciona una forma de documentar y validar las props que se esperan en un componente, lo que puede ayudar a prevenir errores y facilitar el trabajo en equipos de desarrollo. A partir de React 15.5 en adelante, PropTypes se ha mudado a su propio paquete llamado "prop-types".

A continuación, te muestro cómo puedes usar PropTypes en tus componentes:

1. **Instalación de prop-types**:

   Primero, debes asegurarte de que tengas instalada la biblioteca `prop-types` en tu proyecto:

   ```bash
   npm install prop-types
   ```

   O con Yarn:

   ```bash
   yarn add prop-types
   ```

2. **Importación de PropTypes**:

   Importa PropTypes en el archivo donde definirás tus componentes:

   ```javascript
   import PropTypes from 'prop-types';
   ```

3. **Definición de PropTypes en el Componente**:

   Puedes definir PropTypes en tu componente utilizando la propiedad `propTypes`. A continuación, un ejemplo de un componente que espera una prop `nombre` de tipo `string` y una prop `edad` de tipo `number`:

   ```javascript
   import React from 'react';
   import PropTypes from 'prop-types';

   function MiComponente(props) {
     return (
       <div>
         <p>Nombre: {props.nombre}</p>
         <p>Edad: {props.edad}</p>
       </div>
     );
   }

   MiComponente.propTypes = {
     nombre: PropTypes.string,
     edad: PropTypes.number,
   };
   ```

   Si alguien pasa propiedades de un tipo incorrecto, React mostrará advertencias en la consola durante el desarrollo.

4. **Propiedades Opcionales y Requeridas**:

   Puedes indicar si una prop es opcional o requerida utilizando PropTypes. Por ejemplo:

   ```javascript
   MiComponente.propTypes = {
     nombre: PropTypes.string.isRequired, // requerido
     edad: PropTypes.number, // opcional
   };
   ```

5. **Valores Predeterminados**:

   También puedes especificar valores predeterminados (default props) utilizando la propiedad `defaultProps`:

   ```javascript
   MiComponente.defaultProps = {
     nombre: 'Invitado',
     edad: 0,
   };
   ```

   Esto proporciona valores por defecto si las props no se proporcionan.

Usar PropTypes en tus componentes es una buena práctica, especialmente en aplicaciones más grandes o en equipos de desarrollo colaborativo, ya que ayuda a documentar y validar las expectativas de uso de los componentes.


## Hooks

Los hooks son funciones especiales que te permiten añadir estado y otras características de React a componentes funcionales. Algunos de los hooks más comunes son:

### `useState`

`useState` te permite agregar estado a componentes funcionales. Por ejemplo:

```javascript
import React, { useState } from 'react';

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
    </div>
  );
}
```

### `useEffect`

`useEffect` te permite realizar efectos secundarios en componentes funcionales, como llamadas a API o suscripciones a eventos. Por ejemplo:

```javascript
import React, { useState, useEffect } from 'react';

function DatosEnTiempoReal() {
  const [datos, setDatos] = useState([]);

  useEffect(() => {
    // Lógica para obtener datos en tiempo real, por ejemplo, desde una API.
    // Actualiza 'datos' utilizando setDatos.
  }, []); // El segundo argumento, un array vacío, significa que este efecto se ejecuta solo una vez al montar el componente.
  
  return (
    // Renderiza datos en el componente.
  );
}
```
