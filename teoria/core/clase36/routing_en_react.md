![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Routing en React.js

Antes de comenzar debemos instalar el paquete que nos va a permitir hacer routing en React: 

```

    npm install react-router-dom

```

**App.js:**

```javascript

    import React, { Component } from "react";
    import { BrowserRouter ,Link } from "react-router-dom";
    import MainComponent from "./components/Main";
    import "./App.css"
    class App extends Component {
    constructor(props) {
        super(props);
    }

    render() {
        return (
            <BrowserRouter>
                <div className="App">
                    ESTE ES EL COMPONENTE PADRE APP
                    <Link to={"/about"}>About</Link>
                    <Link to={"/list"}>List</Link>
                    <Link to={"/contact"}>Contact</Link>
                    <MainComponent />
                </div>
            </BrowserRouter>
        );
    }
    }
    export default App;

```
**Main.js:**

```javascript
    import React, { Component } from "react";
    import { Routes, Route } from "react-router-dom";
    import List from "../pages/List";
    import About from "../pages/About";
    import Contact from "../pages/Contact";
    class Main extends Component {
        constructor(props) {
            super(props);
        }

        render() {
            return (
            <div>
                <Routes>
                    <Route path="/list" element={<List />} />
                    <Route path="/about" element={<About />} />
                    <Route path="/contact" element={<Contact />} />
                </Routes>
            </div>
            );
        }
    }
    export default Main;

```
**Contact.js (componente página o vista):**

```javascript 
    import React, { Component } from "react";

    class Contact extends Component {
        constructor(props) {
            super(props);
        }
        render() {
            return <div>ESTE ES EL COMPONENTE CONTACT</div>;
        }
    }
    export default Contact;

```

**About.js (componente página o vista)**

```javascript
    import React , {Component} from "react"

    class About extends Component{
        constructor(props) {
            super(props);        
        }
        render() {
            return (
                <div>
                    ESTE ES EL COMPONENTE ABOUT
                </div>
                );
        }
    }
    export default About

```


**List.js (componente página o vista)**

```javascript
    import React, { Component } from "react";

    class List extends Component {
        constructor(props) {
            super(props);
        }

        render() {
            return <div>ESTE ES EL COMPONENTE LIST</div>;
        }
    }
    export default List;

```
**App.css:**
```css

    .App{
        display: flex;
        flex-direction: column;
        text-align: center;
        width: 50%;
        margin-left: 25%;
    }

```