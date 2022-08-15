![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Ampliación de EJS 

Vamos a ver esto con un ejemplo: 

**Pasos:**

1. Crea un nuevo proyecto node e instala **express y ejs**

2. Crea los siguientes ficheros: 

**index.ejs:** 

```HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejemplo EJS</title>
</head>
<body>
    Esto es un ejemplo EJS 
</body>
</html>

```

**server.js:**

```javascript 

    const express = require("express");

    const app = express();
    app.set('views', '.');
    app.set('view engine', 'ejs');

    app.get('/', function(req, res){    
        res.render('index.ejs');
    });
    app.listen(3000);

```

### <%

Se usa para ejecutar código js en HTML que del que no queremos "extraer valores", por ejemplo ejecutar un bucle for de la siguiente forma: 

```HTML

    <% for(let i = 0 ; i < 3 ; i++)  { %>
        <p>ejs is easy</p>
    <% } %>

```

Añade este código al body de tu index.ejs y pruébalo

### <%= 

Se usa para valores calculados, veamos y probemos el siguiente ejemplo: 

```HTML

    <%for(let i = 0; i < 3; i++) {%>
        <ul>
            <li> <%= i + 1  %></li>
        </ul>
    <%}%>

```

### <%-
Se usa para los includes, como ya hemos visto en la [CLASE_22](../clase22/clase22_2.md)

### <%#
Usado para añadir comentarios

### Ejemplo Tabla
Podemos renderizar una vista con una tabla extrayendo los datos de la misma del Backend.

```HTML

<table class="table">
        <thead>
           <tr>
            <th>Número.</th>
            <th>Etiquetas</th>
           </tr>
        </thead>
        <tbody>
         <% tabledata.forEach((e) => { %>
           <tr>
             <td><%=e.col1%></td>
             <td><%=e.col2%></td>
           </tr>
         <% }) %>
        </tbody>
      </table>

```

Recuerda pasarle a la vista el JSON que contiene los datos de la tabla. Edita tu server añadiendo el JSON y modificando el render de la vista: 

```javascript

    let tableItems = [
        {col1:'1',col2:'<%= %>'},
        {col1:'2',col2:'<%- %>'},
        {col1:'3',col2:'<% %>'},
        {col1:'4', col2: '<% %>'}
    ];

    ...

    res.render('index.ejs', {tabledata: tableItems});

```

[DOCUMENTACION_EJS](https://ejs.co/#docs)





