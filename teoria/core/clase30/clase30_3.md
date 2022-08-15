![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Cypress

![img](../../../assets/core/clase30/cypress.png)

Cypress es un framework de testing moderno y todo en uno. Es rápido, fácil de usar y permite ejecutar pruebas sobre cualquier aplicación web. En poco más de 2 años desde su lanzamiento de la versión 1.0.0 se ha convertido en una de las herramientas más populares de testing.

[DOCUMENTACION](https://docs.cypress.io/guides/overview/why-cypress)

## Ejemplo Google
Pasos: 

1. Crea un nuevo proyecto Node

2. Inicialízalo con npm init -y

3. Ejecuta la app con entorno gráfico de Cypress: 

```
    npx cypress open

```
4. Añade a la carpeta 'e2e' el siguiente fichero con el siguiente contenido: 

Esto en la nueva versión se hace por el entorno gráfico usando la opción de "New spec".

**google-search.cy.js:**
```javascript 

describe('Google Search', () => {
    it('loads search page', () => {
      cy.visit('https://www.google.com');
    });

    it('Click Aceptar Button', () => {
        cy.get('#L2AGLb > div').click();
      });    
  
    it('searches for `remarkablemark`', () => {
      cy.get('input[name="q"]').type('remarkablemark{enter}');
    });
  
    it('gets first search result', () => {
      cy.get('#search a')
        .invoke('attr', 'href')
        .then(href => console.log(href));
    });
  });

```

5. Ejecuta la prueba desde el entorno gráfico pinchando sobre ella una vez accedido a test en Chrome.