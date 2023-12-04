# Guía Rápida de React

[documentación oficial de React](https://reactjs.org/).

- [Guía Rápida de React](#guía-rápida-de-react)
  - [Comandos Básicos en YARN](#comandos-básicos-en-yarn)
    - [Paso 1: Instalar Yarn](#paso-1-instalar-yarn)
    - [Paso 2: Crear un nuevo proyecto con Vite](#paso-2-crear-un-nuevo-proyecto-con-vite)
    - [Paso 3: Navegar al directorio del proyecto](#paso-3-navegar-al-directorio-del-proyecto)
    - [Paso 4: Instalar dependencias](#paso-4-instalar-dependencias)
    - [Paso 5: Iniciar el servidor de desarrollo](#paso-5-iniciar-el-servidor-de-desarrollo)
    - [Paso 6: Comenzar a desarrollar](#paso-6-comenzar-a-desarrollar)
    - [Paso 7: Construir la aplicación para producción](#paso-7-construir-la-aplicación-para-producción)
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

## Comandos Básicos en YARN

Guía básica para comenzar un proyecto con React utilizando Yarn y Vite. Vite es un entorno de desarrollo rápido para proyectos basados en JavaScript, y Yarn es un administrador de paquetes que se utiliza para gestionar las dependencias del proyecto.

### Paso 1: Instalar Yarn
Si aún no tienes Yarn instalado, puedes hacerlo siguiendo las instrucciones en [la página oficial de Yarn](https://yarnpkg.com/getting-started/install).

### Paso 2: Crear un nuevo proyecto con Vite
Ejecuta los siguientes comandos en tu terminal para crear un nuevo proyecto con Vite:

```bash
yarn create @vitejs/app my-react-app --template react
```

Esto creará un nuevo directorio llamado `my-react-app` con una estructura de proyecto básica de React.

### Paso 3: Navegar al directorio del proyecto
Ve al directorio del proyecto recién creado:

```bash
cd my-react-app
```

### Paso 4: Instalar dependencias
Instala las dependencias del proyecto utilizando Yarn:

```bash
yarn
```

### Paso 5: Iniciar el servidor de desarrollo
Inicia el servidor de desarrollo para tu aplicación React:

```bash
yarn dev
```

Esto iniciará el servidor y podrás ver tu aplicación en `http://localhost:5173`.

### Paso 6: Comenzar a desarrollar
Abre tu editor de código favorito y comienza a editar los archivos en el directorio `src`. Puedes ver los cambios en tiempo real en tu navegador mientras desarrollas.

### Paso 7: Construir la aplicación para producción
Cuando estés listo para construir tu aplicación para producción, puedes ejecutar:

```bash
yarn build
```

Esto generará una carpeta `dist` que contiene los archivos optimizados para producción.

¡Y eso es básicamente todo! Ahora tienes un nuevo proyecto React configurado con Yarn y Vite, listo para ser desarrollado y desplegado. Puedes personalizar tu aplicación según tus necesidades y explorar más sobre Vite y sus características en la [documentación oficial de Vite](https://vitejs.dev/).

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
