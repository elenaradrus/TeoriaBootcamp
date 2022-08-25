![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Ampliación Express 

Vamos a ver algunas funcionalidades y propiedades de Express con las que ya hemos trabajado (y otras que no hemos visto) con algo más de detalle que el que hemos dedicado hasta ahora.

## Métodos

### all
Se trata de un comodín, este método captura cualquier tipo de petición HTTP en una endpoint.

Se usa para endpoints que formen parte de la lógica general de la aplicación.

**Ejemplo:**

```javascript

    app.all('/secret', function (req, res, next) {
        console.log('Accessing the secret section ...')
        next() // pass control to the next handler
    })

```

### disable
Establece un elemento de configuración booleano a falso, donde el nombre es una de las propiedades de la tabla de configuración de la aplicación. 

**Por ejemplo:**

```javascript 

    app.disable('trust proxy') //pone la propiedad a false
    
```
Esto se puede usar para indicar a nuestro servidor, que el proxy desde el que se conecta un cliente no es de confianza.

### disabled
Devuelve true si la propiedad indicada se encuentra deshabilitada.

**Siguiendo con el ejemplo anterior:**

```javascript 

    app.disabled('trust proxy') // => true

```

### enable 
Establece un elemento de configuración booleano a verdadero, donde el nombre es una de las propiedades de la tabla de configuración de la aplicación. 

```javascript 

    app.enable('trust proxy') //pone la propiedad a true
    
```

### enabled 
Devuelve true si la propiedad indicada se encuentra habilitada.

**Siguiendo con el ejemplo anterior:**

```javascript 
   
    app.enabled('trust proxy') // => true

```

### set
Permite añadir una propieda de configuración y darle un valor, más allá de los booleanos que hemos visto.

**Ejemplo:**

```javascript

    app.set('title', 'My Site') //Añade la propiedad y le da un valor de tipo string

```

### get
Este método se encuentra sobrecargado, diponemos de dos opciones:

1. Si le pasamos como parámetro el nombre de una propiedad de configuración como las que hemos visto, nos devuelve su estado: 

**Ejemplos:**

```javascript

    app.get('title') // => undefined

    app.set('title', 'My Site') //añade la propiedad
    app.get('title')  // => "My Site"

    ...

    app.disable('trust proxy')
    app.get('trust proxy') // => false

    ...

    app.enable('trust proxy')
    app.get('trust proxy') // => true

```

2. Si los parámetros son al menos dos, un string con el endpoint y una función de callback, en este caso captura las peticiones HTTP get en el endpoint indicado (lo hemos usado muchas veces)

### post, put, delete y otros
Capturan las peticiones HTTP del tipo correspondiente y los hemos usado.

### engine
Indica al servidor el motor de plantillas que vamos a usar, por ejemplo PUG o EJS, ya hemos usado engine.

**Ejemplo:** En este caso lo que estamos indicando es que cuando se detecte un html se renderice como una plantilla EJS.

```javascript 

    app.engine('html', require('ejs').renderFile)

```

### listen
Lanza el servidor en modo escucha en una ip y un puerto, si omitimos o ponemos 0 en el lugar del puerto, el SO elige un puerto arbitrario.

### use 
Asocia la función o funciones middleware en una ruta especificada: el middleware se ejecuta cuando la base de la ruta solicitada coincide con la ruta.

**Ejemplo:**

```javascript 

    app.use(function (req, res, next) {
        console.log('Time: %d', Date.now())
        next()
    })

```

[DOCUMENTACION_EXPRESS](https://expressjs.com/es/api.html#express)
