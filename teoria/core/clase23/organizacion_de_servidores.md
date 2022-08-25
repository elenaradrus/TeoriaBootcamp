![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Organización de Servidores - Proyectos de desarrollo

Aunque la organización de los proyectos de desarrollo depende de muchos factores. Algunos de ellos son: 

1. Recursos Humanos que van a participar en él
2. Dimensariones y fases de proyecto
3. Diseño de la Arquitectura del proyecto a nivel lógico
4. Recursos físicos a disposición
5. Cantidad y variedad de los servicios prestados por la aplicación

Estos factores entre otros, apoyados en la expreriencia y cultura de la empresa que desarrolla el proyecto, definen en muchos casos la organización de los servidores en la arquitectura física del proyecto.

Esto que vamos a comentar es el mínimo que se debe tener en un proyecto profesional, sin importar la dimensión (pero no implica que todas las empresas den importancia a las mismas cuestiones o estén correctamente organizadas por cuestiones principalmente de recursos).

Dentro de las Fases de Desarrollo de nuestros proyectos debemos tener al menos tres escenarios y a ellos va a asociado al menos un servidor: 

1. **Desarrollo (des o dev):** Es el escenario que debemos usar durante el desarrollo para realizar nuestras pruebas más allá de nuestro PC.
2. **Pre-producción (pre):** Es el escenario que debe ser un "clon" de nuestro escenario de producción (mismo SO, mismas versiones de todo el software, mismos niveles de seguridad...etc) y sirve para realizar pruebas de versiones más o menos estables que ya estamos pensando en pasar a producción y para eso necesitamos confirmar que van a comportarse como esperamos en producción.
3. **Producción (pro):** Escenario en el que ya ponemos nuestra aplicación disponible al cliente

Aquí les dejo un artículo de la infraestructura de Netflix, que aunque no es actual, nos puede dar una idea del problema al que se enfrenta y ha enfrentado este gigante del entretenimiento a nivel informáticos en general: 

[INFRAESTRUCTURA_NETFLIX](https://www.xataka.com/streaming/la-compleja-infraestructura-detras-de-netflix-que-pasa-cuando-le-das-al-play)

