![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Expresiones regulares 
Se entiende por Expresión Regular a la forma compacta de representar los lenguajes. Por lo cual a partir de la expresión regular podemos pasar directamente a su automáta y viceversa.

Es un equivalente algebraico para un automata: 

-  Utilizado en muchos lugares como un lenguaje para describir patrones en texto que son sencillos pero muy utiles.
- Pueden definir exactamente los mismos lenguajes que los automatas pueden describir: Lenguajes regulares.
- Ofrecen algo que los automatas no: Manera declarativa de expresar las cadenas que queremos aceptar.
 
Nosotros no vamos a programar autómatas, pero nuestros programas van a usar la expresiones regulares para definir (de forma declarativa) patrones de texto que nos permitan validar, buscar o reemplazar datos, ya que las expresiones regulares definen, como hemos dicho lenguajes y esto a nivel práctico y para lo que lo vamos a usar se reduce a: 

- Definir los caracteres aceptados
- Definir el órden de los mismos aceptado

Este tema es largo y complejo, pero nosotros lo vamos a ver, tratar y usar a nivel básico.
Debe quedar claro que si se van a usar expresiones regulares complejas o a nivel de programación avanzada, se debe profundizar en este tema.

Veamos la sintaxis básica de una expresión regular, cuando usemos la clase RegExp de JS: 

```
   /patrón/

```

Lo que vamos a ver por medio de ejemplos es cómo se define el patrón.

**Ejemplos de sus usos:**
- Comandos de búsqueda (por ejemplo grep o find de UNIX)
- Sistemas de formateo de texto: Usan notacion de tipo expresion regular para describir patrones (por ejemplo validar un email o un dni con su letra)
- Generadores de analizadores-lexicos (los analizadores lexicos son parte de un compilador o de un intéprete)

**Un ejemplo inicial:**

Las expresiones regulares, como ya hemos dicho, denotan lenguajes. 
Por ejemplo, la expresion regular: 

```

   01* + 10* 

```
Denota todas las cadenas que son o un 0 seguido de cualquier cantidad de 1’s o un 1 seguido de cualquier cantidad de 0’s.

Para ver cómo funcionan las expresiones regulares, vamos a analizar un ejemplo: 

## Patrones 

Los patrones de las Expresiones Regulares están formados por elementos constantes (letras, símbolos, números o combinaciones de estos) y algunos símbolos con significado especial, que indican las condiciones que se deben cumplir en la cadena para buscar una coincidencia (o válida).

Los más comunes de estos símbolos con signidicado especial son: 
- Los corchetes [ ]
- Los paréntesis ( )
- Las llaves { }
- La barra invertida \\
- El pipe | 
- Los símbolos *, +, $, ^, ?...etc
 
Hay muchos más, pero nos bastará con algunos para empezar.

Veamos un ejemplo práctico que iremos siguiendo paso a paso y explicando cómo se ha desarrollado:

## Cédula de identidad Venezuela

Antecedentes: El documento de identidad en Venezuela empieza por V si eres Venezolano o E si eres extranjero, a continuación dispone de un -, seguido de un número entre 1 y 99 999 999.

Ejemplos: 

- Cédula válida: V-11122233
- Cédula no válida: S-33333333
- Cédula no válida: E-3333333A
- Cédula no válida: E-333333333333

Vamos a hacer un programa en JS, que usando una expresión regular diseñada por nosotros, nos permita validar la cédula en Venezuela.

Un patrón inicial de la Expresión Regular que permite validar una cédula puede ser: 

```
   	[VE]-[0123456789]{1,8}

```

Vamos a explicarlo por partes: 

Este patrón significa, en lenguaje natural, lo siguiente:

Para ser valida como cédula de identidad, la cadena suministrada debe:

- Empezar por una letra que puede ser V ó E
- Seguir con un guión simple
- Continuar con números entre el 0 y 9 (mínimo 1 digito y 8 como máximo)

Profundicemos en esto: 

**Símbolos:**

- Los corchetes **[]** indican un conjunto de caracateres, un dominio (si hablamos de teoría de conjuntos), significa que sólo los caracteres de ese conjunto pueden usarse, y no otros.

Si no se especifica la cantidad de estos caracteres, se asume que sólo se refiere a una (1) posición, un sólo carácter del conjunto. En este ejemplo, o **V o E…pero no las dos, y no puede omitirse.**

- **Seguidamente vemos un guión.** Cuando no colocamos corchetes [ ], ni otros símbolos de agrupación (que veremos luego), la presencia de un carácter significa literalmente ese carácter en esa precisa posición. Así pues en este caso, **el guión sólo representa eso, un guión “-” luego de la letra V o E.**

- Luego vemos, de nuevo **entre corchetes un conjunto de números.** Ya sabemos que representan los valores individuales que se pueden usar, en este caso, **cualquier número entre 0 y 9.** Podrían haber estado ordenados así [5432109876] y tendrían exactamente el mismo efecto. Incluso, pudiéramos usar una forma abreviada más cómoda, que es [0-9], que indica el mismo rango de valores, de 0 a 9, y donde **el guión separa el valor menor del mayor.**

En este caso el guión tiene una función específica porque esta dentro de los corchetes y separa los dos valores.

- **Las llaves indican, cuantificadores de posiciones o caracteres permitidos.** En este caso, **entre 1 y 8 caracteres**, que pueden ser cualquiera de los valores individuales del conjunto definido por los corchetes.

Tras esto que hemos visto, el patrón puede quedar también así: 

```

   [VE]-[0-9]{1,8}

```

Veamos ahora un script JS que permite validar una cédula: 

```javascript 

   const cedula    = 'V-11122233';
   const regExp    = new RegExp(/[VE]-[0-9]{1,8}/); 
   const resultado = regExp.test(cedula);
   
   console.log (resultado) 

```

Continuemos con el mismo ejemplo viendo más elementos de los patrones que nos van a permitir trabajar con Expresiones Regulares

## Modificadores o flags

Hay algunos modificadores de los patrones que se colocal al final de la barra delimitadora y tienen efecto sobre el patrón.

Veamos uno: **i**

```

   /[VE]-[0-9]{1,8}/i

```

Con este modificador le estamos indicando al método (test en este caso), que haga comparación sin tener en cuenta mayúsculas o minúsculas. Así pues, considerará como váildos: v, V, e, y E en nuestro ejemplo, lo que es muy conveniente en ciertos casos.

Veamos ahora **más símbolos**:

- ?: 0-1 ocurrencias de la expresión
- +: 1-n ocurrencias de la expresión
- *: 0-n ocurrencias de la expresión

Esto se puede llevar a nuestro ejemplo en el caso de que **la V/E y el guión no sean obligatorios** porque queramos validar cédulas que los lleven y las que no. En ese caso el patrón queda: 

```

   /([VE]-)?[0-9]{1,8}/i

```

Como podemos ver lo que sea hace es colocar la parte "opcional" entre paréntesis y ponerle una interrogación a continuación (o un * o un +, según nuestras necesidades)

Una vez que hemos llegado hasta aquí podemos seguir afinando nuestra Expresión Regular.

Por defecto, la verificación de la expresión regular se hace en cualquier parte de la cadena.

Es como si le dijéramos al programa, busca alguna coincidencia de este patrón en cualquier parte de la cadena o texto. Significa entonces que cadenas como: xxV-111111, Hola5555555mundo o v-555A, devolverían true para el método test ya que todas tienen un segmento que coincide con nuestro patrón.

Vamos a solucionar esto, ya que queremos que empiece y finalice con el formato indicado, para ello usaremos los caracteres ^ y $.

- ^: Indica que la cadena debe empezar como se le indica en el patrón, no puede haber nada antes.

El patrón quedaría: 

```

   /^([VE]-)?[0-9]{1,8}/i

```

- $: Indica que la cadena debe terminar como se le indica en el patrón, no puede haber nada después.

El patrón quedaría, ya completo: 

```

   /^([VE]-)?[0-9]{1,8}$/i

```

De este modo nos aseguramos de que la cadena que queremos validar coincide completamente con el patrón y no es parte de otra cadena .

Para terminar hablemos de la barra invertida o caracter de escape.

Este caracter **"\\"** tiene tres utilidades: 

1. Indicar que un carácter en particular debe ser tomado como un literal. Esto se usa para caracteres que tienen un significado especial dentro de las Expresiones Regulares (Ejemplo: "\(" representa al caracter "(" dentro de la Expresión Regular de forma literal)

2. Introducir elementos especiales dentro de nuestro patrón, como pueden ser tabuladores ("\t") o saltos de línea ("\n")

3. Introducir metacaracteres dentro de la Expresión Regular, vamos a ver dos: "\d" y "\w": 

- "\d": Equivale al patrón [0-9], que ya hemos visto y que nos viene muy bien para nuestro ejemplo.

- "\w": Equivale al patrón [a-zA-Z0-9_] (se pueden indicar rangos de caracteres), que indica que son válidos cualquier minúscula, mayúscula, cifra o _

Tras todo esto, podemos dejar nuestra expresión regular, como sigue: 

```

   /^([VE]-)?\d{1,8}$/i

```

Quedando nuestro ejemplo: 

```javascript

   const cedula    = 'V-11122233';
   const regExp    = new RegExp(/^([VE]-)?\d{1,8}$/i);
   const resultado = regExp.test(cedula);
   
   console.log(resultado);

```

### Ejercicios

1. Realiza un programa en JS que permita al usuario insertar una cadena y valide su formato, usando expresiones regulares. Las condiciones de la cadena son: 

- Empieza por un número impar
- Luego tiene un "(" y un "$"
- A continuación tiene hasta tres mayúsculas
- Por último una minúscula

La cadena puede estar dentro de otra.

2. Modifica el ejercicio anterior para que la cadena empiece y termine exactamente como se indica.

3. Modifica el ejercicio anterior para que las 4 letras puedan ser mayúsculas o minúsculas.

4. Realiza un formulario en el que el usuario inserte DNI, teléfono y email y valida el formato de los mismos.

- Formato DNI: 8cifras-1letra
- Formato teléfono: +34-xxxxxxxxx
- Formato email: letras@letras.3letras

Además añade la validación de la letra del DNI, que se debe corresponder con el número según el algoritmo de la policía nacional.