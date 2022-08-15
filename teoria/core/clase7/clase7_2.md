![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Formas Alternativas de Condicional Simple

## Operador Ternario (?)
Este operador representa un "if else comprimido". 

Sintaxis: 

```Javascript 

    condición ? codigoTrue : codigoFalse

```

La mejor manera de verlo es con ejemplos: 

```Javascript

    var n = 0;
    n == 7 ? alert("Es igual a 7"):alert("No es igual a 7");

    var stop = false;
    var edad = 15;
    while (!stop){
        edad < 18 ? (alert("Tienes "+edad),edad++): (alert("Ya eres mayor de edad"),stop=true)
    }

```

## else if 
Hasta ahora hemos anidado los if en los else cuado queremos encadenar condiciones, pero hay otro modo de tratar los else que contienen  un if; este modo nos recuerda a los switch.

Veamos un ejemplo: 

```Javascript

    var n = parseInt(prompt("Inserta un número"));

    if(n % 2 == 0){
        alert("Es múltiplo de 2");

    }else if(n % 3 == 0){
        alert("Es múltiplo de 3");
    }else{
        alert("No es múltiplo de 2 ni de 3 ");
    }

```
