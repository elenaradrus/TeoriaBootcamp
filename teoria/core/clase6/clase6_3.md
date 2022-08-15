![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Soluciones ejercicio fechas

## Solución de Yann

```javascript 

    let fechaDia1=parseInt(prompt('Día 1'));//3
    let fechaMes1=parseInt(prompt('Mes 1'));//1
    let meses=[31,28,31,30,31,30,31,31,30,31,30,31];
    let contadordias= 0 ;
    let contadormeses=0;
    let fechaDia2=parseInt(prompt('Día 2'));//5
    let fechaMes2=parseInt(prompt('Mes 2'));//6

    for(let i=fechaMes1-1; i<fechaMes2-1;i++){
        contadormeses=contadormeses+ meses[i];    
    }
    contadordias=contadormeses-fechaDia1+fechaDia2;
    if(contadordias==1){
        alert('Faltan '+contadordias+' día')}
    else{
        alert('Falta '+contadordias+' días')
    }

```

## Solución con varios arrays e intercambiando fechas

```javascript 
function ejercicioFechas() {
  let fecha1 = [prompt("Dime el primer día"), prompt("Dime el primer mes")]
  let fecha2 = [prompt("Dime el segundo día"), prompt("Dime el segundo mes")];
  let sumames = 0;
  const meses30 = [4, 6, 9, 11];
  function intercambiaFecha(f1, f2) {
    return [[f2[0], f2[1]], [f1[0], f1[1]]];
  }
  function ordenaFechas(f1, f2) {
    if (f2[1] == f1[1]) {
      if (f2[0] < f1[0]) {
        let fechas = intercambiaFecha(f1, f2);
        f1[0] = fechas[0][0];
        f1[1] = fechas[0][1];
        f2[0] = fechas[1][0];
        f2[1] = fechas[1][1];
      }
    } else {
      if (f2[1] < f1[1]) {
        let fechas = intercambiaFecha(f1, f2);
        f1[0] = fechas[0][0];
        f1[1] = fechas[0][1];
        f2[0] = fechas[1][0];
        f2[1] = fechas[1][1];
      }
    }
  }
  ordenaFechas(fecha1, fecha2);
  if (fecha1[1] != fecha2[1]) {
    for (let i = fecha1[1] - 1; i < (fecha2[1] - 1); i++) {
      if (i == 2) {
        sumames += 28;
      } else {
        if (i == meses30[0] || i == meses30[1] || i == meses30[2] || i == meses30[3]) {
          sumames += 30;
        } else {
          sumames += 31;
        }
      }
    }
    if (fecha1[1] == 2) {
      sumames += (28 - fecha1[0]);
    } else {
      if (fecha1[1] == meses30[0] || fecha1[1] == meses30[1] || fecha1[1] == meses30[2] || fecha1[1] == meses30[3]) {
        sumames += (30 - fecha1[0]);
      } else {
        sumames += (31 - fecha1[0]);
      }
    }
  }else{
        sumames+= fecha2[0]-fecha1[0];
  }

  alert(sumames)
  sumames = 0;
}
ejercicioFechas();

```
## Solución con funciones 

```javascript 


    function esDe30(mes) {
        var encontrado = false;
        var meses30 = [4, 6, 9, 11];
        var i = 0;
        while (i < meses30.length && !encontrado) {
            encontrado = encontrado || meses30[i] == mes;
            i++;
        }
        return encontrado;
    }

    function sumarDias(mes, resultado) {
        if (mes == 2) {
            resultado = resultado + 28;
        } else {
            if (esDe30(mes)) {
                resultado = resultado + 30;
            } else {
                resultado = resultado + 31;
            }
        }
        return resultado;
    }



    function difFechas() {
        var dia1 = parseInt(prompt("Inserta el primer día"));
        var mes1 = parseInt(prompt("Inserta el primer mes"));
        var dia2 = parseInt(prompt("Inserta el segundo día"));
        var mes2 = parseInt(prompt("Inserta el segundo mes"));


        var resultado = 0;
        if (mes1 == mes2) {
            if (dia1 < dia2) {
                resultado = dia2 - dia1;
            } else {
                resultado = dia1 - dia2;
            }
        } else {
            if (mes1 < mes2) {
                for (let i = (mes1 + 1); i < mes2; i++) {
                    resultado = sumarDias(i, resultado);
                }
                resultado = sumarDias(mes1, resultado) + dia2 - dia1;

            } else {
                for (let i = (mes2 + 1); i < mes1; i++) {
                    resultado = sumarDias(i, resultado);
                }
                resultado = sumarDias(mes2,resultado) + dia1 - dia2;
            }
        }

        alert(resultado);
    }

```
