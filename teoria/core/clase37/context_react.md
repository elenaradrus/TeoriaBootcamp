![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Context

La Context API de React es una forma de crear variables globales que podrás compartir fácilmente con otros componentes de tu aplicación. La alternativa consiste en pasar las propiedades de un componente padre a un componente hijo o nieto, y así sucesivamente en este orden descendente.

También podrías usar una librería de gestión de estado como Redux. Sin embargo, la Context API es una solución más ligera y sencilla para comenzar y para aplicaciones de tamaño moderado.

Context está diseñado para compartir datos que pueden considerarse “globales” para un árbol de componentes en React, como el usuario autenticado actual, el tema o el idioma preferido. Por ejemplo, en el código a continuación, pasamos manualmente una prop de “tema” para darle estilo al componente Button:

```javascript

    class App extends React.Component {
        render() {
            return <Toolbar theme="dark" />;
        }
    }

    function Toolbar(props) {
    // El componente Toolbar debe tener un prop adicional "theme"
    // y pasarlo a ThemedButton. Esto puede llegar a ser trabajoso
    // si cada botón en la aplicación necesita saber el tema,
    // porque tendría que pasar a través de todos los componentes.
  return (
        <div>
           <ThemedButton theme={props.theme} />
        </div>
     );
    }

    class ThemedButton extends React.Component {
    render() {
        return <Button theme={this.props.theme} />;
        }
    }

```

La alternativa con Context quedaría: 

```javascript 

    // Context nos permite pasar un valor a lo profundo del árbol de componentes
    // sin pasarlo explícitamente a través de cada componente.
    // Crear un Context para el tema actual (con "light" como valor predeterminado).
    const ThemeContext = React.createContext('light');

    class App extends React.Component {
    render() {
        // Usa un Provider para pasar el tema actual al árbol de abajo.
        // Cualquier componente puede leerlo, sin importar qué tan profundo se encuentre.
        // En este ejemplo, estamos pasando "dark" como valor actual.
        return (
        <ThemeContext.Provider value="dark">
            <Toolbar />
        </ThemeContext.Provider>
        );
    }
    }

    // Un componente en el medio no tiene que
    // pasar el tema hacia abajo explícitamente.
    function Toolbar() {
    return (
        <div>
        <ThemedButton />
        </div>
    );
    }

    class ThemedButton extends React.Component {
        // Asigna un contextType para leer el contexto del tema actual.
        // React encontrará el Provider superior más cercano y usará su valor.
        // En este ejemplo, el tema actual es "dark".
        static contextType = ThemeContext;
    render() {
        return <Button theme={this.context} />;
    }
    }

```

[OTRO_EJEMPLO](https://www.neoguias.com/context-api-react/#:~:text=la%20Context%20API-,Qu%C3%A9%20es%20la%20Context%20API%20de%20React,sucesivamente%20en%20este%20orden%20descendente.)