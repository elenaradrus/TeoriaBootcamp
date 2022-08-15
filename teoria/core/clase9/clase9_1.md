![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Ampliación de funciones y Desestructuración

Ya hemos hablado de las funciones, pero hay que ampliar información sobre ellas.

## Funciones tradicionales (puras) - Ventajas y desventajas
**Algunos recursos:**
- [las-funciones-puras-en-javascript-concepto-ejemplos-y-beneficios](http://www.etnassoft.com/2016/06/21/las-funciones-puras-en-javascript-concepto-ejemplos-y-beneficios/)
- [javascript-pure-functions](https://willtaylor.blog/javascript-pure-functions/)


**Características:**
- Código más conciso y expresivo
- Que el estado sea inmutable, evita muchos errores (sin efectos colaterales)
- Entrada y salida; Las funciones reciben parámetros y devuelven un resultado.
- Las funciones puras son muy previsibles y testeables
- Código infinitamente más expresivo
- Proceso de depuración simplificado
- Fomenta mucho la descomposición de las tareas complejas
- Hacemos uso de composiciones partiendo de fragmentos pequeños y especializados
- Gestión de recursos. Diferentes scopes


## Funciones flecha (arrow functions) - ECMA6
Algunas características:
- No pueden ser usadas como constructores
- No tienen una propiedad de prototipo `prototype`
- Retorno de objetos literales
- Siempre son anónimas
- return implicito en declaración inline

Algunos recursos: 

[PROPIEDAD_PROTOTYPE](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/Object_prototypes)
- [MDN | Arrow_functions](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Funciones/Arrow_functions)
- [arrow-functions-es6](https://desarrolloweb.com/articulos/arrow-functions-es6.html)

## Parámetros opcionales
Podemos asigna valores predeterminados a las funciones y así permitimos que el número de parámetros sea variable. 

Veamos un ejemplo: 

```Javascript

    function f (x, y = 3, z = 22) {
        return x + y + z
    }

    console.log(f(3));
    console.log(f(3,0));
    console.log(f(3,0,0));

```

Esto puede ser usado en el caso de registros web con datos opcionales por ejemplo.

```javascript
    function registro (nombre, dni, email="Sin email", telefono="Sin teléfono") {
        var datos = [nombre, dni, email, telefono]
        alert(`Ha sido registrado con los datos:\n ${datos}`);
    }
    registro("Davinia de la Rosa", "11111111A");
```


## Desestructuración

Nos permite rápidamente asignar valores a un JSON a partir de datos compuestos, esto tiene múltiples usos, pero claramente permite ahorrar tiempo a la hora de recorrer elementos y guardarlos en otros.

Veamos ejemplos:

**Ejemplo: Arrays**
```Javascript 

    let [a, b] = [10, 20];
    console.log(a);
    console.log(b);


    let list = [ 3, 5, 7,6 ]
    let [ a1, , , b2 ] = list; // Guarda a1=3 y b2=6
    console.log(a1);
    console.log(b2);
    console.log(list);

    // Asignar nombres a elementos de objetos pasados por parámetro
    function imprime ([ saludo, hora ]) {
        console.log(`${saludo}, buenos ${hora}`);
    }
    imprime([ "hola", "dias" ]); //Quita los [] y explica lo que pasa
    
    let c,d;
    let list2 = [ 33,2,5,6 ];
    [ a,b,c,d ] = list2;

    console.log(list2);
    console.log(a);
    console.log(b);
    console.log(c);
    console.log(d);

    list2 = [ 33, 2, ,6 ];
    [ a,b,c=9,d ] = list2;
    console.log(a);
    console.log(b);
    console.log(c);
    console.log(d);

    list2 = [33,2];
    [ a,b,c=9,d ] = list2;
    console.log(a);
    console.log(b);
    console.log(c);
    console.log(d);

```

**Ejemplos: Objetos**

```Javascript

    // Asignación básica
    const user = {
        id: 42,
        is_verified: true
    };
    
    const {id, is_verified} = user;
    
    console.log(id); // 42
    console.log(is_verified); // true 

    // Asignar nuevos nombres de constantes que recojan los valores de o
    const o = {p: 42, q: true};
    const {p: foo, q: bar} = o;

    console.log(foo); // 42 
    console.log(bar); // true

    // Valores predeterminados
    const {a = 10, b = 5} = {a: 3};

    console.log(a); // 3
    console.log(b); // 5

```
