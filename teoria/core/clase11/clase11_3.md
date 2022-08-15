![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Recursividad
Un problema de naturaleza recursiva es aquel que usa el propio problema para obtener una solución.

El ejemplo más claro es el factorial: 
```
    5! = 5 * 4!
    4! = 4 * 3!
    3! = 3 * 2!
    2! = 2 * 1!
    1! = 1 * 0!
    0! = 1 -> esta es la condición de parada, no existe el factorial de un 
    número negativo

    Si desarrollamos esto queda algo así: 

    5! = 5 * 4! = 5 * (4 * 3!) = 5 * (4 * (3 * 2!)) = 5 * (4 * (3 * (2 * 1!)))
    = 5 * (4 * (3 * (2 * (1 * 0!))))) = 5 * (4 * (3 * (2 * (1 * 1)))))

    o lo que es lo mismo: 

    5! = 5 * 4 * 3 * 2 * 1

```

En Javascript esto se resuelve con una función que se llama a sí misma y que empieza indicando la condición de parada de la recursividad, algo como esto: 

```Javascript

   function factorial(n){
        if(n == 0){
            return 1;
        }else{
            return n * factorial(n-1);
        }
    }

    console.log(factorial(5));

```

## Ejercicios
1. Realiza la serie de fibonacci (1, 1, 2, 3, 5, 8, 13...) usando una función recursiva en Javascript
2. Realiza la suma de todos los elementos de un array numérico, usando una función recursiva en Javascript

