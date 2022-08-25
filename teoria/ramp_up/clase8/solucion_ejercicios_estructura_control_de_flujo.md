![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Soluciones simples ejercicios clase 6_4 (Estructuras de control de flujo)

Se incluye solamente el código JavaScript

## Ejercicio 1
```javascript

    var n1 = prompt('Inserta un número');
    var n2 = prompt('Inserta otro número');
    var n3 = prompt('Inserta el último número');

    if(n1<=n2 && n1<n3){
    alert('El menor es ' + n1);
    }else{
    if(n2<n1 && n2<=n3){
        alert('El menor es ' + n2);
    }else{
        alert('El menor es ' + n3);
    }
    }

```

## Ejercicio 2
```javascript 

var frase = prompt('Inserta una frase').toLocaleLowerCase();
var letra = prompt('Inserta una letra').toLocaleLowerCase()[0];
//variable para contar las veces que aparece la letra en la frase
var cont = 0;
for(var i = 0; i<frase.length;i++){
  if(letra==frase.charAt(i)){
    cont++;
  }
}
alert('La letra '+ letra + 'aparece '+ cont +' veces');

```

## Ejercicio 3
```javascript 

var n1 = parseFloat(prompt('Inserta un número con decimales'));
var n2 = parseFloat(prompt('Inserta otro número con decimales'));
var op = prompt('Si quieres sumar escribe un +, si no un -');

if(op == '+'){
  alert(n1 +'+' +n2 +'='+(n1+n2));
}else{
  alert(n1 +'-' +n2 +'='+(n1-n2));
}

```

## Ejercicio 4
```javascript 

const userC = "admin";
const passC = "admin";
var user, pass;
var intentos = 3;
do{
  user =  prompt('Usuario');
  pass =  prompt('Contraseña');
  intentos--;
}while((user!=userC || pass!=passC) && intentos>0);

if(user==userC && pass==passC){
  alert('Bienvenid@');
}else{
  alert('Intentos agotados');
}

```

## Ejercicio 5
```javascript 
var letra =  prompt('Inserta una letra').toLocaleLowerCase()[0];

switch(letra){
  case 'a':
    alert(7);
    break;
  case 'b':
    alert(9);
    break;
  case 'c':
    alert(101);
    break;
  default:
    alert('Te has equivocado de letra');
}

```

## Ejercicio 6
```javascript 

var palabras = ['casa', 'perro', 'coche', 'camión', 'sol', 'hola', 'ola'];
//variable para el intercambio
var aux;
for (let i = 1; i < palabras.length; i++){
  for (let j = 0; j < palabras.length - 1; j++){
    if (palabras[j] > palabras[j+1]){
      aux = palabras[j];
      palabras[j] = palabras[j+1];
      palabras[j+1] = aux;
    }
  }
}

alert(palabras);

```

