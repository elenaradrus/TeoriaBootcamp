![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# JEST

![img](../../../assets/core/clase27/jest.png)

Se trata de un módulo para pruebas unitarias, que mantiene Facebook y que permite pruebas en aplicaciones con Node y con React entre otros.

Vamos a ver las bases de la teoría con un ejemplo y algunas funciones:

## Ejemplo inicial - Método test 

Pasos: 

1. Crea un proyecto y ejecuta **npm init -y**

2. Instala **jest** con npm 

3. Crea los siguientes ficheros: 

**calculadora.js:**

```javascript 

    const operaciones = {
        sumar:(a, b) => a + b,
        restar:(a, b) => a - b,
        multiplicar:(a, b) => a * b,
        dividir: (a, b) => a / b
    };
    module.exports = operaciones;

```

**calculadora.test.js:**

```javascript 

    const operaciones = require('./calculadora');

    describe('Operaciones matemáticas', () => {
        test('Realizamos la suma', () => {
            expect(operaciones.sumar(1,1)).toBe(2);
        });
        test('Realizamos la resta', () => {
            expect(operaciones.restar(1,1)).toBe(0);
        });
        test('Realizamos la multiplicacion', () => {
            expect(operaciones.multiplicar(1,1)).toBe(1);
        });
        test('Realizamos la division', () => {
            expect(operaciones.dividir(1,1)).toBe(1);
        });
    });

```

4. Modifica el package.json cambiando el contenido de la clave "test" por "jest"

```json
    
    "test": "jest"

```

5. Ejecuta **npm run test**

## Matchers

Se trata de funciones que dependen de **expect** y que permiten añadir funcionalidad a las pruebas.

### toBe

Compara con valores primitivos y lo hemos usado en nuestro ejemplo

### toEqual

Usado para comparar recursívamente todas las propiedades de un objetos, también conocido como igualdad profunda.

Veamos un ejemplo:

Crea el siguiente fichero en el mismo proyecto y ejecuta de nuevo tus pruebas unitarias: 

**toEqualsTest.test.js:**

```javascript

    describe('Common matchers', () => {
        const datos = {
            nombre: 'Persona 1',
            edad: 10
        }
        const datos2 = {
            nombre: 'Persona 1',
            edad: 10
        }
        test('Comprobamos que los objectos son iguales', () => {
            expect(datos).toEqual(datos2);
        });
    });

```

### toBeLessThan 

El valor es menor que.

### toBeLessThanOrEqual
El valor es menor o igual que.

### toBeGreaterThanOrEqual
El valor es mayor o igual que.

### toBeGreaterThan
El valor es mayor que.

Veamos un ejemplo: 

Crea el siguiente fichero en el mismo proyecto y ejecuta de nuevo tus pruebas unitarias: 


**testToCompare.test.js:**

```javascript

    const operaciones = require('./calculadora');

    describe('Matchers numéricos', () => {
        test('Resultado menor que...', () => {
            expect(operaciones.restar(5,3)).toBeLessThan(3);
        });
        test('Resultado menor o igual que...', () => {
            expect(operaciones.restar(5,3)).toBeLessThanOrEqual(2);
        });
        test('Resultado mayor o igual que...', () => {
            expect(operaciones.multiplicar(2,5)).toBeGreaterThanOrEqual(10);
        });
        test('Resultado mayor que...', () => {
            expect(operaciones.sumar(5,5)).toBeGreaterThan(9);
        });
    });

```

### toBeTruthy

El valor es verdadero.

### toBeFalsy 

El valor es falso.

### toBeUndefined 

El valor es ‘undefined’

### toBeNull

El valor es ‘null’

Veamos un ejemplo: 

Modifica tu calculadora dejándola así: 

**calculadora.js:**

```javascript 

    const operaciones = {
        sumar:(a, b) => a + b,
        restar:(a, b) => a - b,
        multiplicar:(a, b) => a * b,
        dividir: (a, b) => a / b,
        isNull: () => null,
        isFalse : () => false,
        isTrue : () => true,
        isUndefined : () => undefined
    };
    module.exports = operaciones;

```

Ahora modifica los test de tu calculadora, dejándolos así: 


**calculadora.test.js:**

```javascript

    const operaciones = require('./calculadora');

    describe('Operaciones matemáticas', () => {
        test('Realizamos la suma', () => {
            expect(operaciones.sumar(1,1)).toBe(2);
        });
        test('Realizamos la resta', () => {
            expect(operaciones.restar(1,1)).toBe(0);
        });
        test('Realizamos la multiplicacion', () => {
            expect(operaciones.multiplicar(1,1)).toBe(1);
        });
        test('Realizamos la division', () => {
            expect(operaciones.dividir(1,1)).toBe(1);
        });
    });

    describe('Matchers Boolean, Undefined o Null', () => {
        test('Resultado true', () => {
            expect(operaciones.isTrue()).toBeTruthy();
        });
        test('Resultado false', () => {
            expect(operaciones.isFalse()).toBeFalsy();
        });
        test('Resultado undefined', () => {
            expect(operaciones.isUndefined()).toBeUndefined();
        });
        test('Resultado null', () => {
            expect(operaciones.isNull()).toBeNull();
        });
    });
```

Ejecuta tus pruebas de nuevo

### toContain

Contiene el elemento dentro del array

### toHaveLength

El array tiene la longitud que le indiquemos como parámetro

Veamos un ejemplo: 

Crea el fichero con el contenido siguiente y ejecuta de nuevo tus pruebas: 

**arrays.test.js:**

```javascript 

    const provincias = ['Álava','Badajoz','Cáceres','Girona','Huelva','Jaén','La Rioja','Madrid','Navarra'];
    const dias = ['Lunes','Martes','Miercoles','Jueves','Viernes','Sabado','Domingo'];

    const arrProvincias = () => provincias;
    const arrDias = () => dias;

    describe('Matchers Arrays', () => { 
        test('Madrid existe en el array', () => {
            expect(arrProvincias()).toContain('Madrid');
        });
        test('Guadalajara no existe en el array', () => {
            expect(arrProvincias()).not.toContain('Guadalajara');
        })
        test('El array semana tiene 9 elementos', () => {
            expect(arrDias()).toHaveLength(7);
        })
    });

```

### toMatch

Comprueba que un texto coincide con una expresión regular

Veamos un ejemplo: 

Crea el fichero con el contenido siguiente y ejecuta de nuevo tus pruebas: 

**regexp.test.js:**

```javascript 

    const expReg = {
        responseOK: 'Response OK',
        responseFAIL: 'Response FAIL',
        email: 'test@test.com',
        telefono: '919784852'
    };
    const objExpReg = () => expReg;

    describe('Matchers Strings', () => {
        const exp = objExpReg();
        test('Comprobamos si la respuesta es correcta', () => {
            expect(exp.responseOK).toMatch(/OK/);
        });
        test('Comprobamos si la respuesta es incorrecta', () => {
            expect(exp.responseFAIL).toMatch(/FAIL/);
        });
        test('Comprobamos si la respuesta tiene una longitud', () => {
            expect(exp.responseFAIL).toHaveLength(13);
        });
        test('Comprobamos dirección de email', () => {
            expect(exp.email).toMatch(/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.([a-zA-Z]{2,4})+$/);
        })
        test('Comprobamos número de teléfono', () => {
            expect(exp.telefono).toMatch(/^[9|6|7][0-9]{8}$/);
        });
    });


```

Como podemos ver, disponemos de muchas herramientas para pruebas, pero debemos diseñarlas y desarrollarlas nosotros.

Para poder ver la cobertura de nuestras pruebas disponemos de un flag (parámetro de Jest) que nos permite ver un informe de las pruebas.

Veamos los pasos a seguir: 

1. Modifica el package.json añadiendo a scripts lo siguiente: 

```json

    "test:cobertura": "jest --coverage"

```

2. Ejecuta las pruebas con el informe: 

```

    npm run test:cobertura

```

Esto además de sacar un resumen del informe por consola, genera un directorio **coverage** en el que puedes encontrar el informe en una sencilla app web.


[DOCUMENTACION_JEST](https://jestjs.io/es-ES/docs/getting-started)