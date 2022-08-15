![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Soluciones Hexágono

## Solución José Luis

```javascript

class Hexagon {
    constructor(dimension1, dimension2) {
        this.dimension1 = dimension1
        this.dimension2 = dimension2
    }
    dibujar() {
        
        let hex = ''
        var espacios = this.dimension1 - 1
        let n = this.dimension2 - 1;
        let m = this.dimension2 - n + 1;
        // let m=1;
        for (let i = 0; i < (this.dimension2 / 2) - 1; i++) {
            for (let j = 0; j < espacios; j++) {
                hex += '-'
            }
            espacios--
            for (let j = 0; j < this.dimension1 + (i * 2); j++) {
                hex += '+'
            }
            hex += '\n'
        }
        for (let i = this.dimension2 / 2; i <= ((this.dimension1 * 2) - 1); i++) {
            for (let j = 0; j < this.dimension2 - n; j++) {
                hex += '-'
            }
            n--
            for (let j = 0; j < this.dimension2 - m; j++) {
                hex += '+'
            }
            m += 2
            hex += '\n'
        }
        return hex
    }
}
const r = new Hexagon(4, 10);
alert(r.dibujar())


```

## Solución Davinia

```javascript


    class Hexagono {
        constructor(dim1, dim2) {
            this.dim1 = dim1;
            this.dim2 = dim2;
        }
        //Otro método
        dibujar() {
            var pintar = `Dimensión 1: ${this.dim1}\nDimensión 2: ${this.dim2}\n`;
            var espacios = this.dim1 - 1;
            var inicio;
            var limite;
            for (let i = 0; i < 7; i++) {
                inicio = espacios;
                if (i < 3) {
                    limite = espacios + this.dim1 + i * 2;
                    for (let k = 0; k < espacios; k++) {
                        pintar = pintar + "  ";
                    }
                    for (let j = inicio; j < limite; j++) { //cambiar
                        pintar = pintar + "+";
                    }
                    espacios--; //cambiar
                    pintar = pintar + "\n";
                } else {
                    limite = this.dim2 - espacios;
                    for (let k = 0; k < espacios; k++) {
                        pintar = pintar + "  ";
                    }
                    for (let j = inicio; j < limite; j++) { //cambiar
                        pintar = pintar + "+";
                    }
                    espacios++; //cambiar
                    pintar = pintar + "\n";
                }
            }
            alert(pintar);
        }
    }
    const r = new Hexagono(4,10);
    console.log(r);
    console.log(r.dim1);
    console.log(r.dim2);
    r.dibujar();

```

## Código Mihai

```javascript 
class Hexagon {
    constructor(D1, D2) {
        this.D1 = D1
        this.D2 = D2
    }
    rombo() {
      //var D1 = 4;
      //D1 = Number(D1);
      //var D2 = 10;
      //D2 = Number(D2);
      var linea = ""; //aqui se almacena cada linea de codigo 
      var nespacios = (this.D2 - this.D1) / 2; //numeros de espacios que hay que pintar en cada linea
      var nsinb = 0; //numeros de sinbolos que hay que pintar
  
      //console.log(linea); 
      for (let i = this.D1; i <= this.D2; i += 2) {
        //console.log(i);
        nespacios = ((this.D2 - i) / 2)
        console.log(nespacios);
        nsinb = 0;
    
        //para pintar los espacion
        while (nespacios > 0) {
          linea += "💵";
          nespacios--;
        }
    
        //para pintar los sinbolos
        while (nsinb < i) {
          linea += "🤑";
          nsinb++;
        }
    
        //para pintar los espacion
        nespacios = ((this.D2 - i) / 2)
        while (nespacios > 0) {
          linea += "💵";
          nespacios--;
        }
        linea += "\n";
      }
    
      for (let i = (this.D2 - 2); i >= this.D1; i -= 2) {
        //console.log(i);
        nespacios = ((this.D2 - i) / 2)
        console.log(nespacios);
        nsinb = i;
    
        //para pintar los espacion
        while (nespacios > 0) {
          linea += "💵";
          nespacios--;
          //console.log(linea)
          //console.log(nespacios)
        }
    
        //para pintar los sinbolos
        while (nsinb > 0) {
          linea += "🤑";
          nsinb--;
          //console.log(linea)
          //console.log(nsinb);
        }
    
        //para pintar los espacion
        nespacios = ((this.D2 - i) / 2)
        while (nespacios > 0) {
          linea += "💵";
          nespacios--;
          //console.log(linea)
          //console.log(nespacios)
        }
        linea += "\n";
      }
      
    return linea
    }
  }
  function pintar (){
    let n1 = parseInt(document.getElementById("n1").value);
    let n2 = parseInt(document.getElementById("n2").value);
  const r = new Hexagon(n1, n2);
  alert(r.rombo())
  }

``` 