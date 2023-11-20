# Conceptos

- [Conceptos](#conceptos)
- [**Compilación, transpilación e interpretación**](#compilación-transpilación-e-interpretación)
- [**Diferencia entre transpilar y compilar**](#diferencia-entre-transpilar-y-compilar)

# **Compilación, transpilación e interpretación**

1. Compilación en el frontend:
   - Ejemplo: Compilar SCSS a CSS.
   - En el caso de SCSS (Sass), un preprocesador de CSS, se escribe el código en un formato más avanzado y luego se compila a CSS estándar que los navegadores pueden entender. El resultado es un archivo CSS que se enlaza en las páginas web.

2. Transpilación en el frontend:
   - Ejemplo: Transpilar TypeScript a JavaScript.
   - TypeScript es un superset de JavaScript que agrega características adicionales, como tipado estático. El código TypeScript se transpila a JavaScript para que los navegadores puedan ejecutarlo. El resultado es un archivo JavaScript.

3. Interpretación en el frontend:
   - Ejemplo: Interpretación de JavaScript en el navegador.
   - En el navegador web, el código JavaScript se interpreta directamente. Cuando un navegador carga una página web, interpreta y ejecuta el código JavaScript en tiempo real. Esto permite la interactividad en la página, manipulación del DOM y otros comportamientos dinámicos.

Además, en el frontend, HTML y CSS no necesitan un proceso de compilación o transpilación en sí mismos. HTML se interpreta directamente en el navegador para renderizar la estructura de la página, mientras que CSS se interpreta para aplicar estilos a los elementos HTML. Estos lenguajes son entendidos y procesados por los navegadores sin necesidad de una conversión previa.

En resumen, en el desarrollo frontend, la compilación y transpilación se utilizan para convertir lenguajes de alto nivel, como SCSS y TypeScript, en lenguajes más simples que los navegadores pueden entender (CSS y JavaScript). La interpretación es el proceso en el que los navegadores interpretan directamente el código JavaScript, HTML y CSS para renderizar páginas web y brindar interactividad al usuario.

# **Diferencia entre transpilar y compilar**
Tanto SCSS a CSS como TypeScript a JavaScript son ejemplos de procesos de traducción de un lenguaje de alto nivel a otro lenguaje de alto nivel. Sin embargo, la principal diferencia entre compilación y transpilación radica en el propósito y la naturaleza de los lenguajes de destino, así como en cómo se utilizan en el contexto del desarrollo web:

1. Compilación:
   - La compilación se refiere al proceso de traducir un lenguaje de alto nivel a un lenguaje de nivel más bajo o a un lenguaje de máquina. En este caso, el lenguaje de destino es generalmente más eficiente y está más cerca del hardware de la computadora.
   - En el contexto del desarrollo web, se usa principalmente cuando se trata de lenguajes de servidor o desarrollo de aplicaciones de escritorio.
   - Ejemplo: Compilar código C++ a código de máquina.

2. Transpilación:
   - La transpilación se refiere al proceso de traducir un lenguaje de alto nivel a otro lenguaje de alto nivel que es similar pero está diseñado para un propósito diferente o una versión anterior.
   - En el contexto del desarrollo web, se utiliza para traducir lenguajes modernos o avanzados a versiones más simples o compatibles con navegadores y entornos específicos.
   - Ejemplo: Transpilar TypeScript (un superset de JavaScript) a JavaScript estándar (ES5) para garantizar la compatibilidad con navegadores más antiguos.

En resumen, la principal diferencia entre compilación y transpilación en el contexto del desarrollo web es el nivel de lenguaje de destino y el propósito. La compilación generalmente traduce a un lenguaje de nivel más bajo o de máquina, mientras que la transpilación traduce a un lenguaje de alto nivel similar pero con un propósito específico, como la compatibilidad con navegadores. Ambos procesos son útiles en diferentes situaciones y tienen como objetivo facilitar el desarrollo y la ejecución de aplicaciones web.

Una solicitud HTTP, comúnmente conocida como solicitud HTTP o HTTP request en inglés, es un mensaje que se envía desde un cliente a un servidor para solicitar algún recurso o acción en la World Wide Web. El protocolo HTTP (Hypertext Transfer Protocol) es el protocolo estándar utilizado para la comunicación entre clientes (navegadores web, aplicaciones, dispositivos) y servidores web.

Una solicitud HTTP consta de varios componentes clave:

1. **Método HTTP**: Indica la acción que se debe realizar en el recurso solicitado. Los métodos más comunes incluyen GET (para obtener información), POST (para enviar datos), PUT (para actualizar recursos), DELETE (para eliminar recursos) y otros.

2. **URL (Uniform Resource Locator)**: Es la dirección del recurso al que se está accediendo. La URL generalmente incluye el esquema (por ejemplo, "http" o "https"), el nombre de dominio (por ejemplo, "www.ejemplo.com") y la ruta del recurso (por ejemplo, "/pagina.html").

3. **Cabeceras (Headers)**: Las cabeceras proporcionan información adicional sobre la solicitud, como el tipo de contenido que se acepta, la información de autenticación, la información del agente de usuario (navegador) y más. Las cabeceras son clave para la negociación de contenido y la configuración de la solicitud.

4. **Cuerpo de la solicitud (Body)**: Algunas solicitudes, como las de tipo POST o PUT, pueden incluir datos adicionales en el cuerpo de la solicitud. Esto se utiliza para enviar información, como formularios, datos de carga, JSON, XML, etc.

Una vez que se envía una solicitud HTTP desde un cliente (como un navegador web), el servidor web recibe la solicitud y la procesa. Luego, el servidor puede enviar una respuesta HTTP al cliente, que contiene la información solicitada (por ejemplo, una página web, datos JSON, un archivo, etc.) o un código de estado para indicar el resultado de la solicitud (por ejemplo, 200 para éxito, 404 para recurso no encontrado, 500 para error del servidor, etc.).

Las solicitudes HTTP son fundamentales en la comunicación entre clientes y servidores en la web, y son la base de la mayoría de las interacciones que ocurren en internet, como cargar páginas web, enviar datos a través de formularios, consumir servicios web, y más.
