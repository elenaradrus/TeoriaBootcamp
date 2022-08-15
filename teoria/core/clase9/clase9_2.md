![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Spread y Rest 

Son dos herramientas muy usadas por lo práctico de su naturaleza y que nos vamos a encontrar en el código moderno, es por esto que vamos a empezar por entender cómo se comportan, para poco a poco irlas incorporando en nuestro código. 

## Spread sintax o sintaxis extendida
La sintaxis extendida o spread syntax permite a un elemento iterable como por ejemplo un array o cadena ser expandido en llamadas donde se esperan cero o más argumentos o elementos (para array literales), o a un objeto ser expandido en lugares donde se esperan cero o más pares de clave-valor (para JSON).

Veamos ejemplos: 

```Javascript

    function sum(x, y, z) {
        return x + y + z;
    }

    const numbers = [1, 2, 3];

    console.log(sum(...numbers)); // 6

    console.log(sum.apply(this, [4, 5, 6])); //15

    const numbers2 = [1, 2, 3, 5];
    console.log(sum(...numbers2)); // 6

```

Otros ejemplos: 

```Javascript 

    let miArray = [2, 5, 7, 1, 9];
    let minimo = Math.min(...miArray);
    console.log(minimo);

    let misConocimientos = ['variables', 'operadores', 'estructuras de control', 'funciones'];
    let aprendido = ['spread', 'local storage'];
    let misConocimientosAmpliados = [...misConocimientos, ...aprendido, 'otra cosa más'];
    console.log(misConocimientosAmpliados);

    const user1 = { 
        name: 'Jen', 
        age: 22, 
    }; 
    
    const user2 = { 
        name: "Andrew", 
        location: "Philadelphia" 
    }; 

    const mergedUsers = {...user1, ...user2}; 
    console.log(mergedUsers) 

```

## Rest 
El operador Rest es exactamente igual a la sintaxis del operador de Spread, y se utiliza para desestructurar arrays y objetos. En cierto modo, Rest es lo contrario de spread. Spread 'expande' un array en sus elementos, y Rest recoge múltiples elementos y los 'condensa' en uno solo.

Veamos ejemplos: 

```Javascript

    function operacion (x, y, ...a) {
        return (x + y) * a.length
    }

    console.log(operacion(1,2,3,4));//6

    function sum(...a) {
        return a.reduce((previous, current) => {
            return previous + current;
        });
    }
    
    console.log(sum(1, 2, 3)); //6
    
    console.log(sum(1, 2, 3, 4)); //10

    function xyz(x, y, ...z) {
        console.log(x, ' ', y); // hey hello
    
        console.log(z); // ["wassup", "goodmorning", "hi", "howdy"]
        console.log(z[0]); // wassup
        console.log(z.length); // 4
    }
  
    xyz("hey", "hello", "wassup", "goodmorning", "hi", "howdy")
  
```


