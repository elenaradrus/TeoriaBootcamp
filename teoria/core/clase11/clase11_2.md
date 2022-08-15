![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

- **.race(): Método que permite realizar una "carrera de promesas"**

```javascript   

    let p1 = new Promise(function(resolve, reject) {
        setTimeout(resolve, 400, "Promesa 1");
    });
    let p2 = new Promise(function(resolve, reject) {
        setTimeout(resolve, 200, "Promesa 2");
    });

    Promise.race([p1, p2]).then(function(value) {
      console.log(value); // "segunda" - Promesa 2 más rápida
    });

```
- **.all(): Método que permite evaluar un conjunto de promesas a la vez**

```javascript

    let error = false

    let p1 = new Promise(function(resolve, reject) {
      console.log("Promesa 1 - Iniciada");
      setTimeout(resolve, 1100, "Promesa 1 - Terminada");
    });
    let p2 = new Promise(function(resolve, reject) {
      console.log("Promesa 2 - Iniciada");
      setTimeout(resolve, 1800, "Promesa 2 - Terminada");
    });
    let p3 = new Promise(function(resolve, reject) {
      if(error){
        reject("modo error Activado");
      } else {
        console.log("Promesa 3 - Iniciada");
        setTimeout(resolve, 2900, "Promesa 3 - Terminada");
      }

    });
    let p4 = new Promise(function(resolve, reject) {
      console.log("Promesa 4 - Iniciada");
      setTimeout(resolve, 5100, "Promesa 4 - Terminada");
    });

    Promise.all([p1, p2, p3, p4]).then(function(value) {
      console.info("Promise.all -> TODAS las promesas terminadas", value)
    }, function(reason) {
      console.log("Ups...hubo algún error!", reason)
    });

```
## Ejercicios
1. Quiero un perrito, pero no se qué raza escoger, ¿me ayudas?

En este ejercicio utilizaremos la API de https://dog.ceo/dog-api/. Leyendo su documentación, deberás hacer lo siguiente: 

- Imprimir por consola la lista de razas de todos los perros. 
- Imprimir por consola una imagen random de una raza. 
- Imprimir por consola todas las imágenes de una raza concreta. 

¿Y si ahora te pidieramos que podamos poner otra raza en la url para que nos busque otras imágenes? Adapta las urls que ya tenías para que puedas pasarle argumentos.  

Recuerda que para estos ejercicios deberás utilizar fetch. Al haber conseguido que se imprima por consola, el siguiente paso será que se muestren en pantalla con las herramientas que nos ofrece el arbol DOM. 

2. Dada una lista de usuarios de github guardada en una array, utiliza 'https://api.github.com/users/${name}' para obtener el nombre de cada usuario.

- Objetivo: Usar Promise.all()
- Recordatorio: Una llamada a fetch() devuelve un objeto promesa.
- Pregunta. ¿cuántas promesas tendremos?

Hasta que no se resuelvan todas las promesas desencadenadas por cada fetch(), no se cargarán los datos.

Pasos: 
- Mapear el array y hacer un fetch() para cada usuario. Esto nos de vuelve un array lleno de promesas.
- Con Promise.all() harás que se tenga que resolver todo el proceso de peticiones a GitHub a la vez.
- Cuando Promise.all() haya terminado: 
  1. Consigue que se imprima por consola la url del repositorio de cada usuario.
  2. Consigue que se imprima por consola el nombre de cada usuario. 