![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Clase Array
Disponemos también de una clase Array, que nos permite crear objetos y usar métodos que nos ayudan en el día a día.

Veamos ejemplos: 

```Javascript 

    let frutas = ["Manzana", "Banana"];
    let frutasObject = new Array("Fresa", "Piña");
    let frutasObject2 = new Array(["Fresa", "Piña"]);

    console.log(frutas);
    console.log(frutasObject);
    console.log(frutasObject2);
    console.log(frutas.length);
    console.log(frutasObject.length);
    console.log(frutasObject2.length);
    console.log(frutas[0]);
    console.log(typeof(frutas));
    console.log(typeof(frutas[0]));
    console.log(typeof(frutasObject));
    console.log(typeof(frutasObject[0]));
    console.log(typeof(frutasObject2));
    console.log(typeof(frutasObject2[0]));
    console.log(typeof(frutasObject[0][1]));

```

### Métodos destacables de Array

- Map: 
Permite mapear array (construirlos según nuestras necesidades, usando funciones). 

Veamos ejemplos: 

```Javascript 

    let productos = ["patatas", "pescado", "naranjas", "manzana"];
    let resultado = productos.map(function (producto){return producto + " modificado!"});
    console.log(resultado);

    //Equivalente
    let resultado2 = productos.map((alimento) =>{return alimento + " modificado2!"});
    console.log(resultado2);

    // Usando MAP
    let arr = [1, 2, 3, 4, 5, 6, 7];
    let multiplyBy2 = n => n * 2;

    let arr2 = arr.map(multiplyBy2);
    console.log(arr2); // [2, 4, 6, 8, 10, 12, 14]


    // Antes de MAP
    let arr3 = [1, 2, 3, 4, 5, 6, 7];
    let arr4 = [];
    let multiplyBy2_2 = n => n * 2;

    for (let i = 0; i < arr.length; i++) {
        arr4.push(multiplyBy2_2(arr3[i]));
    }
    console.log(arr4); // [2, 4, 6, 8, 10, 12, 14]


```

- Filter
Crea un nuevo array filtrado por una función: 

```Javascript

    function validar(elemento) {
        return elemento >= 10;
    }
    let filtrados = [false, 22, 4, 2, null, "Bye", 31].filter(validar);
    console.log(filtrados);

    //Equivalente 
    let filtrados2 = [false, 22, 4, 2, null, "Bye", 31].filter((elemento) => {return elemento<10});
    console.log(filtrados2);


```

- Reduce
Aplica una función a un acumulador y a cada valor de un array para reducirlo a un único valor. 

En este ejemplo, se hace la suma de todos los elementos del array.

```Javascript

   // Antes de REDUCE
    let lista = [2,-1,1,3,5,8];
    let acumulacion = 0;

    for (let i = 0; i < lista.length; i++) {
        acumulacion += lista[i];
    }
    console.log(acumulacion); // 18

    // Usando REDUCE
    let lista2 = [2,-1,1,3,5,8];
    let acumulado2 = lista2.reduce(function(anterior, actual){
    return anterior + actual;
    });
    console.log(acumulado2); // 18

```

## Recorrer un array con for each
Dentro de las estructuras de control de flujo disponemos de una que nos permite recorrer estructuras de datos complejas como arrays o strings

Veamos ejemplos: 

```Javascript

    let frutas = ["Manzana", "Banana", "Fresa", "Piña"];

    let frutasObject = new Array(["Cereza", "Papaya"], ["Pera", "Sandía"]);

    //forEach
    frutas.forEach(element => {
        console.log(element);
    });

    //for tradicional equivalente
    for (let i = 0; i < frutas.length; i++) {
        console.log(frutas[i]);    
    }

    //forEach
    frutasObject.forEach(element => {
        console.log(element);
    });

    //for tradicional equivalente
    for (let i = 0; i < frutasObject.length; i++) {
        console.log(frutasObject[i]);    
    }

    //forEach
    frutasObject.forEach(element => {
        element.forEach(element2 => {
            console.log(element2);
        });
    });
    
    //for tradicional equivalente
    for (let i = 0; i < frutasObject.length; i++) {
        for (let j = 0; j < frutasObject[i].length; j++) {
            console.log(frutasObject[i][j]);
        }
    } 

    //forEach 
    frutasObject.forEach(element => {
        element.forEach(element2 => {
        for(l of element2){
            console.log(l);
        }
        console.log("Fin Fruta");
        });
    });

    //for tradicional equivalente
    for (let i = 0; i < frutasObject.length; i++) {
        for (let j = 0; j < frutasObject[i].length; j++) {
            for (let k = 0; k < frutasObject[i][j].length; k++) {
                console.log(frutasObject[i][j][k]);
            }
            console.log("Fin Fruta");
        }
    }

```

## Ejercicios 
1. Crea un array de dos dimensiones (matriz) que contenga números y cadenas solicitados al usuario, muestra por pantalla los elementos cadena que se encuentren en posiciones fila par y columna impar

Ej: 
```
1       Hola      3
Adiós   3         2   -> Muestra Hola y Manzana
4       Manzana   5
 

```

2. Crea un array a partir de las siguientes instrucciones: 
- El tamaño es solicitado al usuario
- Elemento1: 1
- Elemento2: 1
- ElementoN: ElementoN-1 + ElementoN-2

3. Solicita al usuario un array de máximo 10 números reales y calcula su media.


[MÁS_INFORMACIÓN_ARRAY](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array)


[CONVERSIÓN_TIPOS](https://flaviocopes.com/javascript-casting/)