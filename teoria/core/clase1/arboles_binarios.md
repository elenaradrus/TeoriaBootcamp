![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Árboles y recorridos

##  Árboles Binarios de Búsqueda
Vamos a hablar brevemente de esta estructura de datos que tiene naturaleza recursiva (cada rama es un árbol) y que permite buscar con mucha rapidez datos que se puedan ordenar.

Las normas que deben cumplir los nodos de estos árboles son: 

1. Cada nodo tiene un máximo de 2 hijos (por esto es binario)
2. El primer nodo es la raíz del árbol completo
3. Los elementos menores que la raíz van a la izquierda
4. Los elementos mayores que la raíz van a la derecha
5. No se pueden repetir elementos
6. Cada nodo es raíz del sub-árbol en el que se encuentran sus hijos

Ejemplo: 

![img](../../../assets/core/clase1/ABB.png)

Aquí tienes una herramienta online para crear estos árboles paso a paso 

[ABB](https://visualgo.net/es/bst)

## Recorridos
Hay diferentes maneras de recorrer un ABB, dependiendo de lo que necesitemos y de la información que almacenen. 

### Recorrido preorden
El orden en el que se visitan los nodos es: 
1. Raíz
2. Izquierdo
3. Derecho


### Recorrido inorden
El orden en el que se visitan los nodos es: 
1. Izquierdo
2. Raíz
3. Derecho

### Recorrido posorden
El orden en el que se visitan los nodos es: 
1. Izquierdo
2. Derecho
3. Raíz

## Ejemplo recorridos
- Orden de inserción de los nodos: 15,9,20,8,10,13,12,19,23,21,25

- Preorden: 15,9,8,10,13,12,20,19,23,21,25

- Inorden: 8,9,10,12,13,15,19,20,21,23,25

- Posorden: 8,12,13,10,9,19,21,25,23,20,15

## Ejercicio
- A partir de un ABB con estos nodos: 2,1,7,26,15. Indica qué resultado darían todos los recorridos
