![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Selenium 
![img](../../../assets/core/clase30/selenium.png)

Selenium Webdriver es una herramienta que permite automatizar pruebas UI (User Interface) en aplicaciones Web que no utiliza middleware (como en otras versiones de Selenium) sino controla el navegador comunicándose directamente con él, algunos de los lenguajes que son soportados son:

- Java
- C#
- Python
- Ruby
- PHP
- JavaScript

Webdriver nos ayudará a poder simular la manera en que los usuarios reales interactúan con alguna aplicación web.

[DOCUMENTACION](https://www.selenium.dev/documentation/)

## Ejemplo Google

Veamos un ejemplo simulando la navegación en Google: 

Pasos: 

1. Crea un proyecto Node

2. Inicializa el proyecto con npm init -y

3. Instala las dependencias necesarias: 

```
    npm install selenium-webdriver chromedriver geckodriver
```

4. Crea una carpeta test

5. Dentro de la carpeta test crea el siguiente javascript con el siguiete contenido: 

**test.js:**

```javascript 

const { By, Key, Builder } = require("selenium-webdriver");
require("chromedriver");


async function example() {
    //Cadena que vamos a buscar en Google
    var searchString = "Automatizar pruebas con Selenium y JavaScript";

    //Esperamos a que se abra la ventana de Chrome
    let driver = await new Builder().forBrowser("chrome").build();

    //Accedemos a google.com en una petición get
    await driver.get("http://google.com");

    //Pulsamos en el botón aceptar de la ventana que nos aparece inicialmente
    let button = await driver.findElement(By.xpath('//*[@id="L2AGLb"]/div'));
    await button.click();

    //Escribimos en la búsqueda y pulsamos enter
    await driver.findElement(By.name("q")).sendKeys(searchString, Key.RETURN);

    //Mostramos el título de la página
    var title = await driver.getTitle();
    console.log('Title is:', title);

    //Cerramos el navegador
    //await driver.quit();

}

example();

```

6. Ejecutamos la prueba
