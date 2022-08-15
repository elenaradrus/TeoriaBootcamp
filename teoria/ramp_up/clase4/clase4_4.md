![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Pseudoclases y Pseudoelementos

## Pseudoclase
Una pseudoclase es un selector que marca los elementos que están en un estado específico, por ejemplo, aquellos por los que el cursor les pasa por encima. Tienden a actuar como si hubieras aplicado una clase en una o varias etiquetas, pero sin hacerlo, haciendo la aplicación de estilos más sencilla y felxible

Sintaxis: 

```

    :pseudo-class-name

```

### :first-child
Siempre selecciona el primer hijo de un tipo, veamos un ejemplo para clarificarlo: 

```css

    article p:first-child {
        font-size: 120%;
        font-weight: bold;
    }   
    
```

```html

<article>
    <p>Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo
            melon azuki bean garlic.</p>

    <p>Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard
            greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</p>
</article>

```

### :last-child
Último hijo de un tipo, es decir en el árbol el último nodo de la derecha.

## :only-child 
Elemento hijo único, es decir su elemento padre no dispone de otro hijo de su tipo.

Ejemplo: 

```css

    p:only-child {
        background-color: lime;
    }

```
### :hover 
Se aplicarán los estilos que usen este selector, si el usuario pasa el cursor sobre un elemento, normalmente un enlace.

### :focus
Se aplicarán los estilos que usen este selector, si el usuario selecciona el elemento con los controles del teclado.

### :visited
Se aplicarán los estilos que usen este selector, si el usuario ya ha visitado un enlace


## Pseudoelemento
Se comportan de manera similar, pero simulan haber añadido un elemento nuevo al HTML y no una clase.

Sintaxis: 

```

    ::pseudo-element-name

```

### ::first-line
Nos permite ahorrar un span y una clase y contar el número de palabras que caben en una línea, para aplicar estilos a la primera línea de un párrafo por ejemplo, ya que siempre va a seleccionar esa primera línea sin tener en cuenta su longitud.

Ejemplo: 

```css

    article p::first-line {
        font-size: 120%;
        font-weight: bold;
    }   

```

```html

    <article>
        <p>Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo
                melon azuki bean garlic.</p>

        <p>Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard
                greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</p>
    </article>

```

Además podemos combinar pseudoclases y pseudoelementos entre sí (ya hemos visto en los ejemplos que se pueden combinar con el resto de selectores, por ejemplo el descendente).

Ejemplo: 

```css

    article p:first-child::first-line {
        font-size: 120%;
        font-weight: bold;
    }

```
Selecciona la primera línea del primer elemento **p** que esté dentro de un elemento **article**.

[PSEUDOCLASES_PSEUDOELEMENTOS](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)

[RESUMEN_PROPIEDADES](https://www.eniun.com/resumen-tabla-propiedades-css-valores/)