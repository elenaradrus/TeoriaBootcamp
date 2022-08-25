![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# node-fetch 

Ya hemos trabajado en JS con fetch, veamos ahora cómo hacerlo desde Node con un ejemplo sencillo.

### Fecth a la api de GitHub que ya conocemos bien

**Pasos:**
1. Instala node-fetch con npm

2. Permite que tu script se pueda ejecutar con npm start y añade al package.json la clave type y el valor module (se trata de una especificación de la librería)

3. Genera el index.js con el siguiente código

```javascript
    
    import fetch from 'node-fetch';

    fetch('https://api.github.com/users/daviniathebridge')
        .then(res => res.json())
        .then(json => console.log(json));


    //También podemos traer el HTML de una petición web: 
    fetch('https://google.com')
        .then(res => res.text())
        .then(text => console.log(text));

```

[NODE-FETCH](https://www.npmjs.com/package/node-fetch)