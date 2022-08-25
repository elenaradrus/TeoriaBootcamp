![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Comentarios y conversiones de tipos simples

## Comentarios
Los comentarios en Javascipt se colocan como se puede ver en el siguiente ejemplo: 

```javascript 

    // Cometario de linea
    /*
        Comentario de bloque
    */

```

## Ejemplo con conversión de tipos simple: 
Durante los ejercicios del día de hoy vas a necesitar hacer coversiones de tipos entre cadena de caracteres y números enteros o rales. 

Ejemplo: 

**index.html:**

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
        <script src="./script.js"></script>
    </body>
    </html>

```

**script.js:**

```javascript

    var n = window.prompt("Inserta un número entero: ");
    alert(n+n+2);
    n = parseInt(n);
    alert(n+n+2);
    var n2 = window.prompt("Inserta un número real: ");
    alert(n2+n2+2);
    n2 = parseFloat(n2);
    alert(n2+n2+2);

```

[MÁS_INFORMACIÓN_PARSEINT](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

[MÁS_INFORMACIÓN_PARSEFLOAT](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)