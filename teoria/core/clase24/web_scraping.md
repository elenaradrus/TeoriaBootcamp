![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png "logotipo de The Bridge")

# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Web Scraping

## [Scraping](https://www.digitalocean.com/community/tutorials/how-to-scrape-a-website-using-node-js-and-puppeteer-es)

La extracción de datos de la web (web scraping) es un proceso que automatiza la recopilación de datos de Internet. En general, conlleva la implementación de un rastreador (crawler) que navega por la web de forma automática y extrae datos de páginas seleccionadas.

![Scraping](../../../assets/core/clase24/scraping1.jpeg)


Hay muchos motivos por los cuales se puede querer utilizar este proceso:

- **Motores de búsqueda:** _Google, Yahoo, Bing, DuckDuckGo, etc.

- **Comparación de precios en tiendas.** _Metabuscadores como (Trivago, Rastreator, Atrápalo...)

- **Portales de empleo.**

- Aplicaciones que **requieran datos** públicos de terceros.

- **Reunir datos**  de contacto de empresas o personas a partir de sitios como linkedin.com 

- **Hacer estudios de mercado**:  Para monitorizar a la competencia.

- **Extraer información de foros.**

- **Reunir información** \*Para testear/entrenar modelos de **_Machine Learning_** en aquellos casos donde no hay suficiente cantidad de información disponible.\*

- **Reunir información para distintos tipos de research.**

---

### ¿Cómo funciona el Web Scraping?

El proceso de web scraping consta de los siguientes pasos:

**1. Solicitud-respuesta**

- Solicitar al sitio web de destino el **contenido** de una URL específica.

- Es necesario **estudiar** previamente cómo están compuestas las urls del sitio web del que queremos extraer datos.

- En respuesta se **obtiene** la información solicitada en HTML.

**2. Analizar y extraer**

- **Tomar** el HTML recibido

- Capturar el contenido deseado seleccionando los **nodos del DOM** que contengan dicho material.

**3. Limpiar y dar formato a los datos**

- **Organizar** la información obtenida en una estructura de datos (por ejemplo, un objeto JSON) para poder utilizarla de acuerdo a las necesidades del proyecto.

- Los datos limpios y estructurados se pueden **almacenar** en bases de datos, devolver en la respuesta de una API, etc.

---

### Scraping

Vamos a ir viendo por ejemplos de cómo vamos a ir aumentando la recogida y uso de los datos de otras páginas web. En nuestro caso usaremos **_[Amazon.]('http:/www.amazon.es')_**

#### Sacar una imagen de Amazon

**1º. Paso:**

Creamos una carpeta scraping y en la terminal inicializamos npm para el proyecto:

```

npm init -y

```

Se genera el archivo **package.json** quedando de esta forma:

```js

{
  "name": "scraping",
  "version": "1.0.0",
  "description": "Scrapear",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}

```

**2º Paso**

Instalación del paquete _puppeteer_. Este comando además de instalar Puppeteer y una versión de **Chromium**. Chromium será nuestro navegador para realizar el scraping.

```

npm install puppeteer

```

**3º Paso**

Creamos el archivo **index.js** y le pegamos el siguiente código:

```js

//? 1. Nos traemos la librería puppeteer (Resuelven en promesas)
const puppeteer = require("puppeteer");

//? 2. Obtener el navegador que vamos a utilizar.
(async () => {
  // Si headless esta en true, se oculta el chromium
  const browser = await puppeteer.launch({
    headless: false,
  });
  // Es como abrir una nueva página/pestaña en el navegador
  const page = await browser.newPage();
  // console.log("Abre el navegador");

  // Para ir a una página en concreto.
  await page.goto("http://www.amazon.es");
  // console.log("Abrió Amazon");

  // Para hacer click al mensaje de cookies.
  await page.click("#sp-cc-accept");
  // console.log("Clickeo");

  //Hacemos una foto a la página
  await page.screenshot({ path: "amazon.jpg" });
  // console.log("Hizo Foto");

  //Se cierra el navegador
  await browser.close();
})();

```

**4º Paso**

Arrancamos el Back con:

```

node script.js

```

Veremos que se nos guarda en nuestra carperta la imagen de **amazon.jpg**.

---

#### Sacar una imagen de una búsqueda

Copiamos y pegamos esto en el código. Borrándo lo anterior o creando un nuevo **archivo.js**.

```js
const puppeteer = require("puppeteer");

(async () => {
  const browser = await puppeteer.launch({
    headless: false,
  });
  const page = await browser.newPage();
  await page.goto("http://www.amazon.es");

  // Para hacer click al mensaje de cookies.
  await page.click("#sp-cc-accept");

  //Acceder al buscador de amazon por su selector. ('Selector','Búsqueda')
  await page.type("#twotabsearchtextbox", "juegos");

  //Click del botón de la búsqueda
  await page.click(".nav-search-submit input");

  //Espera (x) segundos
  // await page.waitForTimeout(1000);

  await page.screenshot({ path: "amazonJuegos.jpg" });
  // await browser.close();
})();

```

#### Sacar datos de una búsqueda

##### $$$eval$() y $eval()


```js

//document.querySelector('selector')
await page.$eval('selector', texto => texto.innerText) 
```
```js
//document.querySelectorAll('selector')
await page.$$eval("selector", (textos) => textos.map((texto) => texto.innerText));

```


Copiamos y pegamos esto en el código. Borrándo lo anterior o creando un nuevo **archivo.js**.

```js

const puppeteer = require("puppeteer");

(async () => {
  // Si headless esta en true, se oculta el chromium
  const browser = await puppeteer.launch({
    headless: false,
  });

  // Es como abrir una nueva página/pestaña en el navegador
  const page = await browser.newPage();

  // Para ir a una página en concreto.
  await page.goto("http://www.amazon.es");

  // Para hacer click al mensaje de cookies.
  await page.click("#sp-cc-accept");

  //Acceder al buscador de amazon por su selector. ('Selector','Búsqueda').
  await page.type("#twotabsearchtextbox", "libros");

  //Click del botón de la búsqueda.
  await page.click(".nav-search-submit input");

  //Esperamos que se cargue la página, ya que sino no encuentra nada.
  await page.waitForTimeout(5000);

  //Recogemos en un array de las imágenes de los libros
  const urlImg = await page.$$eval("img.s-image", (urlImg) =>
    urlImg.map((img) => img.src)
  );

  //Recogemos en un array los títulos
  const titulos = await page.$$eval("h2 span", (titles) =>
    titles.map((title) => title.innerHTML)
  );

  //Recogemos en un array el precio
  const precios = await page.$$eval(".a-price-whole", (precios) =>
    precios.map((precio) => precio.innerHTML)
  );

  const arrayLibros = [];
  for (let i = 0; i < precios.length; i++) {
    const datosLibro = {
      titulo: titulos[i],
      img: urlImg[i],
      precio: precios[i],
    };
    arrayLibros.push(datosLibro);
  }
  console.log(arrayLibros);

  // //Se cierra el navegador
  // await browser.close();
})();

```

* * *

### Ejercicios:

1. Realizar un scraping de aquellos productos que queremos obtener. Hay libre elección del tema a scrapear, puede ser juegos, películas, ropa ...

2. Se deberá obtener un json con la información y sacarlo en tarjeta por el front.
