![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

## Clase String 
Javascript dispone de una clase String que nos permite manejar cadenas de caracteres con la ayuda adicional de los métodos que nos proporciona.

Veamos ejemplos de uso: 

```Javascript

    const string1 = "Una cadena primitiva";
    console.log(string1);
    const string2 = 'También una cadena primitiva';
    console.log(string2);
    const string3 = `Otra cadena primitiva más con un ${"template"}`;
    console.log(string3);
    const string4 = new String("Un objeto String");
    console.log(string4);
    console.log(string4.valueOf);
    console.log(string4["valueOf"]);
    const nombreF = "valueOf";
    console.log(string4[nombreF]);
    console.log(string4.valueOf()); 
    console.log(typeof(string1));
    console.log(typeof(string4));
    console.log(typeof(string4[nombreF]));

```

Ejemplo: Dividir una cadena larga en líneas: 

```Javascript 
    //Método 1
    let longString = "Esta es una cadena muy larga que necesita " +
                 "que dividimos en varias líneas porque " +
                 "de lo contrario, mi código es ilegible.";
    //Método 2
    let longString2 = "Esta es una cadena muy larga que necesita \
                que dividimos en varias líneas porque \
                de lo contrario, mi código es ilegible."


```
[STRING](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String)

[STRING_TEMPLATE](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Template_literals)

## Ejercicios - Todos los ejercicios se deben realizar con objetos String
1. Solicita una cadena al usuario e indica la cantidad de veces que aparece la a en las palabras impares
2. Solicita una cadena al usuario y devuélvela invertida
Ej: "Hola, ¿qué tal estás?" -> estás? tal ¿qué Hola,



