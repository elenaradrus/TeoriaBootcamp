![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Módulos en Node

### Crear un módulo (paquete/librería)

Antes de enseñarte cómo crear módulos propios, te dejo la documentación de la versión de Node con la que estamos trabajando para que veas los módulos propios:

[DOCUMENTACION NODE](https://nodejs.org/dist/latest-v16.x/docs/api/)

Además, aquí tenemos la documentación de NPM, que iremos viendo y comentando poco a poco: 

[DOCUMENTACION NPM](https://docs.npmjs.com/)

Ahora sí, pasemos a comentar cómo podemos crear módulos y exportarlos, con ejemplos y un pequeño ejercicio: 

Lo normal es que no usemos un único fichero de javascript en el lado del servidor y para poder exportar funcionalidades de estos y poder importalos desde otro se usan las palabras reservadas **require** (ya la hemos visto y usado) y **exports**.

Para ver esto, vamos a realizar un ejemplo: 

- Crea un script llamado **calculadora.js**, en él debes incluir 4 funciones (suma, resta, mult y div) que hagan las operaciones básicas entre dos números (ojo con la división); al final de este script debes incluir líneas como la siguiente (una por función): 

```javascript

    exports.operacion = operacion;

```

Lo que nos encontramos tras el "." de la palabra reservada **exports** es la función que queremos exportar y lo que colocamos después es cómo la podemos invocar dentro del fichero que use la librería.

Ahora crea un fichero index.js y usa las funciones. Debes incluír en él una línea de código como la siguiente:

```javascript

    const calculadora = require("./calculadora.js");

```
Es importante colocar "./", debido a que el **require** busca los ficheros en el directorio de instalación de node y no en el directorio actual, por tanto debemos darle una ruta absoluta o relativa para encontrar nuestro módulo.

Ejecuta con npm start el index.js y prueba las 4 operaciones usando tu constante calculadora.

Una vez que funcione, ejecuta lo siguiente en el index.js: **console.log(calculadora);**, para que veas lo que trae la constante calculadora dentro y puedas ver todo lo exportado.

### Exportar un módulo usando module
Los pasos son los siguientes: 

1. En tu archivo **calculadora.js** crea un JSON de la siguiente forma: 

```javascript
    const calculadora = {
        suma:suma,
        resta:resta,
        mult:mult,
        div:div
    }

    //o bien 
    const calculadora = {}
    //...
    calculadora.suma = suma;
    calculadora.resta = resta;
    calculadora.mult = mult;
    calculadora.div = div;
    //...
    module.exports = calculadora;

```
**module** es un objeto que permite exportar, por medio de su método **exports**, JSON completos, funciones...etc. 

Veamos otro ejemplo, exportando una función: 

**calculadora.js:**

```javascript

    module.exports=function div(a,b){
        if(b != 0){
            return a / b;
        }else {
            return "No se puede dividir por 0";
        }
    }

    //O bien 
    function div(a,b){
        if(b != 0){
            return a / b;
        }else {
            return "No se puede dividir por 0";
        }
    }

    module.exports = div;

    //O bien
    module.exports = function(a,b) {
        if(b != 0){
            return a / b;
        }else {
            return "No se puede dividir por 0";
        }
    };
    //O bien

    module.exports = (a,b) => {
        if(b != 0){
            return a / b;
        }else {
            return "No se puede dividir por 0";
        }
    };

    //O bien 
    module.exports = div => {
        return 70/7; //Ejemplo para algo concreto
    };

```
**index.js:**

```javascript

    console.log(calculadora(70,7));
    //O bien para el último ejemplo: 
    console.log(calculadora);

```

Cuando usamos **exports.** lo que estoy exportando es una única propiedad de un JSON.

**Más información:**
- [nodejs_modules - W3schools](https://www.w3schools.com/nodejs/nodejs_modules.asp)
- [node-js-modules-create-publish](https://guru99.es/node-js-modules-create-publish/)
- [nodejs-modules - Tutorialsteacher](https://www.tutorialsteacher.com/nodejs/nodejs-modules)
- [how-to-use-module-exports-in-node-js](https://stackabuse.com/how-to-use-module-exports-in-node-js/)

