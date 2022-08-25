![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Web Storage y Métodos de Object

## Web Storage
Web Storage es la nueva caracteristica que traen los navegadores actuales gracias a HTML5 para guardar información en el lado del cliente. 

La información la guardamos al igual en pares clave-valor. Todo lo guardado resulta ser una cadena y la información es persistente sólo el lado del cliente.

Uso y limitaciones:
- 5-10Mb según navegador
- Almacenamiento local (lectura/escritura cliente)
- Sin caducidad
- Funcionamiento clave/valor (diccionario)
- Solo se permite el almacenamiento de cadenas de texto (JSON.stringfy)

**Local Storage vs Session Storage**
- Local Storage no tiene fecha de expiración
- Session Storage solo será válida para la ventana actual en la que estamos navegando y solo son accesibles para el dominio actual. 
- La información de ambas puede ser eliminada si se limpia la información guardada en el navegador.

Recursos
- [MDN | API_de_almacenamiento_web](https://developer.mozilla.org/es/docs/Web/API/API_de_almacenamiento_web)
- [html-5-diferencias-y-ejemplos-entre-local-storage-y-session-storage](https://anexsoft.com/html-5-diferencias-y-ejemplos-entre-local-storage-y-session-storage)
- [que-es-y-como-utilizar-localstorage-y-sessionstorage](https://ed.team/blog/que-es-y-como-utilizar-localstorage-y-sessionstorage)
- [LocalStorage, sessionStorage](https://javascript.info/localstorage)
- [storing_and_retrieving_an_array_from_local_storage](https://www.kirupa.com/html5/storing_and_retrieving_an_array_from_local_storage.htm)


Veamos ejemplos: 

**Guardar datos:**

```javascript

    localStorage.setItem('name', 'Davinia'); // op1
    localStorage.surname = 'de la Rosa'; // op2

```

**Leer datos:**

```javascript

    let firstName = localStorage.getItem('name');
    let lastName  = localStorage.surname;
    console.log(`Hola, mi nombre es ${firstName} ${lastName}`)
    // o también
    console.log(`Hola, mi nombre es ${localStorage.getItem('name')} ${localStorage.surname}`)

```

**Eliminar datos:**

Se borra por clave

```javascript
    
    localStorage.removeItem('surname');

```

**borrar todo:**

```javascript
    
    localStorage.clear();

```

**Leer todo lo que hay en local Storage:**

```javascript

    for(let i=0; i<localStorage.length; i++) {
        let key = localStorage.key(i);
        alert(`${key}: ${localStorage.getItem(key)}`);
    }

```

**Leer/escribir un objeto de LocalStorage:**

usar JSON.stringify() y JSON.parse() (ya los hemos visto)
- [MDN | JSON.stringify()](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/JSON/stringify)
- [MDN | JSON.parse()](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/JSON/parse)

```javascript

    //Escribir
    localStorage.setItem('user', JSON.stringify({
        username: 'Davinia',
        api_key: 'abc123xyz789'
    }));
    //Leer
    var user = JSON.parse(localStorage.getItem('user'));

```

**Leer/escribir un array de LocalStorage:**

```javascript

    var movies = ["Reservoir Dogs", "Pulp Fiction", "Jackie Brown", 
                "Kill Bill", "Death Proof", "Inglourious Basterds"];
    //Escribir
    localStorage.setItem("quentinTarantino", JSON.stringify(movies));

    //Leer
    var retrievedData = localStorage.getItem("quentinTarantino");

```

## Métodos de Object
- [MDN | Objects](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Object) 
- [how-to-use-object-methods-in-javascript](https://www.digitalocean.com/community/tutorials/how-to-use-object-methods-in-javascript)

- Object.entries():

```javascript

    // Creamos un objeto
    const operatingSystem = {
        name: 'Ubuntu',
        version: 18.04,
        license: 'Open Source'
    };

    // Obtenemos los conjuntos clave/valor
    const entries = Object.entries(operatingSystem);

    console.log(entries);
    /*
    [
        ["name", "Ubuntu"]
        ["version", 18.04]
        ["license", "Open Source"]
    ]
    */

```

- Object.keys(): 

```javascript

    const employees = {
        boss: 'Michael',
        secretary: 'Pam',
        sales: 'Jim',
        accountant: 'Oscar'
    };

    // Obtenemos las claves en un array
    const keys = Object.keys(employees);

    console.log(keys);//["boss", "secretary", "sales", "accountant"]

```
- Object.values():

```javascript

    const session = {
        id: 1,
        time: `26-July-2018`,
        device: 'mobile',
        browser: 'Chrome'
    };

    // Obtenemos los valores en un array
    const values = Object.values(session);

    console.log(values); // [1, "26-July-2018", "mobile", "Chrome"]

```

- Object.create():

```javascript

    const persona = {
        nombre: 'espacio para el nombre',
        apellidos: 'espacio para los apellidos',
        edad: 'espacio para la edad',
        muestraDatos() {
            const menor = this.edad < 18 ? 'es menor de edad' : 'no es menor de edad';

            alert(`Nombre: ${this.nombre}, Apellidos: ${this.apellidos}.\nTiene ${this.edad} años  y ${menor}`);
        }
    };

    // Creamos un objeto persona (equivalente a new)
    var persona1 = Object.create(persona);
    persona1.nombre = "Rafael";
    persona1["apellidos"] = "Pérez Ramírez";
    persona1["edad"] = 15;
    persona1.muestraDatos();

    // Alternativa con new
    var persona2 = new Object(persona);
    persona2["nombre"] = "Ana";
    persona2.apellidos = "Valcárcel Luis";
    persona2.edad = 43;
    console.log(persona2["muestraDatos"]);
    persona2.muestraDatos();

```

- Object.assign():

```javascript

    //Objeto 1
    const personalInformation = {
        firstName: 'Philip',
        lastName: 'Fry'
    };

    //Objeto 2
    const details = {
        job: 'Delivery Boy',
        employer: 'Planet Express'
    };

    // Objeto resultante de combinar ambos
    var person = Object.assign(personalInformation, details);
    console.log(person);

```


### Ejercicios
1. Formulario de contacto - Local Storage
- Crear un formulario de contacto con los siguientes campos:
  - Nombre
  - Email
  - Mensaje
- Guardar en Local Storage los datos de contacto enviados de cada usuario
- Mostrar los datos de los contactos guardados usando herramientas de DOM
- Usa `JSON.parse()` y `JSON.stringify()` para guardar muchos datos usando la misma clave

2. Avanzado - Local Storage
- Crea botón para borrar todos los contactos guardados en Local Storage
- Crea botón para borrar un contacto en concreto de Local Storage, buscando por email