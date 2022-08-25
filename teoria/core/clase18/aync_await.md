![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

### Async / Await
Una función "async" es una función asíncrona, esto quiere decir que espera "await" por un resultado y sólo finaliza cuando obtenga este.

Veamos ejemplos: 

- Fetch tradicional

```javascript

    function getUser(name){
        fetch(`https://api.github.com/users/${name}`)
        .then(function(response) {
            return response.json();
        })
        .then(function(json) {
            console.log(json);
        });
    }
    getUser('daviniathebridge')

```
- Usando Async/Await.
Si usas la palabra clave `async` antes de una definición de función, luego puedes usar `await` dentro de la función. Con `await` (esperas) una promesa, la función se pausa de una forma que se bloquea hasta que la operación termine. Si la operación se completa, recibes de vuelta el valor. Si la operación falla, se arroja la excepción que disparó.

Todo esto se puede usar en combinación con promesas o simplemente con operaciones que no sean inmediatas.

```javascript

    async function getUserAsync(name) {
        let response = await fetch(`https://api.github.com/users/${name}`);
        let data = await response.json()
        return data;
    }

    getUserAsync('daviniathebridge')
    .then(data => console.log(data))
    .catch(error => console.log("hubo un error"+error));

```

- Con try/catch

```javascript

    async function getUserAsync2(name) {
        try {
            let response = await fetch(`https://api.github.com/users/${name}`);
            let data = await response.json()
            return data;    
        }
        catch (error) {
            console.log(`ERROR: ${error.stack}`);
        }
    }
    getUserAsync2('daviniathebridge')
    .then(data=>console.log(data))

```

### Ejercicio
1. Indica la secuencia de salida y explica razonadamente el siguiente código: 

```javascript
    
    const hornoListo = async () => {
        return new Promise(resolve => setTimeout(() => {
            resolve('Beep! Horno Calentado!')
        }, 3000));
    }

    const preCalentarHorno = async () => {
        console.log('Pre calentar horno.');
        const respuesta = await hornoListo();
        console.log(respuesta);
    }

    // Definir las otras funciones
    const obtenerPizzaFria = () => console.log('Obtener pizza.');
    const abrirPizzaFria = () => console.log('Abrir pizza.');
    const obtenerSartenPizza = () => console.log('Obtener sarten.');
    const ponerPizzaSarten = () => console.log('Poner pizza en el sarten.');
    const tomarRefresco = () => console.log('Tomar un refresco.');
    const mirarTV = () => console.log('Ver la televisión.');

    // Ahora llama a las funciones
    preCalentarHorno();
    obtenerPizzaFria();
    abrirPizzaFria();
    obtenerSartenPizza();
    ponerPizzaSarten();
    tomarRefresco();
    mirarTV();

```