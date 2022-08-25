![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Boolean
Hasta ahora hemos hablado mucho de los booleanos como tipo de dato primitivo, debido a que son muy usados en todas las estructuras de control de flujo y en la resolución de prácticamente la totalidad de los problemas.

Javascript proporciona una **clase Boolean** que nos permite crear booleanos y disponer de dos métodos principales que nos permiten pasar a cadena y comprobar su contenido.

Además disponemos del objeto o **función Boolean** que devuelve true si una expresión es verdadera y false en caso contrario.

Vamos a ver ejemplos por serparado: 

## Ejemplos clase Boolean:

```Javascript 

   var x1 = new Boolean(false);
    var x2 = new Boolean(false);
    console.log(x1);

    if (x1) { //Dirección de memoria
        console.log("Entro en el if");
    }else{
        console.log("No entro en el if");
    }

    console.log(x1==false);
    console.log(x1===false);
    console.log(x1==true);
    console.log(x1==x2); //Direcciones de memoria
    console.log(x1===x2); //Direcciones de memoria
    console.log(JSON.stringify(x1) == JSON.stringify(x2)); //Pasamos el objeto a string y comparamos

    var x3 = false;
    if (x3) { //false
        console.log("Entro en el if");
    }else{
        console.log("No entro en el if");
    }

    console.log(x2.toString());
    var x4 = x2.toString(); //Convierte a cadena de caracteres
    console.log(x4[0] + " " +x4[1] + " " + x4.charAt(2) + " " + x4.charAt(3) + ` ${x4[4]}`);
    console.log(x2.valueOf());
    console.log(typeof(x1));
    console.log(typeof(x3));
    console.log(typeof(x2.valueOf));
    console.log(typeof(x2.valueOf()));


```


## Ejemplos objeto/función Boolean

```Javascript

    console.log(Boolean(1 > 3));    //booleano
    console.log(!!(7 > 3));         //booleano 
    console.log(new Boolean(7 > 3)); //dirección de memoria
    console.log(typeof(Boolean(1 > 3)));//booleano
    console.log(Boolean(1 > 3));    //booleano
    console.log(!!(7 > 3));         //booleano 
    console.log(new Boolean(7 > 3)); //dirección de memoria
    console.log(typeof(Boolean(1 > 3)));//booleano
    console.log(typeof(Boolean));//Función

    console.log(Boolean("Hola"));   //true
    console.log(Boolean([1,2,3]));  //true
    console.log(Boolean(new String("Hola")));   //true
    console.log(typeof(Boolean(new String("Hola"))));   //boolean

```
### Ejercicio
1. Utilizando objetos Boolean realiza un programa que indique si un array de 6 elementos solicitado al usuario se encuentra ordenado de la siguiente forma (e1 > e3, e2 < e4 y e5 = e6)

[MÁS_INFORMACIÓN_BOOLEAN](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
