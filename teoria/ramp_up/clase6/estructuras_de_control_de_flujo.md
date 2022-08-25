![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Estructuras de control de flujo
La ejecución de nuestro código Javascript es secuencial, de arriba a abajo y línea a línea. El orden de ejecución es lo que llamamos flujo de ejecución.

Nos podemos encontrar situaciones en las que debamos interferir en ese flujo de ejecución; para esos casos los lenguajes ponen a nuestra disposición varias herramientas, que vamos a ver a continuación: 

1. Condicional simple (if)
2. Condicional múltiple (switch)
3. Bucles: 
    1. For
    2. While
    3. Do-While

Vayamos uno por uno.

## Condicional simple (if): 
Permite ejecutar código si se cumple una condición. 

Sintaxis: 

```

    if(condición){
        codigo;
    }[else{
        codigo2;
    }]

```

El código puede ser cualquier sentencia válida en Javascript.

Ejemplo 1: 

```javascript 
    //Comprobar si el usuario acierta el 9
    const n = 9;
    var n2 = prompt("Inserta un número");
    if (n == n2) {
        alert("Has acertado el número");
    } else {
        alert("No has acertado el número");
    }

```

**Ejercicio: Indica el flujo de ejecución si el usuario acierta el número y si no**

Ejemplo 2: 

```javascript 
    //Comprobar si el usuario acierta el 9 y si lo hace, si el 9 es múltiplo de 3
    const n = 9;
    var n2 = prompt("Inserta un número");
    if (n == n2) {
        alert("Has acertado el número");
        if(n % 3 == 0){
            alert("Es múltiplo de 3");
        }
    } else {
        alert("No has acertado el número");
    }

```

Ejemplo 3: 

```javascript 

    //Comprobar si el usuario acierta el 9 y si el 9 es multiplo de 3 (a la vez)
    const n = 9;
    var n2 = prompt("Inserta un número");
    if (n == n2 && n %3 == 0) {
        alert("Has acertado el número y es multiplo de 3");
    } else {
        alert("No has acertado el número");
    }

```

Ejemplo 4: 

```javascript
    //Comprobar si el usuario acierta el 9 y si no lo acierta, si el número insertado es múltiplo de 3
    const n = 9;
    var n2 = prompt("Inserta un número");
    if (n == n2) {
        alert("Has acertado el número");
    } else {
        if (n2 % 3 == 0) {
            alert("No has acertado el número, pero has insertado un número multiplo de 3");
        }
    }

```

[IF_ELSE](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else)


## Condicional múltiple (switch):
Si necesitamos hacer varias comparaciones de igualdad, el switch es una buena manera de agruprlas y simplificar el código.

Síntaxis: 

```

    switch (expresión) {
    case valor1:
        codigo1;
        [break;]
    case valor2:
        codigo2;
        [break;]
    ...
    case valorN:
        codigoN;
        [break;]
    default:
        codigoD;
        [break;]
    }


```

Partes que componen al switch: 

1. expresión -> variable o expresión a evaluar en los case
2. case valor -> valores con los que comparamos 
3. default -> equivalente al else, si no se cumple ningún case
4. break -> Permiten terminar una vez ejecutado el código que queremos

Ejemplo: 

```javascript 

    var foo = 0;
    switch (foo) {
    case -1:
        console.log('1 negativo');
        break;
    case 0: // foo es 0, por lo tanto se cumple la condición y se ejecutara el siguiente bloque
        console.log(0)
        // NOTA: el "break" olvidado debería estar aquí
    case 1: // No hay sentencia "break" en el 'case 0:', por lo tanto este caso también será ejecutado
        console.log(1);
        break; // Al encontrar un "break", no será ejecutado el 'case 2:'
    case 2:
        console.log(2);
        break;
    default:
        console.log('default');
    }

```

[SWITCH](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/switch)

## Bucles 
Los bucles son estructuras de repetición que permiten ejecutar código más de una vez.
Disponemos de 3 bucles en Javascript, de manera básica (hay variantes algo más complejas de estos, pero las veremos más adelante)

## For 
Se usa cuando el número de repeticiones es fijo (aunque sea indeterminado porque dependa del usuario, por ejemplo).

Sintaxis:

```
    for (inicializacion/desde; condición/hasta ; incremento/decremento/de cuanto en cuanto){
        codigo
    }

```

Veamos la estructura de la cabecera o signatura: 

1. inicializacion/desde -> Inicialización de la variable que controla el bucle, nos sirve para contar las iteraciones (cada vez que se ejecuta el código).

2. condición/hasta -> Controla que la variable que lo controla tenga el valor que le indica que se para el bucle

3. incremento/decremento/de cuanto en cuanto -> Depende de si vamos contando hacia adelante o hacia atrás, es la parte del bucle que modifica el valor a la varible que lo controla

Ejemplos: 

```javascript 
    
    //Muestra los números del 0 al 9
    for (let i = 0; i < 10 ; i = i + 1) {
        console.log(i);
    }
    //Muestra los números del 1 al 10
    for (let i = 1; i <= 10 ; i = i + 1) {
        console.log(i);
    }
    //Muestra los números del 1 al 10 con operador de post incremento
    for (let i = 1; i <= 10 ; i++) {
        console.log(i);
    }
    //Muestra los números pares que hay entre 1 y 10
    for (let i = 2; i <= 10 ; i=i+2) {
        console.log(i);
    }


```

## While 
Se usa cuando el número de repeticiones depende de una condición.

Sintaxis: 

```

    while(condicion){
        codigo;
    }

```

Ejemplo: 

```javascript

    var n = 9;
    while(n > 3){
        console.log(n);
        n--; //n = n -1
    }

```

**Ejercicio: Indica el flujo de ejecución**

**Importante: Si la condición no se cumple en un while, el código no se ejecuta nunca.**

## Do-while 
Igual que el while, pero se fuerza la primera ejecución del código. Se usa en validaciones, en las que hay que pedir la información una vez y luego comprobar si cumple las condiciones.

Sintaxis: 

```
    do{
        codigo
    }(condicion);

```

Ejemplo: 

```javascript

    var n = 9;
    do{
        console.log(n);
        n--; //n = n -1
    }while(n < 7);

```


