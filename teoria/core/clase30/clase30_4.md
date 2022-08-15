![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Passport

Se trata de una librería que permite realizar autenticación con diferentes métodos o estrategias, vamos a ver cómo autenticar con la estrategia local o tradicional.

## Pasos a seguir: 

1. Crea un proyecto node con un fichero server.js y ejecuta "npm init y"

2. Instala las siguientes dependencias: ejs, express, express-session, passport y passport-local.

Veamos cada una de las que no conocemos: 

- express-session: 

- [passport-local](https://www.passportjs.org/packages/passport-local/): Dependencia de passport en concreto para validaciones con usuario y contraseña.

3. El contenido del server.js es el siguiente: 

```javascript
const express = require('express');
const app = express();
const passport = require('passport');
const session = require('express-session');
//Estrategia que vamos a usar para autenticarnos
const PassportLocal = require('passport-local').Strategy;
//Sustituto de body-parser
app.use(express.urlencoded({extended: true}));
app.set('view engine', 'ejs');

app.use(session({
    secret:'secret',
    //En cada inicio de sesión se guarda la sesión aunque no haya sufrido cambios
    resave: true, 
    //La sesion se va a guardar aunque no lleve ninguna información adicional
    saveUninitialized: true
}));
//Inicializamos Passport para poder usarla en el servidor
app.use(passport.initialize());
//Hacemos llegar al servidor la configuración de sesiones de Passport
app.use(passport.session());
//Validamos usando la estrategia local
passport.use(new PassportLocal(function(username, password, done){
    if(username=="admin" && password=="admin"){
        /*done envía el resultado
            param 1: error
            param 2: resultado (cualquier valor que no sea false), representa
            al usuario que inició sesión
            param 3 (opcional): opciones de configuración
        */
        return done(null, {id: 1, name: "Administrador"}, {});
    }
    return done(null, false);
}));

//Dato normalmente numérico para identificar al usuario con la sesion 
//iniciada
passport.serializeUser(function(user, done){
    done(null, user.id);
});

//Traducción del dato serializado a el usuario que le corresponde
passport.deserializeUser(function(id, done){
    //Está hecho para un único usuario a mano, habría que hacerlo generico
    done(null, {id: 1, name: "Administrador"});
})

app.get('/', (req, res) => {
    res.send("Hola");
});

app.get('/login', (req, res) => {
    res.render("login")
});

app.post('/login', passport.authenticate("local", {
    successRedirect:"/",
    failureRedirect: "/login"
}));

app.listen(3000);


```

4. Crea un directorio views y dentro un fichero login.ejs con el siguiente contenido: 

```HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="/login" method="post">
        Email: <input type="text" name="username">
        <br>
        <br>
        Pass: <input type="password" name="password">
        <br>
        <br>
        <input type="submit" value="Login">
    </form>
</body>
</html>


```