![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Ejemplos posicionamiento
Resumen de algunos elementos en bloque y en línea: 

Los elementos en línea definidos por HTML son: 

```
    a, abbr, acronym, b, br, cite, code, em, font, i, img, input, label, select,small, span, strong, sub, sup, textarea

```


Los elementos de bloque definidos por HTML son: 

```
    address, blockquote, center, dir, div, dl, fieldset, form, h1, h2, h3, h4, h5, h6, hr, menu, noscript, ol, p, pre, table, ul

```

**Ejemplo 1: relativo**

```html

<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8" />
    <title>Posicionamiento</title>
    <style type="text/css">
        #cont {
            border: 20px solid red;
            width: 400px;
            height: 300px;
            margin: 20px;
        }

        #caja {
            border: 5px double blue;
            width: 200px;
            height: 200px;
            /* Jugamos con la posición: relative/absolute */
            position: relative;
            top: 50px;
            left: 50px;
        }
    </style>
</head>

<body>
    <section>
        <div id="cont">
            <div id="caja">
                <p>Lorem ipsum dolor.</p>
            </div>
        </div>
    </section>
</body>

</html>

```

**Ejemplo 2: relativo 2**

```html

<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8" />
    <title>Posicionamiento Relativo</title>
    <style type="text/css">
        img {
            width: 20%;
        }

        img.desplazada {
            position: relative;
            top: 8em;
        }
    </style>
</head>

<body>
    <section>
        <img class="desplazada" src="img/roma.jpg" alt="Imagen genérica" />
        <img src="img/roma.jpg" alt="Imagen genérica" />
        <img src="img/roma.jpg" alt="Imagen genérica" />
    </section>
</body>

</html>

```

**Ejemplo 3: absoluto**

```html

<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8" />
    <title>Posicionamiento Relativo</title>
    <style type="text/css">
        img {
            width: 200px;
        }

        div {
            border: 2px solid #CCC;
            padding: 1em;
            margin: 1em 0 1em 4em;
            width: 300px;
        }

        div img {
            position: absolute;
            top: 50px;
            left: 50px;
        }
    </style>
</head>

<body>
    <section>
        <div>
            <img src="img/roma.jpg" alt="Imagen genérica" />
            <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. </p>
        </div>
    </section>
</body>

</html>

```
