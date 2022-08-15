![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Selectores Básicos 

## Descendente
Selecciona los elementos que se encuentran dentro de otros elementos. Un elemento es
descendiente de otro cuando se encuentra entre las etiquetas de apertura y de cierre del otro
elemento.

El selector del siguiente ejemplo selecciona todos los elementos **span** de la página que se
encuentren dentro de un elemento **p**:

```

    p span { 
        color: red; 
    }

```

Ejemplo: 

```

    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
            <title>Ejemplo de estilos selector descendente</title> 
            <style type="text/css"> 
                p span { color: red; } 
            </style> 
            </head> 
            <body> 
                <section> 
                    <p> Aquí tenemos parte del texto <span>en rojo</span>. 
                        <br /> 
                        Incluso en un nivel inferior, como un 
                        <a href="#"><span>enlace</span></a> 
                    </p> 
                    <br> 
                    Fuera del párrafo el <span> SPAN se mantiene negro</span> 
                </section> 
        </body> 
    </html>

```

Los selectores descendentes permiten aumentar la precisión del selector de tipo o etiqueta. Así,
utilizando el selector descendente es posible aplicar diferentes estilos a los elementos del mismo
tipo. El siguiente ejemplo amplía el anterior y muestra de color azul todo el texto de los **span**
contenidos dentro de un **h1**

Otro ejemplo: 

```

    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
            <title>Ejemplo de estilos seelctor descendente</title> 
            <style type="text/css"> 
                p span { color: red; }
                h1 span { color: blue; } 
            </style> 
        </head> 
    <body> 
        <section> 
            <h1> <span>Titulo en Azul</span></h1>
            <p> Aquí tenemos parte del texto <span>en rojo</span>. 
        </section> 
    </body> 
    </html>

```

Con las reglas CSS anteriores:

- Los elementos **span** dentro de un elemento **p** se muestran de color rojo.
- Los elementos **span** dentro de un elemento **h1** se muestran de color azul.
- El resto de elementos **span** de la página, se muestran con el color por defecto aplicado por el navegador.

### Ejercicio -  Describe las reglas CSS siguientes: 

1. p a span em { color: blue; }
2. p, a, span, em { color: blue; }

Se puede restringir el alcance del selector descendente combinándolo con el selector universal. El
siguiente ejemplo, muestra los dos enlaces de color rojo:

```

    p a { color: red; }
    ... 
    <p><a href="#">Enlace</a></p>
    <p><span><a href="#">Enlace</a></span></p>

```
Sin embargo, en el siguiente ejemplo solamente el segundo enlace se muestra de color rojo:

```
    p * a { color: red; }
    ... 
    <p><a href="#">Enlace</a></p>
    <p><span><a href="#">Enlace</a></span></p>

```
La razón es que el selector p * a se interpreta como todos los elementos de tipo **a** que se
encuentren dentro de cualquier elemento que, a su vez, se encuentre dentro de un elemento de
tipo **p**. Como el primer elemento **a** se encuentra directamente bajo un elemento **p**, no se
cumple la condición del selector p * a. 

Ejemplo:

``` 
    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
        <title>Ejemplo de estilos sin CSS</title> 
        <style type="text/css"> 
            p * a { color: red; }
        </style> 
        </head> 
        <body> 
            <section> 
                <p><a href="#">Enlace</a></p>
                <p><span><a href="#">Enlace</a></span></p>
            </section> 
        </body> 
    </html>

```

### Clase

Una de las soluciones más sencillas para aplicar estilos a un solo elemento de la página consiste en utilizar el atributo class de HTML sobre ese elemento para indicar directamente la regla CSS que se le debe aplicar.

```
    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
            <title>Ejemplo de estilos selector de clase</title> 
        <style type="text/css"> 
            .destacado { color: red; }
        </style> 
        </head> 
            <body> 
            <section> 
                <p class="destacado">Lorem ipsum dolor sit amet...</p>
                <p>Nunc sed lacus et est adipiscing accumsan...</p>
                <p>Class aptent taciti sociosqu ad litora...</p>
            </section> 
        </body>     
    </html>

```

No debemos confundir este selector con los vistos anteriormente.


### Ejercicio -  Describe las reglas CSS siguientes: 

1. p.aviso { ... }
2. p .aviso { ... }
3. p, .aviso { ... }

Por último, es posible aplicar los estilos de varias clases CSS sobre un mismo elemento. La
sintaxis es similar, pero los diferentes valores del atributo class se separan con espacios en
blanco. 

Ejemplo: 

```
    
    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
            <title>Ejemplo de estilos selector clase</title> 
            <style type="text/css"> 
                .error { color: red; }
                .destacado { font-size: 15px; }
                .especial { font-weight: bold; }
            </style> 
        </head> 
        <body> 
            <section> 
                <p class="especial destacado error">Párrafo de texto...</p>
            </section> 
        </body> 
    </html>


```

Si un elemento dispone de un atributo class con más de un valor, es posible utilizar un selector
más avanzado:

```
    .error { color: red; }
    .error.destacado { color: blue; }
    .destacado { font-size: 15px; }
    .especial { font-weight: bold; }
    ... 
    <p class="especial destacado error">Párrafo de texto...</p>

```
En el ejemplo anterior, el color de la letra del texto es azul y no rojo. El motivo es que se ha utilizado un selector de clase múltiple .error.destacado, que se interpreta como "aquellos elementos de la página que dispongan de un atributo class con al menos los valores error y destacado".


### Id

En ocasiones, es necesario aplicar estilos CSS a un único elemento de la página. Aunque puede utilizarse un selector de clase para aplicar estilos a un único elemento, existe otro selector más eficiente en este caso. El selector de ID permite seleccionar un elemento de la página a través del valor de su atributo id. Este tipo de selectores sólo seleccionan un elemento de la página porque el valor del atributo id no se puede repetir en dos elementos diferentes de una misma página.

La sintaxis de los selectores de ID es muy parecida a la de los selectores de clase, salvo que se
utiliza el símbolo de la almohadilla (#) en vez del punto (.) como prefijo del nombre de la regla
CSS. 

Veamos un ejemplo: 

```

    <!DOCTYPE html> 
    <html lang="es"> 
        <head> <meta charset="UTF-8" /> 
            <title>Ejemplo de estilos con selector de id</title> 
            <style type="text/css"> 
                #destacado { color: red; }
            </style> 
        </head> 
        <body> 
            <section> 
                <p>Primer párrafo</p>
                <p id="destacado">Segundo párrafo</p>
                <p>Tercer párrafo</p>
            </section> 
        </body> 
    </html>

```
En el ejemplo anterior, el selector #destacado solamente selecciona el segundo párrafo (cuyo 
atributo id es igual a destacado).

La principal diferencia entre este tipo de selector y el selector de clase tiene que ver con HTML y 
no con CSS. Como se sabe, en una misma página, **el valor del atributo id debe ser único**, de forma
que dos elementos diferentes no pueden tener el mismo valor de id. Sin embargo, el atributo class
no es obligatorio que sea único, de forma que muchos elementos HTML diferentes pueden compartir el mismo valor para su atributo class.

Al igual que los selectores de clase, en este caso también se puede restringir el alcance del 
selector mediante la combinación con otros selectores. El siguiente ejemplo aplica la regla CSS 
solamente al elemento de tipo **p** que tenga un atributo id igual al indicado:

```
    p#aviso { color: blue; }
```

A primera vista, restringir el alcance de un selector de ID puede parecer absurdo. En realidad, un 
selector de tipo p#aviso **sólo tiene sentido cuando el archivo CSS se aplica sobre muchas páginas** 
HTML diferentes.

### Ejercicio -  Describe las reglas CSS siguientes: 


1. p#aviso { ... }
2. p #aviso { ... }
3. p, #aviso { ... }


### Combinación de selectores

CSS permite la combinación de uno o más tipos de selectores para restringir el alcance de las
reglas CSS. 

A continuación se muestran algunos ejemplos habituales de combinación de selectores.

```
    .aviso .especial { ... }

```

El anterior selector solamente selecciona aquellos elementos con un class="especial" que se
encuentren dentro de cualquier elemento con un class="aviso".

Si se modifica el anterior selector:

```
    div.aviso span.especial { ... }

```
Ahora, el selector solamente selecciona aquellos elementos de tipo **span** con un atributo class="especial" que estén dentro de cualquier elemento de tipo **div** que tenga un atributo class="aviso".

La combinación de selectores puede llegar a ser todo lo compleja que sea necesario:

```
    
    ul#menuPrincipal li.destacado a#inicio { ... }

```

El anterior selector hace referencia al enlace con un atributo id igual a inicio que se encuentra
dentro de un elemento de tipo **li** con un atributo class igual a destacado, que forma parte de una
lista **ul** con un atributo id igual a menuPrincipal.

## Ejercicio

- A partir del código HTML y CSS que se muestra, añadir los selectores CSS que faltan para aplicar los estilos deseados. Cada regla CSS incluye un comentario en el que se explica los elementos a los que debe aplicarse:

```
    <!DOCTYPE html> 
    <html lang="es"> 
        <head> 
            <meta charset="UTF-8" />
            <title>Ejercicio de selectores</title>
            <style type="text/css">
                /* Todos los elementos de la pagina */
                { font: 1em/1.3 Arial, Helvetica, sans-serif; }
                /* Todos los parrafos de la pagina */
                { color: #555; }
                /* Todos los párrafos contenidos en #primero */
                { color: #336699; }
                /* Todos los enlaces la pagina */
                { color: #CC3300; }
                /* Los elementos "em" contenidos en #primero */
                { background: #FFFFCC; padding: .1em; }
                /* Todos los elementos "em" de clase "especial" en toda la pagina */
                { background: #FFCC99; border: 1px solid #FF9900; padding: .1em; }
                /* Elementos "span" contenidos en .normal */
                { font-weight: bold; }
            </style>
        </head>
        <body>
            <div id="primero">
                <p>Lorem ipsum dolor sit amet, <a href="#">consectetuer adipiscing elit</a>. 
                Praesent blandit nibh at felis. Sed nec diam in dolor vestibulum aliquet. Duis 
                ullamcorper, nisi non facilisis molestie, <em>lorem sem aliquam nulla</em>, id 
                lacinia velit mi vestibulum enim.</p>
            </div>
            <div class="normal">
                <p>Phasellus eu velit sed lorem sodales egestas. Ut feugiat. <span><a 
                href="#">Donec porttitor</a>, magna eu varius luctus,</span> metus massa 
                tristique massa, in imperdiet est velit vel magna. Phasellus erat. Duis risus. <a
                href="#">Maecenas dictum</a>, nibh vitae pellentesque auctor, tellus velit 
                consectetuer tellus, tempor pretium felis tellus at metus.</p>
                <p>Cum sociis natoque <em class="especial">penatibus et magnis</em> dis 
                parturient montes, nascetur ridiculus mus. Proin aliquam convallis ante. 
                Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac 
                turpis egestas. Nunc aliquet. Sed eu metus. Duis justo.</p>
                <p>Donec facilisis blandit velit. Vestibulum nisi. Proin volutpat, <em 
                class="especial">enim id iaculis congue</em>, orci justo ultrices tortor, <a 
                href="#">quis lacinia eros libero in eros</a>. Sed malesuada dui vel quam. 
                Integer at eros.</p>
            </div>
        </body>
    </html>

```