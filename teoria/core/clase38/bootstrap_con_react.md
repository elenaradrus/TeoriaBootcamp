![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Bootstraps-React

![Logo Bootstrap React](../../../assets/core/clase38/bootstrap.png)

**[React-Bootstrap](https://react-bootstrap.netlify.app/getting-started/introduction/)** es una reimplementación completa de los componentes de Bootstrap usando React. Se sigue la misma metodología que cuando se usa **Bootstrap 5**.

1. **Instalamos** Bootstrap-React en un proyecto que tenga React:
 
```terminal
npm install react-bootstrap bootstrap
```

2. Añadimos a **index.js** el siguiente código:

```js
//IMPORTAMOS LOS ESTILOS DE BOOTSTRAP REACT
import 'bootstrap/dist/css/bootstrap.min.css';
```




3. Copiamos el código en **App.js**.

```js
import React from 'react';
// Importamos BrowserRouter para entender que el Componente Main va hacer de enrutador de componentes de React
import { BrowserRouter } from 'react-router-dom';
import './App.css';
import Main from './component/Main';


function App() {
  return (
    <div>
      <BrowserRouter>
        <Main />
      </BrowserRouter>
    </div>
  );
}

export default App;
```

3. Creamos el componete **Main.js**, nos bajamos el paquete "react-router-dom", y copiamos el código:

```js
import React from 'react';
// Importar Routes y Route para que se puedan linkear y redirigir a los componentes que se llaman
import { Routes, Route } from "react-router-dom";
import Welcome from './Welcome';
import Tercero from './Tercero';
import Bootstrap from './Bootstrap';

const Main = () => {
  return (
    <div className='Main'>

      <Routes>
        <Route path='/' element={<Welcome />} />
        <Route path='/tercero' element={<Tercero />} />
        <Route path='/bootstrap' element={<Bootstrap />} />
      </Routes>

    </div>
  )
}

export default Main
```
4. Creamos el componete **Tercero.js** y copiamos el código:


```js
import React, { useState, useEffect } from "react";
// Se importan aquellas etiquetas para que bootstrap-react lo entienda.
import { Button, Nav, Form, Container } from 'react-bootstrap';


function Tercero() {

    const [nombre, setNombre] = useState("");
    const [edad, setEdad] = useState("");
    const [info, setInfo] = useState("");

    useEffect(() => {
        if (nombre !== "") {
            console.log(`${nombre}`)
        }
    }, [nombre]);

    useEffect(() => {
        if (edad !== "") {
            console.log(edad);
        }
    }, [edad]);

    useEffect(() => {
        console.log("Carga la página");
    }, []);

    const enviar = () => {
        console.log(`Su nombre es ${nombre} y tienes ${edad}`);
        setInfo([nombre, edad]);
    }

    return (
        <Container fluid="md">
            <Button variant="info">
                <Nav.Link href="/"  >Volver</Nav.Link>{' '}
            </Button>

            <br />
            <br />
            <br />
            <br />

            {/* He copiado el formato de un formulario y he ido adaptando a la estructura que tenía antes con esta. */}
            <Form>
                <Form.Group className="mb-3" controlId="formBasicEmail">
                    <Form.Label>Nombre</Form.Label>
                    <Form.Control type="text" className="nombre" placeholder="Nombre" onChange={(e) => setNombre(e.target.value)} />
                    <Form.Text className="text-muted">
                        We'll never share your name with anyone else.
                    </Form.Text>
                </Form.Group>

                <Form.Group className="mb-3" controlId="formBasicPassword">
                    <Form.Label>Edad</Form.Label>
                    <Form.Control type="text" className="edad" placeholder="Edad" onChange={(e) => setEdad(e.target.value)} />
                </Form.Group>

                <Button value="Enviar" className="boton" onClick={() => enviar()} > Enviar </Button>

            </Form>
            {info ? <p> Hola {info[0]}, tienes {info[1]} años</p> : ""}

        </Container>
    )
}

export default Tercero;
```


5. Creamos el componete **Bootstrap.js** y copiamos el código:

```js
// importar React de la biblioteca.
import React from 'react';

//Si se utiliza una etiqueta de React-Bootstrap hay que importarla
import { Button, Nav, Card, Container, Row, Col } from 'react-bootstrap';

//Componente funcional -> 
function Bootstrap(props) {
    return (
        <Container fluid="xl">
            <Button variant="info">
                <Nav.Link href="/"> VOlVER </Nav.Link>{' '}
            </Button>{' '}
            <br />
            <br />
            <br />
            <br />
            <br />
            <Row>
                <Col>
                    <Card style={{ width: '18rem' }}>
                        <Card.Img variant="top" src="https://www.arqhys.com/wp-content/uploads/2014/03/que-es-el-color.png" />
                        <Card.Body>
                            <Card.Title>Card Title</Card.Title>
                            <Card.Text>
                                Some quick example text to build on the card title and make up the bulk of
                                the card's content.
                            </Card.Text>
                            <Button variant="primary">Go somewhere</Button>
                        </Card.Body>
                    </Card>
                </Col>
                <Col>
                    <Card style={{ width: '18rem' }}>
                        <Card.Img variant="top" src="https://astelus.com/wp-content/viajes/Pa%C3%ADs-de-origen-de-las-flores-m%C3%A1s-bonitas-del-mundo.jpg" />
                        <Card.Body>
                            <Card.Title>Card Title</Card.Title>
                            <Card.Text>
                                Some quick example text to build on the card title and make up the bulk of
                                the card's content.
                            </Card.Text>
                            <Button variant="primary">Go somewhere</Button>
                        </Card.Body>
                    </Card>
                </Col>
                <Col>
                    <Card style={{ width: '18rem' }}>
                        <Card.Img variant="top" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSB98BsAKvNDFe9ONADiKwd1uxpruyf2wW6Hg&usqp=CAU" />
                        <Card.Body>
                            <Card.Title>Card Title</Card.Title>
                            <Card.Text>
                                Some quick example text to build on the card title and make up the bulk of
                                the card's content.
                            </Card.Text>
                            <Button variant="primary">Go somewhere</Button>
                        </Card.Body>
                    </Card>
                </Col>
            </Row>
        </Container>

    )
}
export default Bootstrap;
```