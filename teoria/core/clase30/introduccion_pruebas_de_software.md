![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS, JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Pruebas de software
Una parte imprescindible en el desarrollo de software que no podemos omitir son las pruebas.

Como ya hemos visto en nuestras aplicaciones no siempre es sencillo probarlas para todos los casos, ni a veces el diseño de las pruebas es trivial; es por esto, que cada vez se invierten, en los proyectos profesionales, más recursos en el testeo de las aplicaciones.

Veamos los tipos más comunes de pruebas: 

## Pruebas de humo

Son una de las pruebas funcionales de software iniciales que se realizan en un proceso de pruebas, y tienen una gran relevancia, puesto que permiten identificar si las funcionalidades más importantes se encuentran bien; por ejemplo, cuando es desarrollada una aplicación de portal para empleados, la prueba de humo ayuda a testear el funcionamiento general de los aspectos críticos como el inicio de sesión, el registro de detalles y el informe enviado al director, sin verificar detalles como el tipo de campo o la información que entrega.

 

El resultado de las smoke test o pruebas de humo permite decidir si el software es suficientemente estable para afrontar un ciclo de pruebas más exhaustivas y costosas, o si es necesario revertir la producción y no comenzar un nuevo ciclo de pruebas. Para realizarlas, se debe ejecutar un subconjunto de los casos de prueba definidos, los cuales recorren las funcionalidades críticas y básicas del sistema. 

 

Normalmente este grupo de pruebas seleccionadas no sobrepasa el 5% de las pruebas totales que se realizan en un ciclo completo. Cuando el aplicativo no pasa la prueba de humo, se rechaza y se envía al equipo de desarrollo para solucionar los fallos encontrados o en casos más extremos, desarrollar una nueva aplicación.

## Pruebas unitarias 

Son realizadas por el equipo de desarrollo y consisten en comprobar el correcto funcionamiento de las unidades de código; en otras palabras, validan el funcionamiento de los elementos más pequeños del sistema.  Las pruebas unitarias, al fomentar el cambio y la refactorización en etapas tempranas del desarrollo, reducen drásticamente los problemas y tiempos dedicados a la integración y permiten probar o depurar el código sin necesidad de disponer del sistema completo.

Para este tipo de pruebas podemos usar herramientas como Jest.

## Pruebas de integración 

Estas pruebas permiten identificar cómo funciona el sistema al unir los componentes y códigos unitarios, teniendo como objetivo encontrar defectos en las comunicaciones entre las unidades integradas y/o validar que el software se comporte de forma esperada entre las distintas interfaces.

Las pruebas de integración, por lo general se implementan dentro del ciclo luego de las pruebas unitarias. Una vez validado que las unidades por separado funcionan correctamente, se van agrupando una por una hasta que los módulos estén integrados, y así validar el comportamiento de los módulos en conjunto.

Un ejemplo de este tipo de pruebas es cuando mediante un login se accede al home de una cuenta personal. De forma unitaria se probaría que el login valide el usuario y la clave, mientras que independientemente se ensayaría el home. Pero en las pruebas de integración se valida que al verificar el login se envié al home de la cuenta personal con toda la información correcta.

Las buenas prácticas de QA indican que estas pruebas a diferencia de las unitarias, que son realizadas por los desarrolladores, deben ser ejecutadas por equipos especializados en Calidad de Software. La razón de esto se debe principalmente a que no exista un sesgo por parte del analista o desarrollador, y poder enfocarse a la funcionalidad definida en los requerimientos por parte del usuario.

Para este tipo de pruebas podemos usar herramientas como Cypress.

## Pruebas de regresión 

Este tipo de pruebas de regresión son las más utilizadas mientras avanza un proyecto, ya que se realizan para validar que las correcciones o modificaciones del código no hayan impactado negativamente las funcionalidades existentes del producto, es decir, verifican que el producto continúa desempeñándose correctamente con las nuevas funcionalidades, arreglos de fallos o cualquier cambio en la función existente.

Normalmente, se recomienda que sean automatizadas para reducir tiempos y esfuerzo en su ejecución, pero en caso que existan grandes modificaciones al sistema o el software se encuentre inestable se recomienda realizar un mix de pruebas manuales y automatizadas. 

Para automatizar las pruebas podemos usar herramientas como Selenium aunque Cypress en sus últimas versiones también permite realizarlas.


Existen distintos enfoques para realizar las pruebas de regresión, las cuales dependen principalmente del nivel de madurez del sistema, de la envergadura de las correcciones o cambios y del tiempo que se tiene para ejecutar nuevos ciclos o regresiones. Algunos de estos enfoques son los siguientes:

- **Retestear todo:** se ejecutan todas las pruebas del grupo o conjunto existente.

- **Selección de pruebas de regresión:** se ejecutan algunos casos de prueba seleccionados para verificar si el código modificado afecta o no a la aplicación. Esta opción normalmente se realiza cuando existe una trazabilidad clara entre el código y las funcionalidades a las cuales puede afectar.

- **Priorización de casos de prueba:** se priorizan los casos de prueba según el impacto comercial, las funcionalidades críticas y de uso frecuente. Esto permite reducir el conjunto de pruebas de regresión, minimizando el tiempo de los ciclos.

## Pruebas de aceptación 
 
Pertenecen a las últimas del software testing, donde el usuario final se relaciona directamente con el sistema, validando que funcione correctamente en escenarios reales.

Las pruebas de aceptación, generalmente son ejecutadas de forma manual, sin embargo, en muchas ocasiones no siguen un procedimiento estricto y se delegan en los usuarios finales.

Para obtener mejores resultados en esta etapa, se recomienda que los analistas de prueba apoyen a los usuarios con los datos de prueba y flujos de trabajo de la aplicación.

Se pueden automatizar como veremos con Selenium.

Las ventajas de las pruebas de aceptación son: 

- Aumenta la satisfacción de los clientes porque experimentan la aplicación ellos mismos.

- El criterio de la calidad del software es definido en etapas tempranas, lo cual permite tener una clara vista de la estrategia de testeo.

Si tu software es desarrollado y probado con las buenas prácticas de la industria y es sometido a las cinco pruebas funcionales mencionadas, puedes estar seguro que entregarás un producto de calidad y lograrás la confianza esperada de tus usuarios. 

### Ejercicio

- Se quiere desarrollar un software que permita a los usuarios registrarse, hacer login, jugar a juegos (se dispone de un catálogo de 100 juegos), consultar sus últimas partidas, jugar con otros usuarios y ver su ranking dentro de la aplicación.

Diseña un listado de pruebas y clasifícalas por tipo de prueba.