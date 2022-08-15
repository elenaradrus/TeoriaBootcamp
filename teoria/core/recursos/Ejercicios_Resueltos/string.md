![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Clase String Resueltos

1. Solicita una cadena al usuario e indica la cantidad de veces que aparece la a en las palabras impares

```javascript

let cadena = "Hola, ¿qué tal has aparcado?";

let partes = cadena.split(" ");

let cont = 0;

for(let i = 0; i < partes.length; i = i + 2){
    cont += (partes[i].split('a').length - 1);
}

console.log(cont);

```


2. Solicita una cadena al usuario y devuélvela invertida Ej: "Hola, ¿qué tal estás?" -> estás? tal ¿qué Hola,

```javascript

let cadena = "Hola, ¿qué tal estás?";

let partes = cadena.split(" ");

let reves ="";

for(let i = partes.length - 1; i >= 0; i--){
    reves+=partes[i] + " "
}

console.log(reves);


```