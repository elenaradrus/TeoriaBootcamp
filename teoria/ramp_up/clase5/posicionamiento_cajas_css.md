![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Posicionamiento
Los navegadores crean y posicionan de forma automática todas las cajas (modelo de cajas) de los elementos del HTML. CSS, por su parte, permite al diseñador, utilizando las propiedades que proporciona CSS alterar la posición de las cajas, realizar efectos avanzados y diseñar estructuras de páginas que de otra forma no serían posibles.

**Con CSS tenemos 5 formas diferentes de posicionar una caja:**

1. Posicionamiento normal o estático: se trata del posicionamiento que utilizan los navegadores si no se indica lo contrario.

2. Posicionamiento relativo: la caja se posiciona según el posicionamiento normal y después se desplaza respecto de su posición original.

3. Posicionamiento absoluto: la posición de una caja se establece respecto de su elemento contenedor y el resto de elementos de la página ignoran la nueva posición del elemento.

4. Posicionamiento fijo: variante del posicionamiento absoluto que convierte una caja en un elemento inamovible, de forma que su posición en la pantalla siempre es la misma independientemente del resto de elementos e independientemente de si el usuario sube o baja la página en la ventana del navegador.

5. Posicionamiento flotante: se trata del modelo más especial de posicionamiento, ya que desplaza las cajas todo lo posible hacia la izquierda o hacia la derecha de la línea en la que se encuentran.

**El posicionamiento de una caja se establece mediante la propiedad position:**

[POSITION](https://developer.mozilla.org/es/docs/Web/CSS/position)

- static: corresponde al posicionamiento normal o estático. Si se utiliza este valor, se ignoran los valores de las propiedades top, right, bottom y left que se verán a continuación.

El elemento es posicionado de acuerdo al flujo normal del documento. Las propiedades top, right, bottom, left, and z-index no tienen efecto. Este es el valor por defecto.

Ejemplo: 

```css

    position: static;

```

- relative: corresponde al posicionamiento relativo. El desplazamiento de la caja se controla con las propiedades top, right, bottom y left.

El elemento es posicionado de acuerdo al flujo normal del documento, y luego es desplazado con relación a sí mismo, con base en los valores de top, right, bottom, and left. El desplazamiento no afecta la posición de ningún otro elemento; por lo que, **el espacio que se le da al elemento en el esquema de la página es el mismo como si la posición fuera static**.

Ejemplo: 

```css

    position: relative;
    top: 40px; left: 40px;

```

- absolute: corresponde al posicionamiento absoluto. El desplazamiento de la caja también se controla con las propiedades top, right, bottom y left, pero su interpretación es mucho más compleja, ya que el origen de coordenadas del desplazamiento depende del posicionamiento de su elemento contenedor.

**El elemento es eliminado del flujo normal del documento, sin crearse espacio alguno para él elemento en el esquema de la página**. Es posicionado relativo a su ancestro posicionado más cercano, si lo hay; de lo contrario, se ubica relativo al bloque contenedor inicial. Su posición final está determinada por los valores de top, right, bottom, y left.

Ejemplo: 

```css

    position: absolute;
    top: 40px; left: 40px;

```

- fixed: El desplazamiento se establece de la misma forma que en el posicionamiento absoluto, pero en este caso **el elemento permanece inamovible en la pantalla, usando los valores de top, right, bottom, y left**.

- La propiedad position no permite controlar el posicionamiento flotante, que se establece con otra propiedad llamada float. 


