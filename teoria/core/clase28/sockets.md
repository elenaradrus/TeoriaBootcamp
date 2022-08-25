![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Sockets 

Un socket es un mecanismo que permite la conexión entre distintos procesos, habitualmente se utilizan para establecer comunicaciones entre distintas máquinas que estén conectadas a través de la red.

Cuando utilizamos Sockets para comunicar procesos nos basamos en la arquitectura cliente y servidor. Así pues, estableceremos dos Sockets uno será la parte servidor y recibirá la transmisión del cliente y otro será la parte cliente que recibirá la respuesta del servidor.

Además, los sockets necesitan una ip y un puerto para que la comunicación sea en un canal sin confusión.

El concepto de Websocket se basa en esta definición y se ha llevado a las aplicaciones web.

## socket.io

![img](../../../assets/core/clase28/socketio.png)

Es una librería open source con una amplia comunidad que nos ayudará a contruir aplicaciones con conexión persitente entre cliente y servidor. Por lo que contaremos con librerías para cada lado.

El ejemplo más sencillo para ver cómo funciona es la creación de un chat, ya que necesitamos la conexión persistente entre cliente y servidor, mientras el cliente esté conectado y mediante el paso de mensajes podremos ver un poco cómo funciona esta librería y este tipo de aplicaciones.

**Pasos:**

1. Crea un proyecto e instala **express y socket.io**

2. Crea los siguientes ficheros: 

**chat.html:**

```HTML

    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>Sala de chat</title>
    <style>
        body{font-family: Arial;}
    </style>
    </head>
    <body>
    <h3>Mensajes:</h3>
    <ul id="listado-msjs">
        
    </ul>
    <div id="env-msjs">
        <input id="nuevo-msj"  placeholder="Nuevo mensaje">
        <button id="btn-msj" onclick="enviarMensaje()">Enviar</button>
    </div>
    
    <script src="http://code.jquery.com/jquery-1.11.1.js"></script>
    <script src="/socket.io/socket.io.js"></script>
    <script>
        var socket = io(); // Inicializamos socketIO en el cliente
        
        /*
        * Evento listener para el 'nuevo mensaje'
        *   Se puede ver que es el mismo evento que se envia 
        *   desde el servidor.
        * Agregamos el mensaje ingresado por el usuario a la lista.
        */
        socket.on('nuevo mensaje', function (msj) {
            $('#listado-msjs').append( $('<li>').text(msj) );
        });
        
        /*
        * Emitimos un evento de tipo 'nuevo mensaje' cada vez
        * que se presiona el botón enviar y enviamos
        * su contenido como mensaje.
        */
        function enviarMensaje() {
            socket.emit('nuevo mensaje', $('#nuevo-msj').val());
            $('#nuevo-msj').val('');
        };
    </script>
    </body>
    </html>

```

**server.js:**

```javascript

    /*
    * server.js
    */
    
    /* Librerías necesarias para crear la aplicación */
    var app  = require('express')();
    var http = require('http').Server(app);
    var io   = require('socket.io')(http);
    
    
    /*
    *  Configuramos nuestra ruta (index) principal con
    *  express para mostrar el chat
    */
    app.get('/', function(req, res) {
        res.sendFile( __dirname + '/chat.html');
    });
    
    
    /*
    *  Configuramos Socket.IO para estar a la escucha de
    *  nuevas conexiones.
    */
    io.on('connection', function(socket) {
    
        console.log('New user connected');
    
    /*
    * Cada nueva conexión deberá estar a la escucha
    * del evento 'nuevo mensaje', el cual se activa
    * cada vez que un usuario envia un mensaje.
    * 
    * @param  msj : Los datos enviados desde el cliente a 
    *               través del socket.
    */
    socket.on('nuevo mensaje', function(msj) {
        io.emit('nuevo mensaje', msj);
        console.log(msj);
    });
    
    /*
    * Imprimimos en consola cada vez que un usuario
    * se desconecte del sistema.
    */
    socket.on('disconnect', function() {
        console.log('Usuario desconectado');
    });
    
    });
    
    
    /*
    * Iniciamos la aplicación en el puerto 3000
    */
    http.listen(3000, function() {
        console.log('listening on *:3000');
    });

```

[DOCUMENTACION_SOCKET_IO](https://socket.io/)