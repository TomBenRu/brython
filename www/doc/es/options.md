Opciones de la función `brython()`
----------------------------------

Para ejecutar scripts Python en la página, deberás llamar a la función `brython()`
cuando se cargue la página.

`<body onload="brython(`*[options]*`)">`

*options* puede ser un número entero, en este caso indicará el nivel de depuración a usar:

- 0 (valor por defecto) : sin depuración. Usa esta opción cuando la aplicación
  ya ha sido depurada, aumentará ligeramente la ejecución del código
- 1 : los mensajes de error se muestran en la consola del navegador (o a un
  lugar determinado mediante `sys.stderr`)
- 2 : la traducción de código Python a Javascript se muestra en la consola del
  navegador
- 10 : la traducción del código Python y de los módulos importados se mostrará
  en la consola del navegador

*options* puede ser un objeto Javascript, sus palabras clave pueden ser:

- *debug* : nivel de depuración (ver más arriba).
- *static\_stdlib\_import* : booleano, indica si, para importar módulos o
  paquetes de la librería estándar, se debería usar la tabla estática de mapeo en el script
  **stdlib_paths.js**. El valor por defecto es `true`.
- *pythonpath* : una lista de rutas (*paths*) donde se debería buscar a los
  módulos importados.
- *ids* : por defecto, la función `brython()` ejecuta todos los scripts de la
  página. Esta opción permite especificar una lista de elementos con determinada
  `id` (atributo `id` de una etiqueta HTML) cuyo contenido de texto pueda ser
  ejecutado como código Python
- *ipy_id*: similar a *ids*. Ver [brythonmagic](https://github.com/kikocorreoso/brythonmagic)
  para más información.
- *indexedDB* : especifica si el programa puede usar la base de datos indexedDB
  para almacenar una versión compilada de los módulos localizados en __brython_stdlib.js__
  o __brython_modules.js__. El valor por defecto es `true`.

Ejemplo de uso de las opciones de la función `brython`:
-------------------------------------------------------

>    brython({debug:1, ids:['hello']})

ejecutará el contenido del elemento con id "hello" y el nivel de depuración será 1.
