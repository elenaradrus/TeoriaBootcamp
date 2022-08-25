![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# EJS

La idea con EJS es embeber código JS dentro del HTML, veamos esto con un ejemplo:

1. Instala express y ejs con npm.

2. Crea la siguiente estructura de directorios y ficheros en tu proyecto:

**Estructura de directorios y ficheros:**

```

    - views
    ----- partials
    ---------- footer.ejs
    ---------- head.ejs
    ---------- header.ejs
    ----- pages
    ---------- index.ejs
    ---------- about.ejs
    - package.json
    - server.js

```

3. Edita el fichero package.json y déjalo con el siguiente aspecto: 

```javascript

    {
    "name": "node-ejs",
    "main": "server.js",
    "dependencies": {
        "ejs": "^3.1.6",
        "express": "^4.17.2"
        }
    }

```

4. Inserta tu código node: 

**server.js:**

```javascript

    
    var express = require('express');
    var app = express();

    //Se le indica el motor de plantillas 
    app.set('view engine', 'ejs');

    // res.render carga la plantilla en / en este caso

    // index 
    app.get('/', function(req, res) {
        res.render('pages/index');
    });

    // about 
    app.get('/about', function(req, res) {
        res.render('pages/about');
    });

    app.listen(8080);
    console.log('8080 is the magic port');

```

5. Creamos los archivos parciales

**head.ejs:**

```HTML

    <meta charset="UTF-8">
    <title>EJS Is Fun</title>

    <!-- CSS (load bootstrap from a CDN) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.2/css/bootstrap.min.css">
    <style>
        body { padding-top:50px; }
    </style>

```

**header.ejs:**
```HTML

    <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="/">EJS Is Fun</a>
    <ul class="navbar-nav mr-auto">
        <li class="nav-item">
        <a class="nav-link" href="/">Home</a>
        </li>
        <li class="nav-item">
        <a class="nav-link" href="/about">About</a>
        </li>
    </ul>
    </nav>

```

**footer.ejs:**

```HTML

    <p class="text-center text-muted">© Copyright 2020 The Awesome People</p>

```

6. Añade al index las vistas parciales: 

**index.ejs:**

```HTML

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <%- include('../partials/head'); %>
    </head>
    <body class="container">

    <header>
        <%- include('../partials/header'); %>
    </header>

    <main>
        <div class="jumbotron">
            <h1>This is great</h1>
            <p>Welcome to templating using EJS</p>
        </div>
    </main>

    <footer>
        <%- include('../partials/footer'); %>
    </footer>

    </body>
    </html>

```

7. Crea la página de about: 

**about.ejs:**

```HTML

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <%- include('../partials/head'); %>
    </head>
    <body class="container">

    <header>
        <%- include('../partials/header'); %>
        </header>

        <main>
        <div class="row">
            <div class="col-sm-8">
                <div class="jumbotron">
                    <h1>This is great</h1>
                    <p>Welcome to templating using EJS</p>
                </div>
            </div>

            <div class="col-sm-4">
                <div class="well">
                    <h3>Look I'm A Sidebar!</h3>
                </div>
            </div>

        </div>
        </main>

        <footer>
            <%- include('../partials/footer'); %>
        </footer>

        </body>
    </html>

```

[DOCUMENTACION_EJS](https://ejs.co/#docs)