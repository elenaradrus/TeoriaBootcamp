![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Local Storage Resueltos

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Local Storage</title>
    <script src="script.js"></script>
</head>

<body>
    <form action="">
        <label for="">Nombre: </label>
        <input type="text">
        <br>
        <br>
        <label for="">Email: </label>
        <input type="text">
        <br>
        <br>
        <label for="">Mensaje: </label>
        <input type="text">
        <input type="button" value="Añadir a contactos" onclick="guardar();">
    </form>
    <br>
    <br>
    <input type="button" value="Ver todos los contactos" onclick="mostrar();">
    <br>
    <br>
    <input type="button" value="Borrar todos los contactos" onclick="borrarContactos();">
    <br>
    <br>

    <form>
        <label for="">Email: </label>
        <input type="text" name="buscar">
        <br>
        <br>
        <input type="button" value="Borrar" onclick="borrarContacto();">
    </form>

</body>

</html>


```


```javascript 

var colors = ["yellow", "pink", "blue", "red"]

function guardar() {
    let datos = document.getElementsByTagName("input");

    let contactos = JSON.parse(localStorage.getItem("contactos"));

    if (contactos)
        contactos.push({ nombre: datos[0].value, email: datos[1].value, mensaje: datos[2].value });
    else
        contactos = [{ nombre: datos[0].value, email: datos[1].value, mensaje: datos[2].value }];

    localStorage.setItem("contactos", JSON.stringify(contactos));

    alert("Contacto Añadido");
}

const crearContacto = (nombre, email, mensaje, i) => {


    let div = document.createElement("div");
    let pNombre = document.createElement("p");
    let textNombre = document.createTextNode("Nombre: " + nombre);
    let pEmail = document.createElement("p");
    let textEmail = document.createTextNode("Email: " + email);
    let pMensaje = document.createElement("p");
    let textMensaje = document.createTextNode("Mensaje: " + mensaje);

    pNombre.appendChild(textNombre);
    pEmail.appendChild(textEmail);
    pMensaje.appendChild(textMensaje);

    div.appendChild(pNombre);
    div.appendChild(pEmail);
    div.appendChild(pMensaje);
    div.style = "background-color: " + colors[i];
    div.name = nombre;

    document.body.appendChild(div);
}

function mostrar() {
    let contactos = JSON.parse(localStorage.getItem("contactos"));
    if (contactos) {
        let divs = document.getElementsByTagName("div");
        console.log(divs.length)
        if (divs.length != 0)
            for (let i = divs.length - 1; i >= 0; i--) {
                console.log(divs[i].name)
                document.body.removeChild(divs[i]);
            }

        contactos.map((e, i) => crearContacto(e.nombre, e.email, e.mensaje, i % colors.length));
    } else {
        alert("No hay contactos que mostrar")
    }
}

const borrarContactos = () => {
    localStorage.removeItem("contactos");
}

const borrarContacto = () => {
    let email = document.getElementsByName("buscar")[0].value;
    let contactos = JSON.parse(localStorage.getItem("contactos"));
    if (contactos) {
        let i = 0;
        let encontrado = false;
        while (!encontrado && i < contactos.length) {
            encontrado = contactos[i].email == email;
            i++;
        }
        if (encontrado) {
            let borrar = JSON.stringify(contactos[i - 1]);
            contactos = contactos.filter(function (item) {
                item = JSON.stringify(item);
                return item != borrar
            });
            if (contactos.length == 0)
                localStorage.removeItem("contactos");
            else
                localStorage.setItem("contactos", JSON.stringify(contactos));
            alert("Contacto Borrado");

        } else {
            alert("El contacto que desea borrar no existe");
        }
    } else {
        alert("No hay contactos");
    }



}

``` 
