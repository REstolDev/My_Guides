<div align="center">

    # APUNTES JS

</div>

### MENÚ

- [MENÚ](#menú)
- [CALLBACK](#callback)


### CALLBACK

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