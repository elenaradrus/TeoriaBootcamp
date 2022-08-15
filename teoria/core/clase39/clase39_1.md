![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Ejemplo Selenium en React:
Pasos que vamos a seguir: 

1. Crea un proyecto Node nuevo

2. Inicialízalo con npm init -y

3. Instala las dependencias necesarias: 

```
    npm install --save selenium-webdriver chromedriver geckodriver
```

4. Crea un proyecto React y en **App.js** coloca el siguiente código: 

```javascript

import './App.css';

function App() {
  return (
    <div className="App">
      
        Nombre:
        <br />
        <input id="nombre" type="text"/>
        <br />
         {/* <button id="boton" onClick= {alert('Se ha pulsado el botón ')}>Enviar</button> */}
    </div>
  );
}

export default App;


```

5. Crea  en el server el directorio test y dentro: 

**test.js**
```javascript

const { By, Key, Builder } = require("selenium-webdriver");
require("chromedriver");


async function example() {
    
    var nombre = "Davinia";

    let driver = await new Builder().forBrowser("chrome").build();
    await driver.get("http://localhost:3000");

    await driver.findElement(By.xpath('//*[@id="nombre"]')).sendKeys(nombre, Key.RETURN);
    //await driver.findElement(By.xpath('//*[@id="boton"]')).click();

    //Cerramos el navegador
    //await driver.quit();
}

example();

```

6. Ejecuta tu aplicación de React: npm start

7. Ejecuta tus pruebas con Selenium: node .\test\test.js
