![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Una solución del ejercicio de los colores

Puede haber muchas más soluciones válidas, pero esta es una de ellas.


```html
<!DOCTYPE html> 
<html lang="es"> 
    <head> 
        <meta charset="UTF-8" /> 
        <title>Ejemplo de estilos ejercicio</title> 
        <style type="text/css"> 
            h1 {color: teal}
            strong, a, th[scope="row"],tfoot th  {color: red}
            td strong, span.destacado, thead th, th[scope="row"].especial { color: orange}
            #subtitulo, caption, a em {color: blue }
            div a, td {color: green }
            div {color: olive}
            #especial {color: fuchsia}
            span.especial {color: purple}
            table, tr, th, td {
                border-collapse: collapse;
                border: 1px solid black;
            }
        </style> 
    </head> 
    <body>
        <h1 id="titulo">Lorem ipsum dolor sit amet</h1>
        <p>Nulla pretium. Sed tempus nunc vitae neque. <strong>Suspendisse 
        gravida</strong>, metus a scelerisque sollicitudin, lacus velit 
        ultricies nisl, nonummy tempus neque diam quis felis. <span 
        class="destacado">Etiam sagittis tortor</span> sed arcu sagittis tristique.</p>
        <h2 id="subtitulo">Aliquam tincidunt, sem eget volutpat porta</h2>
        <p>Vivamus velit dui, placerat vel, feugiat in, ornare et, urna. <a 
        href="#">Aenean turpis metus, <em>aliquam non</em>, tristique in</a>, pretium 
        varius, sapien. Proin vitae nisi. Suspendisse <span class="especial">porttitor 
        purus ac elit</span>. Suspendisse eleifend odio at dui. In in elit sed metus 
        pretium elementum.</p>
        <table summary="Descripción de la tabla y su contenido">
            <caption>Título de la tabla</caption>
            <thead>
                <tr>
                    <th scope="col"></th>
                    <th scope="col" class="especial">Título columna 1</th>
                    <th scope="col" class="especial">Título columna 2</th>
                </tr>
            </thead>
            <tfoot>
                <tr>
                    <th scope="col"></th>
                    <th scope="col">Título columna 1</th>
                    <th scope="col">Título columna 2</th>
                </tr>
            </tfoot>
            <tbody>
                <tr>
                    <th scope="row" class="especial">Título fila 1</th>
                    <td>Donec purus ipsum</td>
                    <td>Curabitur <em>blandit</em></td>
                </tr>
                <tr>
                    <th scope="row">Título fila 2</th>
                    <td>Donec <strong>purus ipsum</strong></td>
                    <td>Curabitur blandit</td>
                </tr>
            </tbody>
        </table>
        <div id="adicional">
            <p>Donec purus ipsum, posuere id, venenatis at, <span>placerat ac, lorem</span>. 
            Curabitur blandit, eros sed gravida aliquet, risus justo 
            porta lorem, ut mollis lectus tortor in orci. Pellentesque nec augue.</p>
            <p>Fusce nec felis eu diam pretium adipiscing. <span id="especial">Nunc elit 
            elit, vehicula vulputate</span>, venenatis in, 
            posuere id, lorem. Etiam sagittis, tellus in ultrices accumsan, diam nisi feugiat
            ante, eu congue magna mi non nisl.</p>
            <p>Vivamus ultrices aliquet augue. <a href="#">Donec arcu pede, pretium 
            vitae</a>, rutrum aliquet, tincidunt blandit, pede. 
            Aliquam in nisi. Suspendisse volutpat. Nulla facilisi. Ut ullamcorper nisi quis 
            mi.</p>
        </div>
    </body>
</html>

```


**Se incluye el css dentro del HTML por comodidad, pero las entregas y ejercicios se realizarán siempre en archivos separados (html y css).**