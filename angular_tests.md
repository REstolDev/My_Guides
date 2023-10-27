 <div style="text-align: center"> 

# ***Tests en Angular***

 ### *MENÚ*</div>

- [***Tests en Angular***](#tests-en-angular)
    - [*MENÚ*](#menú)
  - [**Ejecutar los Tests**](#ejecutar-los-tests)
  - [***Introducción Karma, Jasmine y TestBed***](#introducción-karma-jasmine-y-testbed)


## **Ejecutar los Tests**

Cuando ejecutas ng test en una aplicación Angular, estás iniciando el proceso de ejecución de pruebas que involucra a Jasmine, Karma y TestBed, entre otras herramientas. 
`ng test`
     


## ***Introducción Karma, Jasmine y TestBed*** 

1. **Jasmine**: `ng test` utiliza el marco de pruebas Jasmine para definir y estructurar tus pruebas. Jasmine proporciona las funciones y sintaxis para escribir las pruebas en un formato legible y expresivo. Las pruebas se organizan en "specs" (especificaciones) que describen el comportamiento esperado de tus componentes y servicios.

2. **Karma**: Karma es el motor que ejecuta tus pruebas en varios navegadores y entornos. Cuando ejecutas `ng test`, Karma se encarga de:

   - Iniciar un servidor de pruebas local.
   - Cargar los archivos de tu proyecto, incluyendo las pruebas y las dependencias necesarias.
   - Abrir uno o varios navegadores (configurables) para ejecutar las pruebas en ellos.
   - Registrar los resultados de las pruebas, incluyendo éxitos, fallos y errores.

3. **TestBed**: TestBed es una herramienta proporcionada por Angular que te permite configurar un entorno de prueba aislado para tus componentes. En el contexto de `ng test`, TestBed se utiliza para compilar tus componentes y servicios, lo que significa que Angular crea instancias de tus componentes y servicios en un entorno de prueba. Esto te permite probar las interacciones y el comportamiento de tus componentes en condiciones controladas.

En resumen, cuando ejecutas `ng test`, Jasmine se utiliza para definir tus pruebas, Karma se encarga de ejecutarlas en navegadores reales o virtuales, y TestBed crea el entorno de prueba para tus componentes. Esta combinación de herramientas y tecnologías facilita la escritura y ejecución de pruebas unitarias y de integración en aplicaciones Angular.