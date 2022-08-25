![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Programación Orientada a Objetos (POO)
Para comenzar a ver este nuevo paradigma es muy importante señalar, que la Programación Orientada a Objetos amplía todos los conceptos de Programación Estructurada (con subprogramas) que hemos visto, por lo que todo lo anterior se usa, aunque a algunos de los conceptos se les cambia el nombre.

Lo primero que hay que mencionar es que se basa en la idea de la interacción del ser humano con los objetos en su día a día; esto hace que subamos un nivel de abstracción y por tanto de nuevo facilita la vida del programador, además de darle herramientas nuevas.

## Clase

Una clase en POO se define como una plantilla o definición de lo que van a ser los futuros objetos.

Pongamos un ejemplo tangible de nuestro día a día: Si quisiéramos saber qué aspecto tiene una mesa porque no supiéramos lo que es, acudiríamos al diccionario para que nos lo describiera. En el caso de la POO cuando implementamos una clase lo que estamos haciendo es describir los futuros objetos que habrá en nuestra aplicación.

Partes que componen una clase: 

- Atributos
- Métodos

Describiremos estos conceptos más adelante.

**Ejemplos:**

- En una aplicación sobre el personal de una obra, tendríamos la clase “Empleado”
- En una aplicación sobre la gestión de los recursos de una Empresa, tendríamos la clase “Activo”

## Objeto

En POO, un objeto es una "ocurrencia" o “materialización” (no es tangible en software) de una clase.

En el caso de estar programando un software la idea es que haya una clase y tantos objetos como nos haga falta.

Ejemplos: 
- En una aplicación sobre el personal de una empresa, tendríamos la clase “Empleado” y un objeto sería un empleado concreto, con nombre, apellidos y dni.

- En una aplicación sobre la gestión de los recursos de una Empresa, tendríamos la clase “Activo” y un objeto sería un activo concreto, por ejemplo una oficina en propiedad o un ordenador.

## Encapsulamiento

Es importante definir este concepto en este momento, antes de empezar a hablar de las partes que componen una clase (atributos y métodos) porque es una novedad muy potente que trae este paradigma de programación.

En POO hay tres tipos de niveles de acceso (habitualmente) a atributos y métodos y son los siguientes: 

- Público: se permite el acceso al elemento (atributo o método) desde cualquier otra clase.
- Protegido: se permite acceso al elemento (atributo o método) desde la clase que lo contiene y aquellas que heredan de ella.
- Privado: se permite acceso al elemento (atributo o método) desde la clase que lo contiene solamente

El encapsulamiento garantiza la integridad de la información que se encuentra dentro de un objeto porque usando los niveles de acceso comentados, permite acceso y modificación sólo a quién esté "autorizado”.

Esto también está relacionado con la ocultación de información, ya que si el usuario no tiene que ver o cambiar cierta información no se le permite.


## Abstracción
La abstracción consiste en aislar un elemento de su contexto o del resto de los elementos que lo acompañan. En programación, el término se refiere a centrarnos en el "¿qué hace?" más que en el ¿cómo lo hace?", es decir, tratar el diseño de aplicaciones POO como una caja negra. Lo que ha caracterizado, como hemos comentado, a la evolución de los lenguajes de programación, desde los estructurados hasta los Orientados a Objetos, ha sido el nivel de abstracción del que cada uno de ellos hace uso, siendo mucho mayor en la POO.

Desde el punto de vista de la POO expresa las características esenciales de un objeto, las cuales lo distinguen de los demás. Además de distinguir entre los objetos provee límites conceptuales, ya que como hemos hablado el encapsulamiento permite definir diversos niveles de acceso, que amplían o restringen permisos a otras partes de las aplicaciones o usuarios.

Además, genera simplicidad a la hora de diseñar e idear cómo va a ser un programa y al tratarse de clases y objetos esta simplicidad es mayor ya que el permite que el ser humano identifique los elementos de una forma rápida y sencilla.


## Atributos
Se trata de una parte fundamental de una clase y define las “partes” o características que van a tener los futuros objetos de una clase.

Nos definen cómo son los objetos.

Ejemplos: 
- Si estuviéramos programando la clase “Vehículo”, serían atributos el color o el número de ruedas.
- Si estuviéramos programando la clase “Persona”, serían atributos el dni o el nombre.

La pregunta que debemos hacernos es ¿qué partes o características componen a los objetos?

## Métodos
Se trata de subprogramas, que se encuentran dentro de una clase y describen lo que podemos hacer con los futuros objetos, es decir las funcionalidades de los futuros objetos. Es decir, se trata de bloques de código, que realizan una tarea lo más especifica posible y al que le ponemos un nombre; la particularidad es que se asocian a una clase concreta, ya que se programan dentro de ella. 

Ejemplos:
- Si estuviéramos programando la clase “Vehículo”, serían métodos arrancar, acelerar, frenar, calcular el precio…etc

- Si estuviéramos programando la clase “Persona”, serían métodos saludarle, calcular su IMC si dispusiéramos de su peso y altura…etc

La pregunta a la que debemos responder en cuanto a diseñar métodos es “¿Qué hacen los futuros objetos de esta clase?”.

## Constructor
Es el método que permite crear un objeto (pedir memoria e inicializar).

En Javascript la forma de programar clases no es tan clara y guiada como en otros lenguajes, es por esto que el resto de cuestiones las vamos a ver por medio de ejemplos.

Ejemplo 1: 

```Javascript

    class Rectangulo {
        constructor(alto, ancho) {
        this.alto = alto;
        this.ancho = ancho;
        }
    }

    var r = new Rectangulo(3,4);
    alert(r.alto+" "+r.ancho);

```

Ejemplo 2: Clases como expresiones (muy parecido a las funciones)

```Javascript

    // Anonima
    let Rectangulo = class {
    constructor(alto, ancho) {
        this.alto = alto;
        this.ancho = ancho;
    }
    };

    console.log(Rectangulo.name);
    // output: "Rectangulo"

    // Nombrada
    let Rectangulo = class Rectangulo2 {
    constructor(alto, ancho) {
        this.alto = alto;
        this.ancho = ancho;
    }
    };
    console.log(Rectangulo.name);
    // output: "Rectangulo2"

```

## Get y Set
Estos métodos permiten acceder a atributos calculados, esto se entiende mejor con un ejemplo:

```Javascript

    class Rectangulo {
        constructor (alto, ancho) {
            this.alto = alto;
            this.ancho = ancho;
        }
        // Get -> Crea un Atributo nuevo
        get altoAncho() {
            return "Alto: "+this.alto +" Ancho: "+this.ancho;
        }
        //Set
        set altoAncho(dimensiones){
            this.alto = dimensiones[0];
            this.ancho = dimensiones[1];
        }
        //Otro método
        calcArea () {
            return this.alto * this.ancho;
        }
    }

    const r = new Rectangulo(20, 10);
    console.log(r.alto); // 20
    console.log(r.ancho); // 10
    console.log(r.altoAncho); // Alto: 20 Ancho: 10

    r.altoAncho = [30, 40]; // Cambiamos alto y ancho
    console.log(r.altoAncho); // Alto: 30 Ancho: 40
    console.log(r.calcArea()); // 1200

```

Ejercicio
- Realiza con POO un programa que permita pintar en un alert (la salida en el alert se debe ejecutar al pinchar en un botón en el HTML) lo siguiente: 

```

Dimensión 1: 4
Dimensión 2: 10

    ++++
   ++++++
  ++++++++
 ++++++++++
  ++++++++
   ++++++
    ++++

```