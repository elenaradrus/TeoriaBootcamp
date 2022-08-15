![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Primeros pasos con JavaScript

El papel principal de JavaScript simple usado en Front es gestionar eventos y dar funcionalidades sin entrar en el ámbito del Back.

## Ejemplo 1: Dentro de los elementos HTML

Vamos a ver un primer ejemplo usando JS y el evento más usado, onclick. La idea es que cuando se detecte, por parte del usuario, la pulsación del botón va a aparecer un mensaje en una ventana emergente: 

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Primer ejemplo JS</title>
</head>
<body>
    <button onclick="alert('Hola Mundo')">Saludar</button>
</body>
</html>

```

Como podemos ver estamos usando una sentencia JS inmersa dentro del propio HTML, esto es análogo a lo que hemos hecho con la etiqueta style en CSS.

## Ejemplo 2: Dentro de la etiqueta script HTML

Ahora vamos a darle otra vuelta y vamos a colocar nuestro código JavaScript dentro de la etiqueta script, de manera similar a lo que sucede con la etiqueta style, esto modifica el comportamiento del programa, como vas a poder ver

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>
        alert('Hola Mundo');
    </script>
</body>
</html>

```
La etiqueta script puede encontrarse en el head o en el body, depende de nuestras necesidades.

El problema de este ejemplo es que el alert no se ejecuta bajo demanda.


## Ejemplo 3: En un fichero externo

Ahora vamos a pasar el código JavaScript a un fichero externo con extensión js y a dejar tanto el HTML como el JS en el mismo directorio, para simplificar el ejemplo:

1. index.html: 

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script src="script.js"></script>
</body>
</html>

```

2. script.js 

```javascript

    alert('Hola Mundo');

```
El problema de este ejemplo es que el alert no se ejecuta bajo demanda de nuevo.

## Ejemplo 4: En un fichero externo con función y onclick

En este caso, vamos a solucionar el problema y volver a permitir que el alert aparezca al pulsar el botón.

1. index.html: 

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="script.js"></script>
</head>
<body>
    <button onclick="saludo();">Saludar</button>
</body>
</html>

```

2. script.js

```javascript

function saludo(){
    alert('Hola Mundo');
}

```

### Ejercicio: 
- Realiza una página en HTML, que disponga de dos botones, uno de ellos tendrá el texto "Saludar" y al pulsarlo nos indicará "Hola!!"; el segundo tendrá el texto "Despedir", al pulsarlo nos dirá "Adiós!!". Para dar funcionalidad a los botones debes usar JavaScript.


