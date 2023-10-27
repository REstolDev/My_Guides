<div style="text-align: center"> 

# ***Patrones de diseṉo***</div>

- [***Patrones de diseṉo***](#patrones-de-diseṉo)
- [**Introducción**](#introducción)
  - [Ejemplos de código en JavaScript (JS) y TypeScript (TS)](#ejemplos-de-código-en-javascript-js-y-typescript-ts)
    - [**Singleton Pattern en TypeScript:**](#singleton-pattern-en-typescript)
    - [**Factory (Factoría) Pattern en TypeScript:**](#factory-factoría-pattern-en-typescript)
    - [**Decorator (Decorador) Pattern en TypeScript:**](#decorator-decorador-pattern-en-typescript)
    - [**Facade (Fachada) Pattern en TypeScript:**](#facade-fachada-pattern-en-typescript)
  - [En Angular](#en-angular)
    - [**Singleton Pattern en Angular:**](#singleton-pattern-en-angular)
    - [**Factory (Factoría) Pattern en Angular:**](#factory-factoría-pattern-en-angular)
    - [**Decorator (Decorador) Pattern en Angular:**](#decorator-decorador-pattern-en-angular)
    - [**Facade (Fachada) Pattern en Angular:**](#facade-fachada-pattern-en-angular)


# **Introducción**
Los patrones de diseño Singleton, Factory (Factoría), Decorator (Decorador) y Facade (Fachada) son patrones comunes en la programación orientada a objetos que se utilizan para resolver problemas específicos en el diseño de software. Aquí tienes una breve descripción de cada uno de ellos:

1. **Singleton (Singleton Pattern)**:
   - Propósito: Garantizar que una clase tenga solo una instancia y proporcionar un punto de acceso global a esa instancia.
   - Uso típico: Útil cuando solo se necesita una única instancia de una clase en toda la aplicación, como un administrador de configuración o un registro de eventos.
   - Ejemplo: Un gestor de conexiones a una base de datos.

2. **Factory (Factoría) Pattern**:
   - Propósito: Proporcionar una interfaz para crear objetos de una familia de clases relacionadas sin especificar la clase concreta.
   - Uso típico: Útil cuando se necesita abstraer la creación de objetos y permitir la flexibilidad en la elección de la implementación concreta en tiempo de ejecución.
   - Ejemplo: Una fábrica de vehículos que puede crear objetos de clases como Car (Coche), Bike (Bicicleta) o Truck (Camión) según las necesidades.

3. **Decorator (Decorador) Pattern**:
   - Propósito: Permite agregar funcionalidad adicional a un objeto existente dinámicamente sin modificar su estructura.
   - Uso típico: Útil cuando se necesita extender las capacidades de un objeto sin crear una subclase para cada posible combinación de características.
   - Ejemplo: Decorar un objeto gráfico con bordes, sombras o efectos adicionales.

4. **Facade (Fachada) Pattern**:
   - Propósito: Proporcionar una interfaz simplificada y unificada para un conjunto de interfaces más grandes y complejas dentro de un subsistema.
   - Uso típico: Útil cuando se desea ocultar la complejidad interna de un conjunto de clases y proporcionar una interfaz más simple para interactuar con ellas.
   - Ejemplo: Un sistema de gestión de archivos que proporciona una fachada para realizar operaciones de lectura, escritura y eliminación de archivos, ocultando la complejidad de las operaciones del sistema operativo subyacente.

Cada uno de estos patrones tiene su propio propósito y se utiliza en situaciones diferentes para mejorar la modularidad, la reutilización y la mantenibilidad del código. La elección del patrón dependerá de los requisitos específicos de diseño y de cómo se desee abordar un problema particular en un proyecto de desarrollo de software.

 ## Ejemplos de código en JavaScript (JS) y TypeScript (TS)

### **Singleton Pattern en TypeScript:**

```typescript
class Singleton {
  private static instance: Singleton;
  private value: number = 0;

  private constructor() {}

  public static getInstance(): Singleton {
    if (!Singleton.instance) {
      Singleton.instance = new Singleton();
    }
    return Singleton.instance;
  }

  public setValue(value: number): void {
    this.value = value;
  }

  public getValue(): number {
    return this.value;
  }
}

// Uso del Singleton
const singleton1 = Singleton.getInstance();
singleton1.setValue(10);

const singleton2 = Singleton.getInstance();
console.log(singleton2.getValue()); // Imprime 10, ya que ambos objetos apuntan a la misma instancia
```

### **Factory (Factoría) Pattern en TypeScript:**

```typescript
abstract class Vehicle {
  abstract displayInfo(): string;
}

class Car extends Vehicle {
  displayInfo(): string {
    return "This is a Car";
  }
}

class Bike extends Vehicle {
  displayInfo(): string {
    return "This is a Bike";
  }
}

class VehicleFactory {
  static createVehicle(vehicleType: string): Vehicle {
    switch (vehicleType) {
      case "car":
        return new Car();
      case "bike":
        return new Bike();
      default:
        throw new Error("Invalid vehicle type");
    }
  }
}

// Uso de la fábrica
const factory = new VehicleFactory();
const vehicle1 = factory.createVehicle("car");
console.log(vehicle1.displayInfo()); // Imprime "This is a Car"

const vehicle2 = factory.createVehicle("bike");
console.log(vehicle2.displayInfo()); // Imprime "This is a Bike"
```

### **Decorator (Decorador) Pattern en TypeScript:**

```typescript
interface Coffee {
  cost(): number;
}

class SimpleCoffee implements Coffee {
  cost(): number {
    return 5;
  }
}

class MilkDecorator implements Coffee {
  constructor(private coffee: Coffee) {}

  cost(): number {
    return this.coffee.cost() + 2;
  }
}

class SugarDecorator implements Coffee {
  constructor(private coffee: Coffee) {}

  cost(): number {
    return this.coffee.cost() + 1;
  }
}

// Uso del decorador
let coffee: Coffee = new SimpleCoffee();
console.log("Costo del café:", coffee.cost()); // Imprime "Costo del café: 5"

coffee = new MilkDecorator(coffee);
console.log("Costo del café con leche:", coffee.cost()); // Imprime "Costo del café con leche: 7"

coffee = new SugarDecorator(coffee);
console.log("Costo del café con azúcar:", coffee.cost()); // Imprime "Costo del café con azúcar: 8"
```

### **Facade (Fachada) Pattern en TypeScript:**

```typescript
// Subsistema complejo
class CPU {
  freeze() {}
  jump(position: number) {}
  execute() {}
}

// Subsistema complejo
class Memory {
  load(position: number, data: string) {}
}

// Fachada que simplifica la interacción con los subsistemas
class ComputerFacade {
  private cpu: CPU;
  private memory: Memory;

  constructor() {
    this.cpu = new CPU();
    this.memory = new Memory();
  }

  start() {
    this.cpu.freeze();
    this.memory.load(0, "BOOT_ADDRESS");
    this.cpu.jump(0);
    this.cpu.execute();
  }
}

// Uso de la fachada
const computer = new ComputerFacade();
computer.start(); // Inicia la computadora utilizando la fachada
```

Estos ejemplos muestran cómo implementar los patrones de diseño en JavaScript y TypeScript. 

## En Angular

### **Singleton Pattern en Angular:**

Para implementar el patrón Singleton en Angular, puedes crear una clase de servicio que mantenga una instancia única a lo largo de toda la aplicación. Angular proporciona la inyección de dependencias, lo que facilita la gestión de instancias de servicios únicos. Aquí hay un ejemplo:

1. Crea un servicio singleton en Angular:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class SingletonService {
  private value: number = 0;

  setValue(value: number): void {
    this.value = value;
  }

  getValue(): number {
    return this.value;
  }
}
```

2. Luego, puedes inyectar este servicio en cualquier componente o servicio que lo necesite. Angular se asegurará de que solo haya una instancia de `SingletonService` en toda la aplicación.

### **Factory (Factoría) Pattern en Angular:**

Para implementar el patrón Factory en Angular, puedes utilizar servicios para crear instancias de objetos según sea necesario. Aquí tienes un ejemplo básico:

1. Crea un servicio que actúe como una fábrica:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class VehicleFactoryService {
  createVehicle(type: string) {
    if (type === 'car') {
      return new Car();
    } else if (type === 'bike') {
      return new Bike();
    } else {
      throw new Error('Invalid vehicle type');
    }
  }
}
```

2. Luego, puedes inyectar `VehicleFactoryService` en componentes o servicios que necesiten crear instancias de vehículos.

### **Decorator (Decorador) Pattern en Angular:**

El patrón Decorator se puede aplicar en Angular de manera similar a TypeScript puro. Puedes crear clases decoradoras para extender el comportamiento de componentes, servicios o directivas.

### **Facade (Fachada) Pattern en Angular:**

Para aplicar el patrón Facade en Angular, puedes crear un servicio que actúe como una fachada para simplificar la interacción con múltiples servicios o componentes. La fachada encapsulará la lógica compleja y proporcionará una interfaz más simple para el consumo.

En resumen, Angular es un marco de trabajo que se basa en TypeScript y, por lo tanto, es compatible con la implementación de estos patrones de diseño de la misma manera que en TypeScript puro. La diferencia principal radica en cómo se integran con la estructura de una aplicación Angular, como la inyección de dependencias y la organización de servicios y componentes.