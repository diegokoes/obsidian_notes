---
up:
  - "[[react]]"
---
# REACT -> HOOKS -> USESTATE
## DEFINITION
**Official:**
El hook **`useState`** es una función que permite agregar y gestionar un estado local dentro de un componente funcional en React. Proporciona una manera de declarar y actualizar variables cuyo valor puede cambiar con el tiempo, como el contenido de un formulario o el estado de un botón.

**Personal:**
`useState` es como una "caja" en la que puedes guardar datos que cambian mientras usas un componente. Es súper útil para hacer cosas como contar clics, abrir o cerrar menús, o guardar el texto que un usuario está escribiendo.

- - - 
## QUESTIONS

#flashcards/react

¿CÓMO SE UTILIZA USESTATE?
?
Se importa desde React y se llama dentro de un componente funcional. Devuelve un array con dos elementos:
El estado actual.
Una función para actualizar el estado.
```const [contador, setContador] = useState(0);```

¿QUÉ TIPOS DE DATOS PUEDE MANEJAR USESTATE?
?
useState puede manejar cualquier tipo de datos, como números, cadenas, arrays, objetos, e incluso valores null o undefined.

¿CUÁNDO CAMBIA EL ESTADO, QUÉ PASA?
?
Cuando actualizas el estado usando la función setEstado, React vuelve a renderizar el componente para reflejar los cambios.

¿CONST O LET PARA DECLARAR EL ARRAY QUE DEVUELVE USESTATE?
?
En el contexto de useState, no es necesario ni recomendado usar let para declarar las variables destructuradas de useState. Ya que estas variables no se reasignan, const es la opción más adecuada.

¿ES USESTATE ADECUADO PARA MANEJAR ESTADOS GLOBALES?
?
No, useState es ideal para estados locales dentro de un componente. Para estados globales, se recomienda usar Context API, Redux u otras herramientas.

¿QUÉ ES LA FORMA FUNCIONAL DE `setState`?
?
La forma funcional de setState es una manera de actualizar el estado cuando el nuevo estado depende del estado anterior. En lugar de pasar directamente el nuevo estado a la función setState, pasas una función actualizadora que recibe el estado previo (prevState) y devuelve el nuevo estado.
```js
setEstado((prevState) => {
  // Calcula y devuelve el nuevo estado basado en prevState
  return nuevoEstado;
    });
```

¿POR QUÉ USAR LA FORMA FUNCIONAL DE `setState`?
?
Acceso al estado más reciente: Garantiza que estás trabajando con el estado más actualizado, especialmente cuando las actualizaciones son asincrónicas o pueden agruparse.
Evita problemas de sincronización: React puede agrupar varias actualizaciones de estado para optimizar el rendimiento. Usar prevState evita inconsistencias.
Actualizaciones consecutivas confiables: Es esencial cuando realizas múltiples actualizaciones que dependen del estado anterior.

¿CÓMO FUNCIONA PREVSTATE?
?
Recibe el estado previo: La función que pasas a setState recibe prevState, que es el estado del componente justo antes de la actualización.
Calcula el nuevo estado: Usas prevState para calcular y devolver el nuevo estado.
React actualiza el estado: React toma el estado devuelto y actualiza el estado del componente.

¿ES NECESARIO `return` EN USESTATE FUNCIONAL?
?
Cuando utilizas la forma funcional de setState en React, es necesario que la función que pasas devuelva el nuevo estado. Esto es fundamental porque React necesita saber cuál es el nuevo estado para poder actualizarlo correctamente. Sin el return, la función no devolvería nada, y el estado no cambiaría.

- - - 
