![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Solución Grid

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="grid.css">
    <title>Grid</title>
</head>
<body>
    <div class="padre">
        <div class="caja uno white"></div>
        <div class="caja dos white"></div>
        <div class="caja tres white"></div>
        <div class="caja cuatro white"></div>
        <div class="caja cinco white"></div>
        <div class="caja seis white"></div>
        <div class="caja siete white"></div>
        <div class="caja ocho white"></div>
        <div class="caja nueve white"></div>
        <div class="caja diez white"></div>
        <div class="caja once white"></div>
        <div class="caja doce white"></div>
        <div class="caja trece white"></div>
        <div class="caja catorce white"></div>
        <div class="caja quince white"></div>
        <div class="caja dieciseis white"></div>
        <div class="caja diecisiete yellow"></div>
        <div class="caja dieciocho yellow"></div>
        <div class="caja diecinueve red"></div>
        <div class="caja veinte redd"></div>
        <div class="caja veintiuno black"></div>
        <div class="caja veintidos black"></div>
        <div class="caja veintitres blue"></div>
        <div class="caja veinticuatro blue"></div>
    </div>
</body>
</html>

```

```css 


body {
  background-color: black;
}
.padre {
  width: 554px;
  height: 970px;
  display: grid;
  grid-template-columns: 10% 15% 12% 10% 23% 13% 7%;
  grid-template-rows: 8% 13% 14% 9% 6% 2% 5% 4% 6%;
}

.blue {
  background-color: rgb(2, 17, 135);
}
.padre > div {
  border: 4px solid black;
}
.red {
  background-color: rgba(176, 2, 3, 0.812);
}
.redd {
  background-color: rgb(209, 1, 1);
}
.white {
  background-color: white;
}
.yellow {
  background-color: rgba(227, 210, 6);
}

.uno {
  grid-column: 1/3;
  grid-row: 1/2;
}
.dos {
  grid-column: 3/4;
  grid-row: 1/2;
}
.tres {
  grid-column: 4/6;
  grid-row: 1/2;
}
.cuatro {
  grid-column: 6/8;
  grid-row: 1/2;
}
.cinco {
  grid-column: 1/2;
  grid-row: 2/3;
}

.diecisiete {
  grid-column: 2/3;
  grid-row: 2/3;
}

.diecinueve {
  grid-column: 3/6;
  grid-row: 2/4;
}

.veintitres {
  grid-column: 6/7;
  grid-row: 2/3;
}
.ocho {
  grid-column: 1/3;
  grid-row: 3/4;
}

.nueve {
  grid-column: 1/3;
  grid-row: 9/10;
}
.diez {
  grid-column: 3/5;
  grid-row: 8/10;
}

.veinticuatro {
  grid-column: 1/3;
  grid-row: 4/7;
}
.once {
  grid-column: 3/5;
  grid-row: 4/5;
}

.black {
  background-color: black;
}
.veintiuno {
  grid-column: 5/6;
  grid-row: 4/5;
}

.doce {
  grid-column: 5/6;
  grid-row: 5/8;
}
.trece {
  grid-column: 6/8;
  grid-row: 4/6;
}
.veintidos {
  grid-column: 3/5;
  grid-row: 5/8;
}
.catorce {
  grid-column: 6/7;
  grid-row: 3/4;
}
.quince {
  grid-column: 1/2;
  grid-row: 7/9;
}
.dieciseis {
  grid-column: 2/3;
  grid-row: 7/9;
}
.seis {
  grid-column: 7/8;
  grid-row: 3/4;
}
.siete {
  grid-column: 7/8;
  grid-row: 2/3;
}
.dieciocho {
  grid-column: 5/6;
  grid-row: 8/10;
}
.veinte {
  grid-column: 6/8;
  grid-row: 6/10;
}



```