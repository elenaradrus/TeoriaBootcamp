![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# JSON Resueltos

1. 

```javascript

    [
    {
      "nombre": "Francisco Ramirez",
      "edad": 29,
      "puesto": "Contable",
      "Emails": [
        "francisco@gmail.com",
        "francisco@hotmail.es",
        "francisco@thebridgeschool.es"
      ]
    },
    {
        "nombre": "Isabel Pérez",
        "edad": 31,
        "puesto": "Profesora",
        "Emails": [
          "isabel@gmail.com",
          "isabel@hotmail.es",
          "isabel@thebridgeschool.es"
        ]
      }
  ]


```

En el JSON del último ejemplo indica el código de acceso al email de The Bridge de Isabel.

Si la varibla se llamara contactos sería: 

contactos[1].Emails[2]

2. 

```javascript

    {
        "localidade 1": {
        "Continente": "África",
        "País": "Angola",
        "Capital": "Luanda"
        },
        "localidade 2": {
        "Continente": "América do Norte",
        "País": "Estados Unidos",
        "Capital": "Washington DC"
        },
        "localidade 3": {
        "Continente": "América Central",
        "País": "México",
        "Capital": "Cidade do México"
        },
        "localidade 4": {
        "Continente": "América do Sul",
        "País": "Brasil",
        "Capital": "Brasília"
        },
        "localidade 5": {
        "Continente": "Europa",
        "País": "Espanha",
        "Capital": "Madri"
        },
        "localidade 6": {
        "Continente": "Europa",
        "País": "Alemanha",
        "Capital": "Berlim"
        },
        "localidade 7": {
        "Continente": "Oceania",
        "País": "Austrália",
        "Capital": "Camberra"
        },
        "localidade 8": {
        "Continente": "Ásia",
        "País": "Japão",
        "Capital": "Tóquio"
        }
    }


```

Si la variable se llamara localidades: 

- Código para obtener el país de la localidade 8

```javascript

    localidades["localidade 8"]["País"] 

```

- Código que permite añadir una localidad a tu elección

```javascript

    localidades["localidade 9"] = {
       "Continente": "Europa",
        "País": "França",
        "Capital": "Paris"
    } 

```

- Modifica la localidade 4, añadiendo el número de habitantes

```javascript

    localidades["localidade 4"]["n_habitantes"] = "212,6 millones - 2020";

```

- Cambia la estructura del JSON de forma que sea más directo acceder a las capitales de las localidades, dado que va a ser el dato que más vamos a consultar


```javascript 

    {
        "Luanda": {
        "Continente": "África",
        "País": "Angola"
        },
        "Washington DC": {
        "Continente": "América do Norte",
        "País": "Estados Unidos",
        },
        "Cidade do México": {
        "Continente": "América Central",
        "País": "México",
        }
        ...
    }

```

3. A partir de la siguiente información, diseña y elabora un JSON que la contenga y permita acceder de manera lo más sencilla posible, a precio y calorías de cada desayuno.

```javascript 

    let desayunos = [
        {
            "precio": 5.95,
            "calorias": 650,
            "resto_datos": {
                "nombre": "Gofres Belgas",
                "decripcion": "Dos de nuestros famosos Gofres belgas con abundante sirope"
            }

        },
        ...
    ]

```

