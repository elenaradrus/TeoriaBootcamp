![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps


# Sincronía y asincronía
Antes de aplicar estos métodos en programación, debemos conocer un poco de la ejecución de los programas. El espacio de tiempo en el cual se ejecuta un programa en un sistema operativo o entorno se denomina tiempo de ejecución. En dicho proceso se ejecutan una serie de instrucciones que componen complejos algoritmos; con el fin de realizar la acción para cual fue diseñado dicho sistema.

Dicho sistema se alimenta de entradas que, a su vez resultan en salidas, es como si estuvieran en fila esperando su turno, y esto  a su vez  incurre en tiempo de espera, idealmente corto. Tratando de optimizar el proceso, una solución clásica es asignar ese tiempo de espera a otro proceso, que pueda ejecutarse sin necesitar mucho tiempo, de este modo se aprovecha el uso del CPU. Nuestro proceso inconcluso se queda en la cola, mientras otro toma su lugar. Cuando las condiciones para la correcta ejecución de ese proceso se tienen (y el CPU está libre), este se reanuda. Existen varias políticas de repartición de CPU dependiendo del proceso en ejecución.

Aquí es donde comienza el juego de los métodos o llamadas síncronos y asíncronos. En el caso de métodos **síncrono, la invocación espera el resultado, es decir, invocas a un método y te quedas en ese punto esperando hasta que se devuelva un resultado (o un error)**. Por otra parte, con los **asíncronos, realizas la invocación, pero continúas con la ejecución y por lo general se define un callback (alguna función o método)  que recibirá la respuesta o el error para tomar alguna acción**.  En este ultimo la ejecución no se queda esperando la respuesta continua sin bloquear la ejecución del hilo actual.