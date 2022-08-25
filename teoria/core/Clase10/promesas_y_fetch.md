![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Promesas
Una promesa es un objeto que representa la terminación o el fracaso de una operación asíncrona. Una promesa representa un valor que puede estar disponible ahora, en el futuro, o nunca.

Una Promesa se encuentra en uno de los siguientes estados:

- pendiente (pending): estado inicial, no cumplida o rechazada.
- cumplida (fulfilled): significa que la operación se completó satisfactoriamente.
- establecida (settled): se ha cumplido o se ha rechazado ("en ello").
- rechazada (rejected): significa que la operación falló.

Como los métodos `Promise.prototype.then()` y `Promise.prototype.catch()` retornan promesas, éstas pueden ser encadenadas. Podríamos decir que las promesas hacen uso de la recursividad.

Vamos a ver ejemplos en pseudocódigo: 
- En el siguiente ejemplo tenemos una función **crearArchivoAsync** que genera a partir de una configuracion (parámetro) un archivo, si lo hace de manera exitosa debemos llamar a **exitoCallback** y si no a **falloCallback**. El problema es que no podemos controla el momento en el que se llaman usando el paso de parámetros tradicional.

```Javascript 

    function exitoCallback(resultado) {
        console.log("Archivo creado en la ruta " + resultado);
    }

    function falloCallback(error) {
        console.log("Error generando archivo " + error);
    }

    crearArchivoAsync(configuracion, exitoCallback, falloCallback);

```

La solución a esto, entre otras, es usar las promesas para asegurarnos de que la función crearArchivoAsync ha finalizado y podemos llamar a nuestras funciones de exito o fallo como corresponde y cuando corresponde.

La solución sería algo como: 

```Javascript

    const promesa = crearArchivoAsync(configuracion);
    promesa.then(exitoCallback, falloCallback);

    //crearArchivoAsync(configuracion).then(exitoCallback, falloCallback);

```

A diferencia de las funciones callback pasadas al "viejo estilo", una promesa viene con algunas garantías:

- Las funciones callback nunca serán llamadas antes de la terminación de la ejecución actual del bucle de eventos de JavaScript.

- Las funciones callback añadidas con then() incluso después del éxito o fracaso de la operación asíncrona serán llamadas como se mostró anteriormente.

- Múltiples funciones callback pueden ser añadidas llamando a then() varias veces. Cada una de ellas es ejecutada una seguida de la otra, en el orden en el que fueron insertadas.

- Una de las grandes ventajas de usar promises es el encadenamiento, ilustrado a continuación.

Como ya hemos dicho then() devuelve una promesa, es por esto que se pueden encadenar. 

Ejemplo:

```Javascript

    const promesa = hazAlgo();
    const promesa2 = promesa.then(exitoCallback, falloCallback);
    
    //const promesa2 = hazAlgo().then(exitoCallback, falloCallback);

```
Esta segunda promesa (promesa2) representa no sólo la terminación de hazAlgo(), sino también de exitoCallback o falloCallback que pasaste, las cuales pueden ser otras funciones asíncronas devolviendo una promesa. Cuando ese es el caso, cualquier función callback añadida a promesa2 se queda en cola detrás de la promesa devuelta por exitoCallback o falloCallback.

Básicamente, cada promesa representa la terminación de otro paso (asíncrono o no) en la cadena.

En el pasado, hacer varias operaciones asíncronas en fila conduciría a algo como esto: 

```Javascript

    hazAlgo(function(resultado) {
        hazAlgoMas(resultado, function(nuevoResultado) {
            hazLaTerceraCosa(nuevoResultado, function(resultadoFinal) {
                console.log('Obtenido el resultado final: ' + resultadoFinal
            }, falloCallback);
        }, falloCallback);
    }, falloCallback);

```

Con el uso de promesas el pseudocódigo anterior, se convierte en: 

```Javascript

    hazAlgo().then(function(resultado) {
        return hazAlgoMas(resultado);
    })
    .then(function(nuevoResultado) {
        return hazLaTerceraCosa(nuevoResultado);
    })
    .then(function(resultadoFinal) {
        console.log('Obtenido el resultado final: ' + resultadoFinal);
    })
    .catch(falloCallback);

```
Y esto es claramente más sencillo de diseñar codificar y entender.

Veamos ahora un ejemplo con código Javascript válido: 

```Javascript

    var promise = new Promise(function(resolve) {
    
        function sayHello() {
            resolve('Hello World!');
        }
    
        setTimeout(sayHello, 10000);
    
    })

    console.log(promise);
    
    promise.then(function(message) {
        console.log(message) 
    })

```
[INFO_SETTIMEOUT](https://www.w3schools.com/jsref/met_win_settimeout.asp)


## fetch()
Consume una API y devuelve una promesa.

Veamos un ejemplo: 

```Javascript

    fetch('https://api.github.com/users/daviniathebridge')
            .then(res=>res.json())
            .then(json=>console.log(json));

```

## Ejercicio
- ¿Quieres saber mi información? Aquí la tienes.
Para este ejercicio vamos a utilizar la API de usuarios de GitHub, la cual tiene esta URL: https://api.github.com/users/{username}. {username} es el nombre del usuario en GitHub, por lo que si quieres buscar a cualquier usuario, solo tienes que ponerlo en la url. Por ejemplo, https://api.github.com/users/daviniathebridge. Si ponéis esta URL en una nueva pestaña del navegador podréis observar qué datos nos devuelve el API.

Lo primero que haremos será crear un input de tipo texto y un botón para buscar. El usuario escribirá en el input el nombre de usuario de GitHub que quiera buscar. Después crearemos una función que se ejecute cuando se pulse el botón buscar y que contenga una petición a la API para obtener información de ese usuario y así mostrarla en nuestra página:

Lo que queremos que se imprima por consola será:

- nombre
- número de repositorios
- avatar (imagen)

Si ya has obtenido toda la información, utiliza las herramientas del arbol DOM para que esta información aparezca en la pantalla.