# Guía Rápida de Express.js con Habilitación de CORS

## ¿Qué es Express.js?

Express.js es un framework web de Node.js que permite construir aplicaciones web y API de manera sencilla y rápida.

## Instalación

Primero, asegúrate de tener Node.js instalado en tu sistema. Luego, puedes crear un proyecto Express.js yendo al directorio de tu proyecto en la terminal y ejecutando:

```bash
npm init
npm install express --save
```

## Crear una aplicación en Express

~~~
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('¡Hola, mundo!');
});

app.listen(port, () => {
  console.log(`La aplicación está escuchando en el puerto ${port}`);
});
~~~
## Habilitar CORS en Express.js

CORS (Cross-Origin Resource Sharing) permite a los navegadores realizar solicitudes HTTP a un dominio diferente al del recurso original. Para habilitar CORS en Express.js, puedes usar la biblioteca cors. 

Asegúrate de instalarla:

`npm install cors --save
`
Luego, habilita CORS en tu aplicación Express.js:

~~~
const express = require('express');
const cors = require('cors'); // Importa la biblioteca cors
const app = express();
const port = 3000;

// Habilita CORS para todas las rutas
app.use(cors());

app.get('/', (req, res) => {
  res.send('¡Hola, mundo!');
});

app.listen(port, () => {
  console.log(`La aplicación está escuchando en el puerto ${port}`);
});
~~~

Ahora, tu aplicación Express.js estará configurada para permitir solicitudes desde diferentes orígenes.

Recuerda que esta guía es solo una introducción básica a Express.js y CORS. Puedes personalizar y expandir tu aplicación según tus necesidades específicas.

Para obtener información más actualizada o detalles avanzados, consulta la documentación oficial de Express.js 
(https://expressjs.com/) 
y CORS (https://expressjs.com/en/resources/middleware/cors.html).

