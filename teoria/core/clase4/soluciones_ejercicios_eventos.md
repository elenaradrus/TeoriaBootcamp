![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Soluciones Ejercicio Eventos: 

## Display y una función

```Javascript

    function muestraOculta(num) {
        var parrafo = document.getElementById("contenidos_" + num);
        var enlace = document.getElementById("enlace_" + num);
        if (parrafo.style.display == "block" ||
            parrafo.style.display == "") {
            parrafo.style.display = "none";
            enlace.innerText = "Mostrar Contenido";
        }
        else {
            parrafo.style.display = "block";
            enlace.innerText = "Ocultar Contenido";
        }
    }
    window.onload = () => {
        var numEnlaces = document.getElementsByTagName("a").length;
        for(let i=1;i<=numEnlaces;i++){
            document.getElementById("enlace_"+i).setAttribute("onclick", "muestraOculta('"+i+"')");
        }
    }

```

## Visibility y una función

```Javascript

    function muestraOculta(num) {
        var parrafo = document.getElementById("contenidos_" + num);
        var enlace = document.getElementById("enlace_" + num);
        if (parrafo.style.visibility == "visible" ||
            parrafo.style.visibility == "") {
            parrafo.style.visibility = "hidden";
            enlace.innerText = "Mostrar Contenido";
        }
        else {
            parrafo.style.visibility = "visible";
            enlace.innerText = "Ocultar Contenido";
        }
    }
    window.onload = () => {
        var numEnlaces = document.getElementsByTagName("a").length;
        for(let i=1;i<=numEnlaces;i++){
            document.getElementById("enlace_"+i).setAttribute("onclick", "muestraOculta('"+i+"')");
        }
    }

```

## Dos funciones: 

```Javascript

    function oculta(num){
        var parrafo = document.getElementById("contenidos_" + num);
        var enlace = document.getElementById("enlace_" + num);
        parrafo.style.visibility = "hidden";
        enlace.innerText = "Mostrar Contenido";
        enlace.setAttribute("onclick", "muestra('"+num+"')");
    }
    function muestra(num){
        var parrafo = document.getElementById("contenidos_" + num);
        var enlace = document.getElementById("enlace_" + num);
        parrafo.style.visibility = "visible";
        enlace.innerText = "Ocultar Contenido";
        enlace.setAttribute("onclick", "oculta('"+num+"')");
    }
    window.onload = () => {
        var numEnlaces = document.getElementsByTagName("a").length;
        for(let i=1;i<=numEnlaces;i++){
            document.getElementById("enlace_"+i).setAttribute("onclick", "oculta('"+i+"')");
        }
    }

```

## Usando this

```javascript

    function oculta(enlace, parrafo){
      parrafo.style.visibility = "hidden";
      enlace.innerText = "Mostrar Contenido";
      enlace.setAttribute("onclick", "muestra(this,document.getElementById('"+parrafo.id+"'))");
  }
  function muestra(enlace, parrafo){
      parrafo.style.visibility = "visible";
      enlace.innerText = "Ocultar Contenido";
      enlace.setAttribute("onclick", "oculta(this,document.getElementById('"+parrafo.id+"'))");
  }
  window.onload = () => {
      var numEnlaces = document.getElementsByTagName("a").length;
      for(let i=1;i<=numEnlaces;i++){
          document.getElementById("enlace_"+i).setAttribute("onclick", "oculta(this, document.getElementById('contenidos_"+i+"'))");
      }
  }
  
```