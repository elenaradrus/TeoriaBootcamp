![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Clase Array Resueltos

2. Crea un array a partir de las siguientes instrucciones:
El tamaño es solicitado al usuario
Elemento1: 1
Elemento2: 1
ElementoN: ElementoN-1 + ElementoN-2


```javascript 

let tam = 10;

let serie = [1,1];
let iterator = serie.values();

for(let i = 0; i < tam-2; i++)
    if(i == 0 )
        serie.push(iterator.next().value + iterator.next().value);
    else    
        serie.push(serie[i] + serie[i+1])


console.log(serie);


```