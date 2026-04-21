# Laboratorio 6 - Node.js

## Descripción
En este laboratorio se corrigió un servidor con errores y luego se modificó para agregar nuevas rutas y respuestas en formato JSON.

## Parte 1: corrección del archivo original

### Errores encontrados
1. Había errores de sintaxis en la estructura general del servidor.
2. La ruta `/info` no estaba preparada correctamente para responder como se esperaba.
3. La ruta `/api/student` no leía correctamente el archivo JSON.
4. La respuesta 404 no estaba bien manejada.
5. Algunas rutas no funcionaban correctamente hasta corregir la lógica del servidor.

### Correcciones realizadas
1. Se corrigió la estructura general del servidor para que pudiera ejecutarse sin errores.
2. Se corrigió la lectura del archivo `datos.json` usando lectura asíncrona.
3. Se ajustó la respuesta de la ruta `/api/student` para devolver JSON correctamente.
4. Se corrigió el manejo de rutas no encontradas para devolver un 404.
5. Se verificó que todas las rutas respondieran correctamente desde un cliente.

## Parte 2: cambios realizados

### Ruta `/info`
Ahora responde un JSON con las propiedades:
- `mensaje`
- `curso`
- `tecnologia`

### Ruta `/saludo`
Se agregó una nueva ruta que responde con un mensaje.

### Ruta `/api/status`
Se agregó una nueva ruta que responde un JSON con:
- `ok`
- `status`
- `puerto`

### Ruta 404
Se modificó la respuesta 404 para mostrar la ruta que el usuario intentó visitar y no fue encontrada.

## Pruebas realizadas
Las pruebas se realizaron desde el navegador accediendo a `http://localhost:3000`.

### Prueba de `http://localhost:3000/`
Respuesta obtenida:
`Servidor activo`

### Prueba de `http://localhost:3000/info`
Respuesta obtenida:
Un JSON con el mensaje, el curso y la tecnología.

### Prueba de `http://localhost:3000/saludo`
Respuesta obtenida:
Un mensaje de bienvenida en texto plano.

### Prueba de `http://localhost:3000/api/status`
Respuesta obtenida:
Un JSON con el estado del servidor y el puerto 3000.

### Prueba de `http://localhost:3000/api/student`
Respuesta obtenida:
Un JSON con los datos almacenados en el archivo `datos.json`.

### Prueba de ruta inexistente
Se probó una ruta inexistente y el servidor respondió mostrando la ruta no encontrada con código 404.

## Tecnologías usadas
- Node.js
- módulo `http`
- módulo `fs/promises`
- módulo `path`