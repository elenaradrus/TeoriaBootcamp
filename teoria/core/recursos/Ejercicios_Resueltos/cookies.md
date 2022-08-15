![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Cookies Resueltos

- CSS: 
```css
body{

    font-family: 'Montserrat', sans-serif;
font-family: 'Open Sans', sans-serif;
font-family: 'Raleway', sans-serif;
font-family: 'Roboto', sans-serif;
}
section {
    display: flex;
    align-items: center;
    text-align: center;
    flex-direction: column;
    justify-content: center;
}

#cookie-advisor {

    background-color: rgb(0, 0, 0);
    padding: 2%;
    color: white;
}

button {

    padding: 2%;
    background-color: red;
    color: white;
    border-radius: 12px;
    font-size: 1rem;
    margin: 2%;
}

.scale-in-center {
    animation: scale-in-center .5s cubic-bezier(.25, .46, .45, .94) both
}

@keyframes scale-in-center {
    0% {
        transform: scale(0);
        opacity: 1
    }

    100% {
        transform: scale(1);
        opacity: 1
    }
}

```
- HTML:

```HTML 
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AVISO DE COOKIES</title>
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200&family=Open+Sans:wght@300&family=Raleway:wght@300&family=Roboto:wght@300&display=swap"
        rel="stylesheet">
</head>

<body>

    <section>
        <div id="cookie-advisor" class="scale-in-center">
            Utilizamos cookies propias y de terceros para obtener datos estadísticos de la navegación de nuestros
            usuarios y
            mejorar nuestros servicios. Si acepta o continúa navegando, consideramos que acepta su uso. Puede cambiar la
            configuración u obtener más información aquí .
            <br>
            <button onclick="saveCookie();">Aceptar</button>
        </div>

     </section>
     <script src="script.js"></script>
</body>

</html>

```

- JS: 
```javascript 

let dividirCookie = document.cookie.split("=");

if (dividirCookie[0] == "acceptcookie" && dividirCookie[1] == "true") {

 
  document.getElementById("cookie-advisor").style.display = "none";
} else {
  document.getElementById("cookie-advisor").style.display = "block";
}

function saveCookie() {
  var inFifteenMinutes = new Date(new Date().getTime() + 1 * 60 * 1000);

  console.log(inFifteenMinutes)
  let cookies = `acceptcookie=true;expires=${inFifteenMinutes} UTC;  path=/`;

  document.cookie = cookies;

 
}

```